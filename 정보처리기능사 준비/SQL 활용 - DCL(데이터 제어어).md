# SQL 활용 - DCL(데이터 제어어)

### 💡 DCL(Data Control Langauge)

- 데이터의 보안, 무결성, 회복, 병행 제어 등을 정의하는데 사용되는 언어
- DBA가 데이터 관리를 목적으로 사용함
- GRANT, REVOKE, ROLLBACK, COMMIT, SAVEPOINT 등이 있다.

## 1. GRANT, REVOKE

- DBA가 데이터베이스 사용자에게 **권한**을 부여하거나 취소하기 위한 명령어
- **GRANT:** 권한 부여
- **REVOKE**: 권한 취소
- **사용자 등급 지정 및 해제**
    - **DBA**: 관리자
    - **RESOURCE**: 테이블, DB 생성 가능자
    - **CONNECT**: 일반 사용자
    - 사용 예
        
        ```sql
        **GRANT 사용자등급 TO 사용자ID리스트 [IDENTIFIED BY 암호];
        REVOKE 사용자등급 FROM 사용자ID리스트;**
        ```
        
        ① 사용자 ID가 ‘NABI’인 사람에게 데이터베이스 및 테이블 생성 권한을 부여
        
        ⇒ GRANT RESOURCE TO NABI;
        
        ② 사용자 ID가 ‘STAR’인 사람에게 단순히 DB에 있는 정보를 검색할 수 있는 권한을 부여
        
        ⇒ GRANT CONNECT TO STAR;
        
- **테이블 및 속성에 대한 권한 부여 및 취소**
    
    ```sql
    GRANT 권한리스트 ON 개체 TO 사용자 [WITH GRANT OPTION];
    REVOKE [GRANT OPTION FOR] 권한리스트 ON 개체 FROM 사용자 [CASCADE];
    ```
    
    - 권한 종류
        - ALL, SELECT, INSERT, ALTER, UPDATE, DELETE 등
        - **WITH GRANT OPTION**: 부여 받은 권한을 다른 사용자에게 다시 부여할 수 있는 권한을 부여
        - **GRANT OPTION FOR**: 다른 사용자에게 권한을 부여할 수 있는 권한을 취소
        - **CASCADE**: 권한 취소 시 권한을 부여 받았던 사용자가 다른 사용자에게 부여 했던 권한도 취소
    - 사용 예
        
        ① 사용자 ID가 ‘NABI’인 사람에게 <고객> 테이블에 대한 모든 권한과 다른 사람에게 권한을 부여할 수 있는 권한까지 부여
        
        ⇒ GRANT ALL ON 고객 TO NABI WITH GRANT OPTION;
        
        ② 사용자 ID가 ‘STAR’인 사람에게 부여한 <고객> 테이블에 대한 권한 중 UPDATE 권한을 다른 사람에게 부여할 수 있는 권한만 취소
        
        ⇒ REVOKE GRANT OPTION FOR UPDATE ON 고객 FROM STAR ;
        
    

## 2. COMMIT

- 트랜잭션이 성공적으로 끝나고 DB가 새로운 일관성 상태를 가지기 위해 변경된 모든 내용을 DB에 반영하는 명령
- **AUTO COMMIT**
    
    : COMMIT 명령을 실행하지 않아도 DML문이 성공하면 자동으로 COMMIT, 실패하면 자동으로 ROLLBACK 되게 설정할 수 있다.
    

## 3. ROLLBACK

- 아직 커밋되지 않은 변경된 모든 내용들을 취소하고 DB를 이전 상태로 되돌림
    - 트랜잭션의 일부만 성공적으로 완료 되었다면 비일관성 상태를 가질 수 있기 때문에 ROLLBACK 시켜야만 한다.

## 4. SAVEPOINT

- 트랜잭션 내에 ROLLBACK 할 위치인 저장점을 지정하는 명령어
    - 저장점 지정 시 이름을 부여하며, ROLLBACK 시 지정된 저장점까지의 트랜잭션 처리 내용이 취소됨

### ✏️ 연습

**<사원> 테이블**

| 사원번호 | 이름 | 부서 |
| --- | --- | --- |
| 10 | 김기획 | 기획부  |
| 20 | 박인사 | 인사부 |
| 30 | 최재무 | 재무부 |
| 40 | 오영업 | 영업부 |
1. <사원> 테이블에서 ‘사원번호’가 40인 사원의 정보를 삭제한 후 COMMIT 하시오.
    
    ```sql
    DELETE FROM 사원 WHERE 사원번호=40;
    COMMIT;
    ```
    

1. <사원> 테이블에서 ‘사원번호’가 30인 사원의 정보를 삭제
    
    ```sql
    DELETE FROM 사원 WHERE 사원번호=30;
    ```
    

1. SAVEPOINT ‘S1’을 설정하고 <사원> 테이블에서 사원번호가 20인 사원의 정보를 삭제
    
    ```sql
    SAVEPOINT S1;
    DELETE FROM 사원 WHERE 사원번호=20;
    ```
    
2. SAVEPOINT ‘S2’를 설정하고 <사원> 테이블에서 사원번호가 10인 사원의 정보를 삭제
    
    ```sql
    SAVEPOINT S2;
    DELETE FROM 사원 WHERE 사원번호=10;
    ```
    

1. SAVEPOINT ‘S2’까지 ROLLBACK
    
    ```sql
    SAVEPOINT TO S2;
    ```
    
2. SAVEPOINT ‘S1’까지 ROLLBACK
    
    ```sql
    SAVEPOINT TO S1;
    ```
    
3. SAVEPOINT 없이 ROLLBACK
    
    ```sql
     ROLLACK;
    ```