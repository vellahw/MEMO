# SQL 활용 - 조건에 따른 SELECT 연습

![KakaoTalk_20231029_231548805.jpg](SQL%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%E1%86%BC%20-%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%8B%E1%85%A6%20%E1%84%84%E1%85%A1%E1%84%85%E1%85%B3%E1%86%AB%20SELECT%20%E1%84%8B%E1%85%A7%E1%86%AB%E1%84%89%E1%85%B3%E1%86%B8%20299db78893a3456ea50630c5bd45d7a0/KakaoTalk_20231029_231548805.jpg)

<사원> 테이블

```sql
-- 1. 사원T에서 주소만 검색, 같은 주소는 한 번만 출력
SELECT DISTINCT 주소 FROM 사원;

-- 2. 사원T에서 '기본급'에 특별수당 10을 더한 월급을 'XX부서의 XXX의 월급 XXX' 형태로 출력
SELECT 부서+'부서의' AS 부서2,
			 이름+'의 월급' AS 이름2,
			 기본급+10 AS 월급
FROM 사원;

-- 3. 사원T에서 부서는 '기획'이고 기본급이 110보다 큰 튜플을 검색
SELECT * FROM 사원 WHERE 부서='기획' AND 기본급 > 110;

-- 4. 사원T에서 부서가 '기획'이거나 '인터넷인' 튜플
SELECT * FROM 사원 WHERE 부서='기획' OR 부서='인터넷';
--  WHERE IN 사용: SELECT * FROM 사원 WHERE 부서 IN ('기획', '인터넷');

-- 5. 사원T에서 성이 '김'인 사람을 검색
SELECT * FROM 사원 WHERE 이름 LIKE '김%';

-- 6. 사원T에서 '생일'이 '01/01/69'에서 '12/31/73' 사이인 튜플을 검색
SELECT * FROM 사원
WHERE 생일 BETWEEN '01/01/69' AND '12/31/73';

-- 7. 사원T에서 주소가 NULL인 튜플을 검색
SELECT * FROM 사원
WHERE 주소 IS NULL;

-- 8. 사원T에서 주소를 기준으로 내림차순 정렬하고 상위 2개만 출력
SELECT TOP 2
FROM 사원
ORDER BY 주소 DESC;

-- 9. 사원T에서 부서를 기준으로 오름차순 정렬, 같은 부서에 대해선 이름을 기준으로 내림차순 정렬
SELECT * FROM 사원
ORDER BY 부서 ASC, 이름 DESC; -- 부서를 기준으로 이미 묶였으니 이름 내림차

-- 10. 사원T에서 부서별 기본급의 평균을 구하시오
SELECT 부서, AVG(기본급) AS 평균
FROM 사원
GROUP BY 부서;

-- 11. 사원T에서 부서별 튜플 수를 구하시오
SELECT 부서, COUNT(*) AS 사원수
FROM 사원
GROUP BY 부서;

-- 12. 사원T에서 기본급이 100 이상이고 사원수가 2명 이상인 부서의 튜플수를 구하시오
SELECT 부서, COUNT(*) AS 사원수
FROM 사원
WHERE 기본급 >= 100
GROUP BY 부서
HAVING COUNT(*) >= 2;
```