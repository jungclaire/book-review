## Chapter 05. 형식 맞추기
### 포맷팅이 중요한 이유
- 가독성에 필수적이다.
- 코드를 수월하게 읽어나갈 수 있다.
- 아마추어처럼 보이지 않는다.
- 포맷팅으로 인해 코드를 잘못 해석해 버그를 발생할 위험을 줄인다.

### 클린코드 포맷팅
#### 적절한 길이 유지
200라인  
- 코드 길이를 200줄 정도로 제한하는 것은 반드시 지킬 엄격한 규칙은 아니지만, 일반적으로 큰 파일보다는 작은 파일이 이해하기 쉽다.  
> 현업에서 대부분 코드들을 200라인 정도로 유지한다.  
- 코드 길이가 200라인을 넘어간다면 클래스가 여러 개의 일을 하고 있을 수 있다. SRP 위배!
#### 밀접한 개념은 가까이
밀접한 개념은 서로 가까이 둔다.
- 행 묶음은 완결된 생각 하나를 표현하기 때문에 개념은 빈 행으로 분리한다.
- 변수는 사용되는 위치에서 최대한 가까이 선언한다.

### Java Class Declarations
클래스 내부 코드 순서
1. static 변수: public -> protected -> package -> private 순서
2. instance 변수: public -> protected -> package -> private 순서
3. 생성자
4. 메서드: public 멤서드에서 호출되는 private 메서드는 그 아래에 둔다.  
가독성 위주로 그룹핑한다.

### Team Coding Convention
개발 언어의 컨벤션이 우선이지만, 애매한 부분은 팀 컨벤션을 따른다.  
없다면 함께 만들어 가는 것도 좋다.  
Reference  
https://google.github.io/styleguide/javaguide.html  
https://naver.github.io/hackday-conventions-java/
