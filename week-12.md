# Week 12



#### Reducer

* 애플리케이션의 상태와 상태를 변화시키는 액션을 인자로 받아, 새로운 상태를 반환하는 순수 함수
* 특징
  * 순수 함수 : R동일한 인자에 대해 항상 동일한 결과를 반환하고, 외부 상태를 변경하거나 부작용을 일으키지 않음.
  * 상태 변화 : 액션 객체는 일반적으로 type 필드를 포함하며, 이는 어떤 종류의 업데이트를 수행할지 나타내고, 이 정보를 사용해 새로운 상태를 계산함.
  * 불변성 유지 : 상태의 복사본을 만들어 변경사항을 적용하고 새로운 상태를 반환함.
*   코드 예시

    ```javascript
    ‌function counterReducer(state = 0, action) {
      switch (action.type) {
        case 'INCREMENT':
          return state + 1;
        case 'DECREMENT':
          return state - 1;
        default:
          return state;
      }
    }
    ```

