## Chapter 06. 객체와 자료구조

### 자료구조 vs 객체
|자료구조(Data Structure)|객체(Object)|
|:---|:---|
|데이터 그 자체|비즈니스 로직과 관련|
|자료를 공개한다.|자료를 숨기고, 추상화한다. 자료를 다루는 함수만 공개한다.|
|변수 사이에 조회 함수와 설정 함수로 변수를 다룬다고 객체가 되지 않는다. (getter, setter)|추상 인터페이스를 제공해 사용자가 구현을 모른 채 자료의 핵심을 조작할 수 있다.|  


#### 상황에 맞는 선택을 하면 된다.
- 자료구조를 사용하는 절차적인 코드는 기본 자료 구조를 변경하지 않으면서 새 함수를 추가하기 쉽다.
- 절차적인 코드는 새로운 자료 구조를 추가하기 어렵다. 그러려면 모든 함수를 고쳐야 한다.
- 객체지향 코드는 기존 함수를 변경하지 않으면서 새 클래스를 추가하기 쉽다.
- 객체 지향 코드는 새로운 함수를 추가하기 어렵다. 그러면 모든 클래스를 고쳐야 한다.  
  

### 객체 - 디미터 법칙
<img width="288" alt="스크린샷 2021-10-27 오후 9 02 52" src="https://user-images.githubusercontent.com/83348294/139061864-7abd1fcb-45df-4615-a954-8a0a71e8e5ba.png">
클래스 C의 메서드 f는 다음과 같은 객체의 메서드만 호출해야 한다.
- 클래스 C
- 자신이 생성한 객체
- 자신의 인수로 넘어온 객체
- C 인스턴스 변수에 저장된 객체


### DTO
DTO(Data Transfer Object) = 자료구조
#### 다른 계층 간 데이터를 교환할 때 사용
- 로직 없이 필드만 갖는다.
- 일반적으로 클래스명이 Dto(or DTO)로 끝난다.
- getter, setter를 갖기도 한다.

*Beans  
Java Beans: 데이터 표현이 목적인 자바 객체
- 멤버 변수는 privte 속성이다.
- getter와 setter를 가진다.


### Active Record
Database row를 객체에 맴핑하는 패턴  
- 비즈니스 로직 메서드를 추가해 객체로 취급하는 건 바람직하지 않다.
- 비즈니스 로직을 담으면서 내부 자료를 숨기는 객체는 따로 생성한다.
- 하지만 객체가 많아지면 복잡하고 가까운 곳에 관련 로직이 있는 것이 좋으므로 현업에서는 Entity에 간단한 멤서드를 추가해 사용한다.  
  
<img width="255" alt="스크린샷 2021-10-27 오후 9 09 07" src="https://user-images.githubusercontent.com/83348294/139062731-35212faf-bbb7-4b77-ac0d-2953e4671377.png">  
  
Active Record  
- 객체가 row를 담을 뿐 아니라 database에 대한 접근을 포함한다.
- Person의 속성을 담을 뿐 아니라, 생성수정도 객체 안에서 수행할 수 있다.  
  
<img width="315" alt="스크린샷 2021-10-27 오후 9 09 31" src="https://user-images.githubusercontent.com/83348294/139062778-3c840690-add8-44cb-86b3-0c55cda78914.png">  
Data Mapper
- row를 담는 객체와 database에 접근할 수 있는 객체가 분리되어 있다.
- Person은 값만 담고 있고 생성, 수정 등 액션은 Person Mapper에서 담당한다.
