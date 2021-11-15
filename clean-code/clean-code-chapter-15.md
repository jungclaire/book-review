## Chapter 15. JUnit 들여다보기 & 16. SerialDatee 리팩토링

### 15장 JUnit 들여다보기
세상에 완벽한 코드는 없다.
- 의도를 명확하게 표현하기 위해 조건문을 메서드로 분리
- 전후 단계가 있는 변수들 사이 시간적인 결합을 해결하기 위해 리팩토링
- 더 적절한 의미로 네이밍 변경
- 불필요한 연산을 하는 코드 제거

### 16장 SerialDate 리팩토링
남의 코드를 비판하고, 내 코드의 비판을 듣는 건 편안하게 여겨야 할 활동이다.

#### Make it Work
- 테스트 코드가 모든 경우를 테스트하지 않는다. -> 주석 처리된 테스트 코드들을 모두 동작하도록 손본다.
- 코드의 구조를 개선하기 전에 버그들을 수정한다. 경계 조건 오류, 늘 거짓인 조건문

#### Make it Right
- 옛날 스타일 코드 제거
- serialVersioinUID를 컴파일러가 자동 생성하도록 함 (직접 변경하지 않아 생기는 버그보다 변경된 UID로 발생한 예외를 디버깅하는게 낫다)
- DayDate(SerialDate) Abstract Factory를 통해 생성하도록 한다.
- 캡슐화를 위해 접근제한자를 수정 (public -> private)
- 사용되지 않는 변수 제거
- 불필요한 주석 제거

### 오픈 소스 접근법