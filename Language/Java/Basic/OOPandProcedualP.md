# OOP and Procedual Programming
- 서로 반대관계인가? [X]
- 사상적 공통점 : 
    - OOP : 프로그램을 수많은 객체 단위로 나눔
    - PP : 데이터를 처리하는 함수를 구조화(간단하게, 프로시저를 작성하는 내용으로 생각해보자. 그럼 이해가 빠를듯)
        - 배경적 지식: 구조적 프로그래밍(다익스트라)
            - [Wikipedia](https://ko.wikipedia.org/wiki/구조적_프로그래밍)
    - 중요한 포인트는, 서로가 반대개념이 아닌 두 컨셉 모두 명령형 프로그래밍의 하위개념이라는게 포인트(즉, 면접에서 설명할 때 두 개의 차이에 대해서 서로 상반된 개념이에요 하면 땡)
- 문제점?
    - 서로 비슷해 보이는데 어떤 게 문제인가? - 데이터 처리 방법(함수)의 구조화는 성공해도, 데이터 자체의 구조화를 못하면서, 이에 따를 전역 네임스페이스 포화문제 발생
        - 무슨 뜻이냐면, 비슷한 역할을 하는 변수 (ex. checkComponent1Status,2,3,4,...) 의 선언에 따른, 관리해야 할 변수가 폭발적으로 증가함에 따라 관리가 어려움. 하나의 함수가 다른 변수 등에 엉뚱하게 영향을 미치는 경우를 생각해보면 될듯?
    - 데이터를 처리하는 방법의 구조화(프로시저)가, 데이터 처리방법 및 데이터 그 자체로 확장된 것.

- 그럼 차이점에 대해서 논하라 하면 어떤 것을 언급해야 하는가?
    - 데이터를 구조화 하기 위한 작업이 언어 관점에서 고려되었는가?를 봐야하는게 맞아보임.
        - C언어는 struct 있잖아요! -- Data access modifier (public, protected, private 개념은?)
    - 순차적으로 처리되기 때문에 -- 이건 순차 프로그래밍에 맞는 관점이지, 두 패러다임의 차이로 보기는 어렵다. 
        - 객체지향에서 기능을 메소드로 분리하면, 그게 절차지향 언어의 메소드와 기능적으로 다른 역할을 하는가? (ex. 절차지향 언어로 작성한 LinkedList의 append 명령과, 객체지향 언어로 작성한 LinkedList의 append 명령은, 그 처리에 있어서 순차적이므로 이 부분을 차이로 언급하기엔 관계가 없음)
    - 실행 컨텍스트 영역에 대해서, 개발하는 관점에서 같은 변수명을 이용하더라도, 다른 객체, 다른 네임스페이스에 존재하는 내용으로 구분하게 된다면, 서로 영향을 주지 않음. (ex. Apple instance, Banana instance 안에 당도를 뜻하는 sugarContent라는 property가 있다고 가정했을 때, 다른 인스턴스 안에 메소드 처리를 통해 해당 값을 변조한다고 했을 때, 일반적으로 "정상"적으로 구현했다면 서로 다른 인스턴스간에 영향을 주지는 않음. 그런데 절차지향적 언어의 함수 개념에서, 당연히 입력을 잘 조정하면 문제는 없으나, 일반적으로 그러한 함수를 같이 움직이지 않음(당연히, 함수 자체에 대해서는 함수를 어떻게 작동시킬건지(기능)이 포인트이기 때문))

 - 이를 포함한, 객체지향의 4요소 언급 및, 5 원칙을 반드시 기억할것
    - 4요소 :
        - encapsulation(변수, 함수를 하나의 단위로 묶음)
        - inheritance(자식 클래스가 부모 클래스의 특성, 기능을 물려받는 것. 필요한 기능만 재정의해서 사용하는 것을 오버라이딩이라고 부름)
        - polymorphism(변수, 혹은 함수가 상황에 따라 다른 의미로 해석될 수 있음)
    - 5원칙(SOLID):
        - Single Responsibility Principle(단일책임원칙) : 객체는 오로지 하나의 책임만 가져야함(오직 하나의 변경의 이유를 가져야함)
        - Open-Closed Principle(개방-폐쇄 원칙) : 확장에 대해서는 개방적이나, 수정에 대해서는 폐쇄적이어야함
        - Liscov Substitution Principle(리스코프 치환 원칙) : 자식 클래스는, 언제나 자신의 부모 클래스를 대체할 수 있다. 부모 클래스가 들어가야 할 자리에, 자식 클래스가 들어가더라도 잘 작동해야함.
        - Interface Segregation Principle(인터페이스 분리 원칙) : 인터페이스를 다시 작게 나누어서 만든다
        - Dependency Inversion Principle(의존성 역전 원칙) : 추상성이 높고 안정적인 고수준의 클래스는, 구체적이고 불안정한 저수준의 클래스에 의존해서는 안된다. (IoC와는 다른 개념임을 주의)