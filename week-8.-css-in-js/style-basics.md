# Style Basics

#### className

* HTML 요소에 CSS 클래스를 지정하는 데 사용되는 속성
* JavaScript에서 class가 예약어이기 때문에 일반 HTML에서 class 속성 대신 className 속성을 사용
* className 속성은 해당 HTML 요소에 스타일을 적용하기 위해 사용
* HTML 요소에 다양한 스타일을 적용하고, 이를 통해 웹 페이지의 시각적 요소를 조정할 수 있음.React 컴포넌트를 정의
*   React 컴포넌트를 정의

    ```javascript
    import React from 'react';

    export default function Button({ label }) {
        return (
            <button className="custom-button">
                {label}
            </button>
        );
    }
    ```
*   CSS 정의

    ```css
    .custom-button {
        background-color: blue;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 16px;
    }
    ```
*   Button Component 사용

    ```javascript
    import React from 'react';
    import Button from './Button'; // Button 컴포넌트를 임포트합니다.

    function App() {
        return (
            <div>
                <Button label="Click Me" />
            </div>
        );
    }

    export default App;
    ```

####

#### 의미있는 마크업

* 의미있는 마크업(Meaningful Markup)이란, 웹 페이지의 HTML 구조를 논리적이고 의미론적으로 구성하는 방법을 의미함.
* 목적
  * 웹 콘텐츠가 더 접근성이 좋고, 검색 엔진에 친화적이며, 유지보수하기 쉽도록 만드는 것
* **주요 원칙**
  *   적절한 HTML 태그 사용

      콘텐츠의 의미와 구조에 가장 적합한 태그를 선택하여 사용
  *   접근성 고려

      웹사이트가 다양한 사용자와 장치에 접근 가능하도록 만드는 것
  *   검색 엔진 최적화(SEO)

      검색 엔진이 콘텐츠를 더 잘 이해하고 적절하게 인덱싱할 수 있도록 도와줌.
  *   시맨틱 태그 사용

      페이지의 구조가 더 명확해지고, 코드의 가독성이 높아짐.
  *   코드의 간결성과 명확성 유지

      불필요한 태그나 중복을 피하고, 간결하면서도 의미를 명확하게 전달하도록 작성해야 함.
