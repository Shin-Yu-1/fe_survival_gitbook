# styled-components

* React 애플리케이션에서 스타일링을 더 효율적이고 직관적으로 관리하기 위해 만들어진 라이브러리
* 컴포넌트 기반의 개발 방식과 CSS-in-JS의 접근 방식을 결합하여, React 컴포넌트의 스타일링을 개선하고자 함.
* JavaScript 파일 내에서 CSS를 작성
* 스타일링된 컴포넌트를 생성하여 애플리케이션 전반에 걸쳐 재사용
* 유연성과 편의성을 제공
* 스타일과 로직을 컴포넌트 단위로 캡슐화
* 특징
  *   컴포넌트 기반 스타일링

      각 스타일이 하나의 컴포넌트와 연결을 통해 컴포넌트 단위로 스타일을 적용하고 관리할 수 있으며, 전역 스타일의 충돌을 방지할 수 있음.
  *   실시간 스타일 변경

      JavaScript의 props 또는 state를 기반으로 스타일을 동적으로 변경

      사용자 상호작용에 따라 스타일을 변경하거나 테마를 적용하는 데 유용함
  *   태그된 템플릿 리터럴

      ES6의 태그된 템플릿 리터럴 문법을 사용하여 CSS 코드 작성할 때 JavaScript 변수나 함수를 쉽게 삽입할 수 있음.
  *   자동 벤더 프리픽스 적용

      브라우저 호환성을 위해 필요한 CSS 벤더 프리픽스(vendor prefixes)를 자동으로 적용함.
  *   서버 사이드 렌더링 지원

      서버 사이드 렌더링과 호환되어 SEO 최적화 및 초기 렌더링 성능 향상에 도움을 줌
*   작성 예시

    ```javascript
    import styled from 'styled-components';

    const StyledButton = styled.button`
      background-color: blue;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;

      &:hover {
        background-color: darkblue;
      }
    `;

    function App() {
      return <StyledButton>Click Me</StyledButton>;
    }
    ```
