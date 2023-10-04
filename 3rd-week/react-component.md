# React Component

#### REST API 와 GraphQL

* REST API란 무엇인가?
  * Representational State Transfer의 약자
  * GET, POST, PUT/PATCH, DELETE (CRUD)
  * Resource 중심
* GraphQL은 왜 등장했는가?
  * 웹 클라이언트가 데이터를 서버로부터 효율적으로 가져오는 것
  * Graph 자료구조
  * Query에서 얻고자 하는 걸 지정
  * Query(Read), Mutation(Command: Create, Update, Delete), Subscription(Event)
* REST API vs GraphQL

####

#### JSON

* JavaScript Object Notation
* 경량의 DATA-교환 형식
* name/value 형태의 쌍으로 collection 타입
* FE와 BE간 데이터 교환을 위해 만든 것
* String이지만 object형태를 가지길 원해서 만든  포맷

####

#### DSL(Domain-Specific Language)

* Domain-Specific Language(도메인 특화 언어)
* 관련 특정 분야에 최적화된 프로그래밍 언어 (ex. SQL)

####

#### 선언형 프로그래밍

* 어떤 방법으로 해야 하는지를 나타내기보다 무엇과 같은지를 설명하는 경우 혹은 함수형 프로그래밍 언어, 논리형 프로그래밍 언어, 혹은 제한형 프로그래밍 언어로 쓰인 경우를 선언형 프로그래밍이라고 함.
* 가독성과 추상화 수준ㅇ르 높여 개발자가 문제의 본질에 집중할 수 있도록 도와줌.
* 재사용성이 높고 병렬 처리가 유리함.
* React는 HTML과 유사한 모양의 DSL을 사용하여 선언형으로 UI 구성할 수 있음.
* 특수 분야 언어(Domain-specific language, DSL)의 형태로 자주 사용

####

#### 명령형 프로그래밍

* 프로그래밍의 상태와 상태를 변경 시키는 구문의 관점에서 연산을 설명하는 프로그래밍 패러다임
* 컴퓨터가 수행할 명령들을 순서대로 써 놓은 것

####

#### SRP(단일 책임 원칙)

* SOLID 원칙 중 하나로, 모든 클래스는 하나의 책임만 가지며, 클래스는 그 책임을 완전히 캡슐화하는 것을 의미함.
* 단일 클래스의 기능이 적어져 종속성이 줄어들기 때문에 결합도가 낮아짐.
* 컴포넌트가 변경되는 이유는 단 한 개여야 함.

####

#### Atomic Design

* 계층형 구조를 몇 가지 카테고리로 묶은&#x20;
* 데이터와 디자인의 분리를 강조
* atom, molecule, organism, template, page의 5가지 레벨로 구성되어 있음.
  * **atom**  : 더 이상 분해할 수 없는 기본 컴포넌트
  * **molecule** : 여러 개의 atom을 결합하여 자신의 고유한 특성을 가짐
  * **organism**
    * 앞 단계보다 좀 더 복잡하고 서비스에서 표현될 수 있는 명확한 영역과 특정 컨텍스트를 가짐.
    * 나누는 기준은 UI에서 명확한 영역을 가짐
  * **template** : page를 만들 수 있도록 여러 개의 organism, molecule로 구성.
  * **page** : 사용자가 볼 수 있는 실제 콘텐츠를 담고 있음. template의 인스턴스라고 할 수 있음.

####

#### React component 와 props

* props는 properties의 줄임말.
* 나눠진 컴포넌트를 서로 연결하는 방법
* TypeScript를 잘 쓰거나 잘못 쓰게 되는 포인트 중 하나. 적절한 균형점을 잡는 게 중요!
* 테스트 코드를 작성하면 재사용성을 평가하기 쉬워짐.
* 상위 컴포넌트가 하위 컴포넌트에 값을 전달할 때 사용(단방향)
