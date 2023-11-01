---
description: 관심사의 분리 === 내 알 바 아님
---

# External Store

#### 관심사의 분리

* S/W 엔지니어링에서 사용되는 디자인 원칙 중 하나로 애플리케이션의 상태 관리를 효율적으로 할 수 있음.
* 복잡한 프로그램을 더 작고, 관리하기 쉬운 부분으로 나눔. 각 부분은 특정 기능이나 관심사에 중점을 두어, 코드의 가독성, 유지 보수성, 확장성을 향상시킴.

#### Layered Architecture

* 계층형 아키텍처는 소프트웨어 설계를 단순화하기 위해 다양한 기능을 분리된 계층으로 나누는 방식
* 각 계층은 특정 책임과 역할을 가지며, 하위 계층은 상위 계층에 서비스를 제공
* 코드의 유지 관리, 확장성 및 테스트 용이성을 향상
* **계층**
  * 프레젠테이션 계층 (Presentation Layer)
    * 사용자 인터페이스와 사용자 입력을 처리
  * 비즈니스 로직 계층 (Business Logic Layer)
    * 애플리케이션의 핵심 기능과 비즈니스 규칙을 구현
  * 데이터 액세스 계층 (Data Access Layer)
    * 데이터베이스나 외부 시스템과의 통신을 담당
  * 서비스 계층 (Service Layer)
    * 선택적으로 사용
    * 비즈니스 로직 계층과 프레젠테이션 계층 사이 비즈니스 로직의 재사용성을 높이고 시스템의 모듈성을 향상

#### Flux Architecture

* 클라이언트 사이드의 웹 애플리케이션을 더 쉽게 만들기 위해 사용
* Flux는 단방향 데이터 흐름을 가진 구조로, 애플리케이션의 상태와 로직을 좀 더 예측 가능하게 만듦
* **주요 구성 요소**
  * 디스패처 (Dispatcher)
    * 모든 데이터 흐름을 관리하는 중앙 허브 역할
    * 액션은 디스패처를 통해 스토어로 전달
  * 스토어 (Store)
    * 애플리케이션의 상태와 로직을 가짐
    * 스토어는 디스패처를 통해 전달되는 액션을 통해 상태를 업데이트하며, 변경이 있을 때마다 뷰에게 알림
  * 액션 (Action)
    * 뷰에서 발생하는 사용자의 입력이나 서버로부터의 응답을 표현하는 단순한 객체
    * 어떤 일이 일어나야 할지를 나타내지만, 그 일이 어떻게 처리될지는 스토어에서 결정
  * 뷰 (View)
    * React 컴포넌트를 사용하여 만듦
    * 뷰는 사용자에게 UI를 제공하며, 사용자의 입력을 받아 액션을 발생시킴.
    * 토어의 변경을 구독하여 스토어의 상태가 바뀌었을 때 UI를 업데이트
* **주요 특징**
  * 단방향 데이터 흐름
    * 데이터는 항상 한 방향으로 흐르기 때문에, 애플리케이션의 상태를 이해하고 디버깅하기 쉬움
  * 중앙 집중식 디스패처
    * 모든 액션은 중앙 집중식 디스패처를 통해 스토어로 전달되며, 이는 애플리케이션의 행동을 쉽게 추적할 수 있음
  * 상태는 스토어에 의해서만 변경
    * 애플리케이션의 상태를 예측 가능함

#### useReducer

* 복잡한 상태 로직을 다룰 때 useState보다 더 선호되는 방법
* 컴포넌트의 상태 업데이트 로직을 컴포넌트에서 분리시킬 수 있으며, 또한 다양한 상태를 한 곳에서 관리할 수 있음.
* 사용 방법
  * useReducer는 현재 상태와 dispatch 함수를 포함하는 배열을 반환함.
  * dispatch 함수는 액션 객체를 인자로 받아 reducer 함수를 호출
  * reducer
    * 상태를 업데이트하는 함수
    * (state, action) => newState 형태를 가지며 현재 상태와 액션 객체를 인자로 받아 새 상태를 반환
  *   initialState

      * 초기 상태 값을 의미

      ```javascript
      import React, { useReducer } from 'react';

      function counterReducer(state, action) {
        switch (action.type) {
          case 'increment':
            return { count: state.count + 1 };
          case 'decrement':
            return { count: state.count - 1 };
          default:
            return state;
        }
      }

      function Counter() {
        const [state, dispatch] = useReducer(counterReducer, { count: 0 });

        return (
          <div>
            <p>Count: {state.count}</p>
            <button onClick={() => dispatch({ type: 'increment' })}>+</button>
            <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
          </div>
        );
      }
      ```

#### useCallback

* 메모이제이션된 콜백 함수를 반환

{% hint style="info" %}
메모이제이션(Memoization)

컴퓨터 프로그래밍에서 함수의 호출 결과를 저장해두었다가, 같은 입력으로 함수가 다시 호출될 때 이전에 저장해둔 결과를 반환하여 함수의 실행 시간을 단축하는 기법
{% endhint %}

* 특정 의존성이 변경되었을 때에만 콜백 함수를 다시 생성하도록 할 수 있음
*   성능 최적화를 위해 사용되며, 특히 컴포넌트가 리렌더링 될 때마다 콜백 함수가 새로 생성되는 것을 방지

    성능 최적화가 필요한 대규모 애플리케이션 또는 렌더링 성능에 민감한 컴포넌트에서 유용

    ```javascript
    import React, { useCallback, memo } from 'react';

    const ChildComponent = memo(({ onClick }) => {
      console.log('ChildComponent rendered');
      return <button onClick={onClick}>Click me</button>;
    });

    function ParentComponent() {
      const handleClick = useCallback(() => {
        console.log('Button clicked');
      }, []);

      return <ChildComponent onClick={handleClick} />;
    }
    ```
* 의존성 배열을 올바르게 설정해야 함.&#x20;
* 의존성 배열에 빠진 값이 있다면, 콜백 함수 내에서 사용하는 값이 변경되었을 때 콜백 함수가 업데이트되지 않아 버그가 발생할 수 있음.
* 필요한 값을 의존성 배열에 포함시킨다면, 콜백 함수가 불필요하게 재생성되어 성능에 영향을 미칠 수 있음.
