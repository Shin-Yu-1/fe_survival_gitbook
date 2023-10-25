# useRef & Custom Hook

#### useRef

* DOM 요소에 직접 접근하거나, 값의 변경이 있어도 렌더링을 발생시키지 않는 변수를 저장하기 위해 사용
* useRef .current속성을 가지고 있어, 이를 통해 현재의 참조 값을 가져오거나 설정할 수 있음
* 저장된 값은 변경이 있어도 컴포넌트의 리렌더링을 발생시키지 않음.

```javascript
import React, { useRef, useEffect } from 'react';

function App() {
  const inputRef = useRef(null);

  useEffect(() => {
    // 컴포넌트가 마운트되었을 때 input 요소에 포커스 설정
    inputRef.current.focus();
  }, []);

  return <input ref={inputRef} />;
}
```

#### Hook의 규칙

* 최상위에서만 호출해야 함
  * React가 Hooks 호출되는 순서를 기억하여 상태와 생명주기 기능을 올바르게 적용할 수 있도록 함.
* 함수 컴포넌트와 사용자 정의 Hook에서만 Hooks 호출
  * JavaScript 함수에서 호출하면 안 됨.
* 사용자 정의 Hook 네이밍 규칙
  * 사용자 정의 Hook은 'use'로 시작하는 이름이어야 함.
  * React가 사용자 정의 Hook을 인식하고, 해당 함수 내에서 Hook의 규칙을 따르는지 확인할 수 있도록 도와줌.
