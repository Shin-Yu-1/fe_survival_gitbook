---
description: https://react-ko.dev/learn
---

# Week 9

#### 컴포넌트를 만들고 중첩하는 방법

* React 컴포넌트는 마크업을 반환하는 JavaScript 함수임.
*   React 컴포넌트 이름은 항상 대문자로 시작해야 하고 HTML 태그는 소문자로 시작해야 함.

    ```typescript
    function MyButton() {
      return (
        <button>I'm a button</button>
      );
    }

    export default function App() {
      return (
        <div>
          <h1>click the button</h1>
          <MyButton />
        </div>
      );
    }
    ```
* Naming Rules
  *   default export의 경우,

      `import`시에 대문자로 시작하는 새로운 이름을 부여
  * `named export`의 경우,
    * `import`시에 `as`로 대문자로 시작하는 새로운 이름을 부여
    * 컴포넌트 **외부**에서 대문자로 시작하는 새로운 변수에 할당
    * 컴포넌트 **내부**에서 대문자로 시작하는 새로운 변수에 할당

#### 마크업 및 스타일을 추가하는 방법

*   태그를 사용하고 끝엔 태그를 닫아야 함.

    예) \<br />
*   여러 개의 JSX 태그를 반환할 수 없음. 하나의 공유 부모로 감싸야 함

    예) \<div>\<h1>Hi!\</h1>\<p>TEST\</p>\</div>
*   `className`으로 CSS 클래스를 지정

    예) \<div className="my-class"> ... 생략 ... \</div>

#### 데이터를 표시하는 방법

*   중괄호를 사용하여 변수를 삽입

    <pre class="language-javascript"><code class="lang-javascript"><strong>return (
    </strong>  &#x3C;p>
        {data}
      &#x3C;/p>
    );
    </code></pre>

#### 조건 및 목록을 렌더링하는 방법

* 조건 렌더링
  *   if / :?(3항 연산자) / &&

      <pre class="language-javascript"><code class="lang-javascript"><strong>// if
      </strong><strong>let content;
      </strong>if (isConnected) {
        content = &#x3C;SuccessContent />;
      } else {
        content = &#x3C;Failcontent />;
      }
      return (
        &#x3C;div>
          {content}
      <strong>  &#x3C;/div>
      </strong>);

      // 3항 연산자
      return (
        &#x3C;div>
          {isConnected ? (
            &#x3C;SuccessContent />
          ) : (
             &#x3C;Failcontent />
          )}
        &#x3C;/div>
      );

      // And 연산자
      &#x3C;div>
        {isConnected &#x26;&#x26; &#x3C;SuccessContent />}
      &#x3C;/div>
      </code></pre>
  *   목록 렌더링

      *   key를 필히 넣어야 함. 각 항목에 대해, 형제 항목 중에서 해당 항목을 고유한 값의 문자열 혹은 숫자여야 함.

          key는 React가 리스트의 수정, 추가, 삭제 등 변화를  알기 위해 사용함.

      ```javascript
      const scores = [
        { subject: 'Math', score: 2 },
        { subject: 'English', score: 5  },
        { subject: 'Korean', score: 8 },
      ];


      const listItems = scores.map(item =>
        <li key={item.subject}>
          {item.score}
        </li>
      );

      return (
        <ul>{listItems}</ul>
      );
      ```

#### 이벤트에 응답하고 화면을 업데이트하는 방법

*   이벤트 핸들러 함수를 선언하여 이벤트에 응답할 수 있음. 단, 함수를 호출을 하는 것이 아닌 참조를 해야 함.

    호출은 버튼을 클릭하거나 input에 값이 입력되는 등의 이벤트가 발생 시 함수가 호출됨.

    ```javascript
    export default function App() {
      function handleClick() {
        console.log("Good")
      }
      
      return (
        <div>
          <button onClick={handleClick} >Click Me</button>
        </div>
      );
    }
    ```
*   컴포넌트에 _state_를 추가하면 특정 정보를 기억하게 할 수 있음.

    ```javascript
    import { useState } from 'react';

    function IncreaseButton() {
      const [count, setCount] = useState(0);
      
      function handleClick() {
        setCount(count + 1);
      }

      return (
        <button onClick={handleClick}>
          Clicked {count} times
        </button>
      );
    }
    ```

#### 컴포넌트 간에 데이터를 공유하는 방법

* state 끌어올리기(Lifting State Up)
  * state를 끌어올리면 컴포넌트 간에 공유할 수 있음.
  *   두 개 이상의 자식 컴포넌트가 같은 state를 공유해야 할 때 적용함.

      state를 각각의 자식 컴포넌트에 두는 대신, 공통 부모 컴포넌트에 위치시킴.
  * 공통 부모 컴포넌트는 상태를 관리하며, 필요한 자식 컴포넌트들에게 state를 props로 전달함. 이로 인해 상태 관리가 중앙집중화 되고, 데이터 흐름이 명확해짐.
  *   자식은 전달받은 props를 사용하여 UI 렌더링 혹은 상호작용을 처리함.

      상태 변경이 필요한 경우, 부모 컴포넌트로부터 전달받은 함수를 통해 state를 업데이트함.
  *   state가 한 곳에서 관리되므로 자식 컴포넌트들 사이의 상태 일관성을 유지하기 쉬움. 모든 자식 컴포넌트는 같은 상태 값을 참조하므로 상태가 변경되면 모든 컴포넌트들이 자동으로 업데이트 됨.

      ```jsx
      // 부모 컴포넌트
      class ParentComponent extends React.Component {
        constructor(props) {
          super(props);
          this.state = { sharedData: '' };

          this.handleDataChange = this.handleDataChange.bind(this);
        }

        handleDataChange(newData) {
          this.setState({ sharedData: newData });
        }

        render() {
          return (
            <div>
              <ChildComponentA
                data={this.state.sharedData}
                onDataChange={this.handleDataChange}
              />
              <ChildComponentB
                data={this.state.sharedData}
              />
            </div>
          );
        }
      }

      // 자식 컴포넌트 A
      function ChildComponentA(props) {
        return (
          <input
            type="text"
            value={props.data}
            onChange={e => props.onDataChange(e.target.value)}
          />
        );
      }

      // 자식 컴포넌트 B
      function ChildComponentB(props) {
        return <div>{props.data}</div>;
      }

      ```
