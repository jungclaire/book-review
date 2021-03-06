## Chapter 10. 클래스

### 캡슐화
객체의 실제 구현을 외부로부터 감추는 방식
![encapsulation_java](https://user-images.githubusercontent.com/83348294/140053722-4d9d151b-5ad5-4699-b1b5-ae1c0239a57b.png)
- 클래스를 개발할 때 기본적으로 구현을 감추고, 외부 객체와 상호작용하는 부분만 노출한다.
- 외부의 잘못된 사용을 방지한다.
- 경계에서 배웠던 부분! > Map

### 단일 책임 원칙
#### 클래스는 작아야 한다.  
클래스가 맡은 책임이 한 개인가
- 함수와 마찬가지로 클래스도 작아야 한다.
- 함수는 라인 수로 크기를 측정했는데, 클래스는 맡은 책임의 수로 크기를 측정한다.
- 클래스 설명은 만일, 그리고, 하여, 하지만을 사용하지 않고 25 단어 내외로 가능해야 한다. > 책임이 한가지여야 한다.
