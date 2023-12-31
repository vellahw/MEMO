# 운영체제 (OS; Operating System)

- 운영체제는 컴퓨터 시스템의 자원들을 효율적으로 관리한다.
- 사용자가 컴퓨터를 편리하고 효과적으로 사용할 수 있도록 환경을 제공하는 여러 프로그램의 모임
- 다른 응용 프로그램이 유용한 작업을 할 수 있도록 환경을 제공한다.

## 운영체제의 목적

- 처리능력 향상
- 신뢰도 향상
- 사용 가능도 향상
- 반환 시간 단축
    
    ⇒ 이 네가지가 운영체제의 성능을 평가하는 기준이 됨
    

1. **처리 능력(Throughput)**
    
    : 일정 시간 내에 시스템이 처리하는 일의 양
    
2. ****************************반환 시간(Turn Around Time)****************************
    
    : 시스템에 작업을 의뢰한 시간부터  처리가 완료될 때까지 걸린 시간
    
3. **사용 가능도(Availability)**
    
    : 시스템을 사용할 필요가 있을 때 즉시 사용 가능한 정도
    
4. **신뢰도(Reliability)**
    
    : 시스템이 주어진 문제를 정확하게 해결하는 정도
    

## 운영체제의 구성

### **제어 프로그램**

- **감시 프로그램**
    
    : 각종 프로그램의 실행과 시스템 전체의 작동 상태를 감시/감독하는 프로그램
    
- **작업 제어 프로그램**
    
    : 어떤 업무를 처리하고 다른 업무로의 이행을 자동으로 수행하기 위한 준비 및 그 처리에 대한 완료를 담당하는 프로그램
    
- **자료 관리 프로그램**
    
    : 주기억장치와 보조기억장치 사이의 자료를 전송이나 파일의 조각 및 처리, 입/출력 자료와 프로그램간의 논리적 연결 등 시스템에서 취급하는 파일과 데이터를 표준적인 방법으로 처리할 수 있도록 관리하는 시스템
    

### **처리 프로그램**

- **언어 번역 프로그램**
    
    : 원시 프로그램을 기계어 형태의 목적 프로그램으로 번역하는 프로그램
    
- **서비스 프로그램**
    
    : 사용자의 편리를 위해 시스템 제공자가 미리 작성하여 사용자에게 제공해주는 것. 사용빈도가 높음
    
- **문제 프로그램**
    
    : 특정 업무 및 문제 해결을 위해 사용자가 작성한 프로그램
    

## 운영체제의 종류

- Windows, Unix, Linux, MacOS, MS-DOS, Android, iOS

***안드로이드 코드네임**

안드로이드는 2019년 9월 공개된 버전 10 이전까지 알파벳 순서대로 디저트의 이름을 붙여 코드네임으로 사용했음

버전 1.0은 공식적인 코드네임이 없고 1.1은 PM이 알파벳 순서를 무시하고 붙인 이름

| 버전 | 코드네임 |
| --- | --- |
| 1.1 | 프티프루(Petit Four) |
| 1.5 | 컵케이크(Cupcake) |
| 1.6 | 도넛(Donut) |
| 2.0/2.1 | 에클레어(Eclair |
| 2.2 | 프로요 (Froyo |
| 2.3 | 진저브레드 (G |
| 3.0/3.1/3.2 | 허니콤 (H |
| 4.0 | 아이스크림
샌드위치 (I |
| 4.1/4.2/4.3 |  젤리빈 (J |
| 4.4 | 킷캣 (K |
| 5.0/5.1 | 롤리팝 (L |
| 6.0/6.0.1 | 마시멜로 (M |
| 7.0/7.1 | 누가 (N |
| 8.0/8.1 | 오레오 (O) |
| 9 | 파이 (P |

## 운영체제 운용 기법의 발달 과정

### 일괄 처리 시스템(Batch Processing System)

- 초기의 컴퓨터 시스템에서 사용된 형태
- 일정량 또는 일정 기간 동안 데이터를 모아서 한꺼번에 처리함

### 다중 프로그래밍 시스템(Multi-Programming System)

- 하나의 CPU와 주기억장치를 이용
- 여러개의 프로그램을 동시에 처리함

### 시분할 시스템(Time Sharing System)

- 여러명의 사용자가 사용하는 시스템에서 컴퓨터가 사용자드르이 프로그램을 번갈아 처리함
- 그로인해 각 사용자에게 독립된 컴퓨터를 사용하는 느낌을 주는 것
- 라운드 로빈(Roun Robin) 방식이라고도 한다.

### 다중 처리 시스템(Multi- Processing System)

- 여러개의 CPU와 하나의 주기억장치를 이용하여 여러개의 프로그램을 동시에 처리

### 실시간 처리(Real Time Processing System)

- 데이터 발생 즉시나 데이터 처리 요구가 있는 즉시 처리하여 결과를 산출함

### 범용 시스템(General-Purpose System)

- 일괄 처리 시스템, 시분할 시스템, 다중 처리 시스템, 실시간 처리 시스템을 한 시스템에서 모두 제공
- 다중 모드 처리 시스템이라고도 한다.

### 분산 처리 시스템(Distributed Processing System)

- 여러개의 컴퓨터(프로세서)를 통신 회선으로 연결하여 하나의 작업을 처리함

**일괄 처리 시스템 → 다중 프로그래밍 시스템 → 시분할 시스템 → 다중 처리 → 실시간 처리 시스템→ 범용 시스템 → 분산 처리 시스템**