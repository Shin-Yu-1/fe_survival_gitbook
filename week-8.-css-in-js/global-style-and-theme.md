# Global Style & Theme

#### Reset CSS

* 브라우저 간의 일관성 없는 기본 스타일링을 초기화하고 표준화하는 데 사용
* 브라우저 간 스타일 차이를 제거하거나 최소화하기 위해 사용
* 특정
  *   브라우저 간 일관성 확보

      여러 브라우저에서 HTML 요소의 기본 스타일링을 통일하여 브라우저 간 일관된 레이아웃과 디자인을 제공
  *   기본 마진과 패딩 제거

      HTML 요소는 기본적으로 일정한 마진과 패딩을 가지고 있으나 기본 마진과 패딩을 제거하거나 재정의하여, 디자이너가 원하는 정확한 레이아웃을 구현할 수 있도록 도와줌.
  *   다른 스타일 시트의 기반

      다른 CSS 스타일을 적용하기 전의 기반으로 사용됨.

      초기화된 상태에서 시작하면 예측 가능한 결과를 얻을 수 있으며, 커스텀 스타일링을 보다 효과적으로 적용할 수 있음.
  *   단순화된 CSS 유지 관리

      브라우저 기본 스타일을 초기화함으로써, 개발자는 더 간결하고 관리하기 쉬운 스타일 시트를 유지할 수 있음.

#### `box-sizing` 속성

* 웹 페이지의 레이아웃을 구성하는 기본적인 요소
* 요소의 크기, 패딩, 테두리, 마진을 포함
* `box-sizing` 속성은 주로 두 가지 값, `content-box`와 `border-box`를 가질 수 있음.

#### `word-break` 속성

* 텍스트가 어떻게 줄바꿈 되어야 하는지를 지정하는 데 사용
* 긴 단어나 문자열이 컨테이너 요소의 경계를 넘어갈 때 어떻게 처리될지를 정의
* 비-라틴 문자나 URL, 긴 코드 문자열 등과 같은 특수한 콘텐츠에 유용함.
* 속성의 주요 값
  *   normal

      기본적인 줄바꿈 규칙을 사용
  *   break-all

      단어의 중간에서도 줄바꿈이 가능

      긴 단어나 URL이 다음 줄로 넘어가지 않고 컨테이너 내에서 강제로 줄바꿈

      아시아 언어에서 유용하며, 라틴 문자에는 적합하지 않을 수 있음.
  *   keep-all

      한국어, 일본어 또는 중국어와 같은 아시아 언어에서 사용할 때 단어를 쪼개지 않고 줄바꿈을 방지

      아시아 언어의 단어가 라틴 문자처럼 공백으로 구분되지 않을 때 유용함.

#### Theme

* 일관된 디자인 요소와 색상 구성을 의미
* 사용자가 시스템 또는 앱의 외관을 개인화할 수 있도록 하는 기능
* 개발 측면에서 테마는 스타일링 관련 정보(색상, 글꼴, 크기 등)를 중앙 집중화하여 관리하는 방법
* 테마는 각각의 맥락에서 중요한 역할을 하며, 웹/앱 디자인에서는 사용자 경험의 일관성과 맞춤 설정을 제공함.

#### ThemeProvider

* styled-components 라이브러리에서 제공하는 기능
* 전체 애플리케이션 또는 그 일부에 걸쳐 테마를 정의하고 사용할 수 있게 해주는 도구
* 애플리케이션의 다양한 컴포넌트에 일관된 스타일링(색상, 글꼴 등)을 적용할 수 있음.
* ThemeProvider는 React의 Context API를 기반으로 하여, 테마에 관한 정보를 애플리케이션의 모든 레벨에서 사용할 수 있음. 이를 통해 개발자는 중앙 집중화된 테마 객체를 정의하고, 이 객체를 사용하여 애플리케이션 전반에 걸쳐 일관된 디자인을 적용함.
* 테마 객체 정의

```javascript
const theme = {
  colors: {
    primary: 'blue',
    secondary: 'green'
  },
  fontSizes: {
    small: '12px',
    medium: '14px',
    large: '16px'
  }
};
```

* ThemeProvider 적용

<pre class="language-javascript"><code class="lang-javascript">import { ThemeProvider } from 'styled-components';
<strong>
</strong><strong>function App() {
</strong><strong> return (
</strong>  Click me); 
}
</code></pre>

* 스타일 컴포넌트에서 테마 사용

```javascript
import styled from 'styled-components';

const Button = styled.button`
  color: ${props => props.theme.colors.primary};
  font-size: ${props => props.theme.fontSizes.large};
`;nts';
```
