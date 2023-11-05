# TSyringe

#### TSyringe

* TypeScript용 경량의 종속성 주입 (Dependency Injection, DI) 라이브러리
* 객체간의 결합도를 낮추고, 코드의 재사용성을 높이며, 테스트 용이성을 향상시키기 위해 사용
* 주요 기능
  * 종속성 주입
    * 클래스 생성자에 필요한 의존성을 자동으로 주입
  * 싱글톤과 트랜지언트 등록
    * 싱글톤으로 등록된 종속성은 애플리케이션에서 하나의 인스턴스만 존재하며, 트랜지언트는 요청할 때마다 새로운 인스턴스를 생성함.
  * 커스텀 스코프
    * 사용자 정의 스코프를 만들어 관리할 수 있음.
  * 자동 등록
    * 특정 폴더나 패턴을 기반으로 종속성을 자동으로 등록함.

#### 의존성 주입(Dependency Injection)

* 객체 지향 프로그래밍에서 사용되는 디자인 패턴 중 하나
* 객체가 자신의 의존성, 즉 객체가 작동하는 데 필요한 다른 객체(서비스, 클라이언트가 사용할 객체 등)를 직접 생성하지 않고 외부로부터 받아서 사용하는 기법
* 유연하고 테스트 가능하며 유지보수가 용이한 코드를 작성하는 데 중요한 역할
* 목적
  * 결합도 감소
  * 코드 재사용성 증가
  * 유닛 테스트 용이
  * 유지보수성 향상
* 구현 방식
  * 생성자 주입(Constructor Injection)
  * 세터 주입(Setter Injection)
  * 인터페이스 주입(Interface Injection)

#### reflect-metadata

* JavaScript에 데코레이터와 함께 사용할 수 있는 메타데이터를 정의하기 위한 라이브러리
* ES6 리플렉션 API와 메타데이터 API에 대한 폴리필(polyfill) 기능을 제공
* 타입스크립트에서 타입 정보를 런타임에 활용할 수 있도록 하여, 강력한 객체 지향 프로그래밍 기능을 구현하기 위해 사용함.

#### singleton (싱글톤)

* 특정 클래스의 인스턴스가 프로그램 내에 오직 하나만 존재하도록 보장하는 것
* 전역 변수를 사용하지 않고 애플리케이션 전역에서 접근 가능한 하나의 인스턴스를 생성하기 위해 사용
* 오용하면 시스템의 결합도를 높이고 테스트하기 어려운 코드를 만들 수 있으므로 주의해야 함.
*   singleton 사용 하다 에러 발생 시 해결 방법

    ```javascript
    import { singleton } from "tsyringe";

    @singleton()
    ```

    * 최상위 컴포넌트(index.html 내 추가된 js모듈 확인) 파일 내 아래 import 추가
    *   setupTests.ts 파일 생성 후 아래 import 추가

        ```javascript
        import 'reflect-metadata';
        ```
    *   tsconfig.json 내용 추가

        ```javascript
        "experimentalDecorators": true,                   /* Enable experimental support for legacy experimental decorators. */
        "emitDecoratorMetadata": true
        ```

