## Chapter 1. 클린코드
<img width="351" alt="스크린샷 2021-10-10 오후 10 57 04" src="https://user-images.githubusercontent.com/83348294/136698808-097349bb-9013-42eb-acf1-4d31b02714e6.png">

### 나쁜 코드란?
- 성능이 나쁜 코드: 불필요한 연산이 들어가서 개선의 여지가 있는 코드
- 의미가 모호한 코드: 이해하기 어려운 코드. 네이밍과 그 내용이 다른 코드
- 중복된 코드: 비슷한 내용인데 중복되는 코드

### 나쁜 코드가 나쁜 이유
- 나쁜 코드는 계속 나쁜 코드가 만들어지도록 하기 때문
- 나쁜 코드는 팀 생산성을 저하시킨다. 기술부채를 만들어 수정을 더 어렵게 한다.
- 현 시스템을 유지보수하며 대체할 새로운 시스템 개발은 현실적으로 매우 어렵다.

### 나쁜 코드를 짜는 이유
- 일정이 촉박해서... 일정 안에 새로운 기능을 완성해야 해서. 하지만 나쁜 코드는 생산성을 저하하기 때문에 오히려 일정을 맞추기 어렵다.
- 생각보다 영향범위가 넓어서 건드렸다가 다른 부분에 버그가 발생할까봐. 하지만 기술부채는 결국 부메랑처럼 돌아온다.

### 클린코드란?
- 성능이 좋은 코드
- 의미가 명확한 코드 = 가독성이 좋은 코드
- 중복이 제거된 코드
