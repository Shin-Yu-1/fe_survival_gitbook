# React의 Hook

#### React Hook 이란

* React 16.8 버전부터 도입된 새로운 기능
* 클래스 컴포넌트를 사용하지 않고도 상태 관리 및 라이프사이클 기능을 함수 컴포넌트 내에서 사용할 수 있음.

#### Hooks

*   useState

    * 컴포넌트 상태 관리

    ```javascript
    const [state, setState] = useState(initialState);
    ```
*   useEffect

    * 컴포넌트의 라이프사이클을 다루며, 부수 효과(side effects)를 실행
    * 빈 종속성 배열을 사용하게 되면 마운트될 때 한 번만 수행
    * 두 번째 인자로 제공되는 배열은 의존성 배열(dependency array)로 빈 배열일 때는 마운트 될 때 한 번 수행하고, 특정 값들을 포함하는 배열일 경우 특정 값이 변할 때 마다 수행하고, 아무런 배열을 주지 않을 땐 컴포넌트가 렌더링 돌 때마다 수행함
    * 클린업 작업을 할 때 사용할 수 있음.useEffect(() => {

    ```javascript
      fetch('/api/data')
        .then(response => response.json())
        .then(data => setData(data));
    }, []); // 두 번째 인자에는 배열을 안 주거나, [](빈 배열), [value1, value2](특정 값)을 줄 수 있다.
    ```
*   useContext

    * React Context를 사용하여 컴포넌트 트리에서 전역적인 값에 접근

    ```javascript
    const value = useContext(MyContext);
    ```
*   useRef

    * ref( reference,참조)객체를 반환하며, DOM 접근 뿐만 아니라 일반적인 변수를 저장하고 유지하는 데 사용 수 있음.
    * ref는 current라는 프로퍼티를 가지며, 이 프로퍼티에는 변경 가능한 객체를 반환하며, 이 객체는 라이프사이클 동안 유지됨.
    * 값을 보존하는 동안 컴포넌트의 재렌더링을 발생시키지 않는 방법을 제공하기 때문에 특정한 경우 매우 유용하게 쓰임.

    ```javascript
    const myInputRef = useRef(null);

    function focusOnInput() {
      myInputRef.current.focus();
    }

    return <input ref={myInputRef} />;

    const timerID = useRef(null);

    useEffect(() => {
      timerID.current = setInterval(() => {
        console.log('Tick!');
      }, 1000);

      return () => {
        clearInterval(timerID.current);
      };
    }, []);
    ```
*   useLayoutEffect

    * DOM의 변경 후, 화면에 렌더링이 반영되기 전에 동기적으로 실행되는 효과를 생성함.
    * useEffect와 유사하지만 타이밍이 다름

    ```javascript
    const [state, setState] = useState(initialState);

      // 코드 작성
    }, [dependencies]);
    ```

#### React StrictMode 란

* React 애플리케이션의 잠재적인 문제점을 찾아내기 위한 도구
* 개발 모드에서 더 엄격하게 검사하여 부적절한 패턴을 발견하고 경고 제공

```javascript
import React from 'react';

function App() {
  return (
    <React.StrictMode>
      <ChildComponenet />
    </React.StrictMode>
  );
}
```

