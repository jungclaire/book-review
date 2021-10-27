## Chapter 07. 오류 처리

### 예외 처리 방식
오류 코드를 리턴하지 말고, 예외를 던져라.  
옛날에는 오류를 나타낼 때 에러코드를 던졌다. 하지만 예외를 던지는 것이 명확하고, 처리 흐름이 깔끔해진다.
  
예외를 던지고, 처리하는 방식  
1. 오류가 발생한 부분에서 예외를 던진다. (별도의 처리가 필요한 예외라면 checked exception으로 던진다.)
2. checked exception에 대한 예외처리를 하지 않는다면 메서드 선언부에 throws를 명시해야 한다.
3. 예외를 처리할 수 있는 곳에서 catch 하여 처리한다.
  
### Unchecked Exception을 사용하라
#### Exception 가계도  
<img width="324" alt="스크린샷 2021-10-27 오후 9 14 16" src="https://user-images.githubusercontent.com/83348294/139063393-caae4eda-151c-495c-8435-be86ba367ace.png">  
Checked vs Unchecked Exception  
- Exception을 상속하면 Checked Exception  
  명시적인 예외처리가 필요하다. (ex. IOException, SQLException)  
- RuntimeException을 상속하면 UncheckedException  
  명시적인 예외처리가 필요하지 않다. (ex. NullPointerException, IllegalArgumentException, IndexOutOfBoundException)  

#### Effective Java - Exception에 관한 규약  
자바 언어 명세가 요구하는 것은 아니지만, 업계에 널리 퍼진 규약으로 Error 클래스를 상속해 하위 클래스를 만드는 일은 자제하자.  
즉 사용자가 직접 구현하는 unchecked throwable은 모두 RuntimeException의 하위 클래스여야 한다.  
Exception, RuntimeException, Error를 상속하지 않는 throwable을 만들 수도 있지만, 이러한 throwable은 정상적인 사항보다 나을 게 업승면서 API 사용자를 헷갈리게 할 뿐이므로 절대로 사용하지 말자.  
  
#### Checked Exception이 나쁜 이유  
1. 특정 메소드에서 checked exception을 throw하고 상위 메서드에서 그 exception을 catch한다면 모든 중간단계 메소드에 exception을 catch한다면 모든 중간단계 메소드에 exception을 throw 해야 한다.
2. OCP(개방 폐쇄 원칙) 위배 : 상위 레벨 메소드에서 하위 레벨 메소드의 디테일에 대해 알아야 하기 때문에 OCP 원칙에 위배된다.
3. 필요한 경우 checked exception을 사용해야 되지만 일반적인 경우 득보다 실이 많다.  
  
#### Unchecked Exception을 사용하자  
안정적인 소프트웨어를 제작하는 요소로 확인된 예외가 반드시 필요하지는 않다는 사실이 분명해졌다.  
C#은 확인된 예외를 지원하지 않는다. 영웅적인 시도에도 불구하고 C++ 역시 확인된 예외를 지원하지 않는다.  
파이썬이나 루비도 마찬가지다. 그럼에도 불구하고 C#, C++, 파이썬, 루비는 안정적인 소프트웨어를 구현하기에 무리가 없다.  
  
### Exception 잘 쓰기
#### 예외에 메시지를 담아라  
#### 예외에 의미있는 정보 담기  
- 오류가 발생한 원인과 위치를 찾기 쉽도록 예외를 던질 때는 전후 상황을 충분히 덧붙인다.
- 실패한 연산 이름과 유형 등 정보를 담아 예외를 던진다.  
  
#### 예외를 감싸는 클래스를 만든다.
- port.open()시 발생하는 checked exception들을 감싸도록 port를 가지는 LocalPort 클래스를 만든다.
- port.open()이 던지는 checked exception들을 하나의 PortDeviceFailure exception으로 감싸서 던진다.

### 실무 예외 처리 패턴
getOrElse : 예외 대신 기본 값을 리턴한다.
1. null이 아닌 기본 값
2. 도메인에 맞는 기본 값  
  
getOrElseThrow : null 대신 예외를 던진다. (기본 값이 없다면)  
  
