## Chapter 09. 단위 테스트

### 테스트 코드의 중요성
#### 테스트 코드는 중요하다.
- 테스트 코드는 실수를 바로잡아준다.
- 테스트 코드는 반드시 존재해야 하며, 실제 코드 못지 않게 중요하다.
- 테스트 케이스는 변경이 쉽도록 한다. 코드에 유연성, 유지보수성, 재사용성을 제공하는 버팀목이 바로 단위테스트다.  
테스트 케이스가 있으면 변경이 두렵지 않다. 테스트 케이스가 있다면 모든 변경이 잠정적인 버그다.  
테스트 커버리지가 높을수록 버그에 대한 공포가 줄어든다.  
- 지저분한 테스트 코드는 테스트를 안하니만 못하다.

#### Effective Unit Test 테스트의 중요성
테스트는 실사용에 적합한 설계를 끌어내준다.  
테스트를 작성해서 얻게 되는 가장 큰 수확은 테스트 자체가 아니다. 작성 과정에서 얻는 깨달음이다.  

#### 테스트는 자동화되어야 한다.

### 테스트의 종류
- Unit Test: 프로그램 내부의 개별 컴포넌트의 동작을 테스트한다. 배포하기 전에 자동으로 실행되도록 많이 사용한다.
- Integration Test: 프로그램 내부의 개별 컴포넌트들을 합쳐서 동작을 테스트한다.  
Unit Test는 각 컴포넌트를 고립시켜 테스트하기 때문에 컴포넌트의 interaction을 확인하는 Integration Test가 필요하다.
- E2E Test: End to End Test. 실제 유저의 시나리오대로 네트워크를 통해 Endpoint를 호출해 테스트한다.

### Unit Test 작성
#### 테스트 라이브러리를 사용하자
- JUnit: for unit test
- Mockito: for mocking dependencies
- Wiremock: for stubbing out external services
- Pact: for writing CDC tests
- Selenium: for writing UI-driven end-to-end tests
- REST-assured: for writing REST API-driven end-to-end tests  
  
JUnit5 + mockito를 많이 사용한다.

#### TEST Double
테스트에서 원본 객체를 대신하는 객체  
  
Stub  
- 원래의 구현을 최대한 단순한 것으로 대체한다.
- 테스트를 위해 프로그래밍된 항목에만 응답한다.
  
Spy  
- Stub의 역할을 하면서 호출에 대한 정보를 기록한다.
- 이메일 서비스에서 메시지가 몇 번 전송되었는지 확인할 때  
  
Mock
- 행위를 검증하기 위해 가짜 객체를 만들어 테스트하는 방법
- 호출에 대한 동작을 프로그래밍할 수 있다.
- Stub은 상태를 검증하고 Mock은 행위를 검증한다.

#### given-when-then 패턴을 사용하자
given: 테스트에 대한 pre-condition  
when: 테스트하고 싶은 동작 호출  
then: 테스트 결과 확인

### FIRST 원칙
- Fast: 빠르게  
테스트는 빨리 돌아야 한다. 자주 돌려야 하기 때문이다.
- Independent: 독립적으로  
각 테스트를 독립적으로 작성한다. 서로에게 의존하면 실패한 원인을 찾기 어려워진다. (다른 테스트의 실패로 인한건지, 코드 오류인지)  
- Repeatable: 반복가능하게  
테스트는 어떤 환경에서도 반복 가능해야 한다. 실제 환경, QA 환경, 모든 환경에서 돌아가야 한다.
- Self-Validating: 자가검증하는  
테스트는 bool값으로 결과를 내야 한다.
- Timely: 적시에  
테스트하려는 실제 코드를 구현하기 직전에 구현한다.
