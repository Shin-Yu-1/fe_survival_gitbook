---
description: 컴포넌트의 스타일을 동적으로 관리하는 데 사용
---

# props와 attrs

#### props

* React 컴포넌트로 전달되는 데이터를 의미
* 스타일을 동적으로 정의할 때 사용
* 컴포넌트의 외부 상태나 속성에 따라 스타일을 변경하므로, 컴포넌트의 재사용성과 유연성이 증가
* 예시

```javascript
const Button = styled.button`
  color: ${props => props.primary ? 'white' : 'palevioletred'};
  background: ${props => props.primary ? 'palevioletred' : 'white'};
`;
```

#### attrs

* styled-components와 같은 CSS-in-JS 라이브러리에서 사용되는 기능으로, 컴포넌트에 고정적인 HTML 속성을 추가하는 데 사용
* 모든 인스턴스에 걸쳐 고정된 속성을 갖는 스타일 컴포넌트를 생성할 수 있음
* HTML 속성 외에도 추가적인 데이터를 컴포넌트에 주입하는 데 사용될 수 있음
*   예시

    ```javascript
    const Input = styled.input.attrs(props => ({
      type: 'text',
      size: props.size || '1em',
    }))`
      border: 1px solid;
      margin: ${props => props.size};
      padding: ${props => props.size};
    `;

    ```
