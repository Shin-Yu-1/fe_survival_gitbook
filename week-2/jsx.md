---
description: XML같은 문법 확장! 리액트 부산물 같은 존재!
---

# JSX

> JavaScript XML의 약자
>
> JavaScript의 문법 확장

변수, 함수, 조건문, 반복문 등 JavaScript의 기능을 JSX 내에서 직접 사용 가능함.

#### React에서 JSX를 사용하는 목적

* JavaScript와의 통합으로 데이터 처리와 UI 렌더링 로직을 함께 묶을 수 있음.
* 컴포넌트를 HTML 태그처럼 간단하게 사용할 수 있음.
* 직관적이고 선언적인 구문 덕분에, 개발자는 UI의 복잡한 상태 관리보다는 UI 자체와 그에 따른 사용자 경험에 더 집중할 수 있음.

#### Syntactic sugar

* 프로그래밍 문법적인 특성 중 하나
* 언어의 기능성을 변경하지 않으면서 코드를 더 읽기 쉽고 명확하게 만들어 주는 문법적 편의성을 의미함.
* 기본적인 연산이나 표현을 더 간결하고 직관적으로 표현하기 위한 추가적인 문법적 특징이 있음.
* 굳이 사용하지 않아도 기능 구현에는 문제 없음.

#### React.createElement

* React element(요소)를 생성하는 함수
* 화면에 어떤 내용이 보여져야 하는지를 나타냄.
* 실제 DOM 요소로 변환되기 전의 중간 표현(representation)

```
// React.createElement
React.createElement(
  'div', 
  { className: 'my-class' }, 
  'Hello, World!'
)

// JSX
<div className="my-class">Hello, World!</div>
```

#### React Element&#x20;

* React Element tree 갱신하는데에 쓰일 수 있음.
* React 애플리케이션의 가장 작은 구성 단위
* Element들을 사용하여 "virtual DOM"을 구성

#### React StrictMode

* 애플리케이션 또는 개별 컴포넌트의 부분을 더 엄격하게 체크하는 도구
* 개발 모드에서만 보이는 경고와 에러들을 포착하여 애플리케이션의 잠재적인 문제점들을 식별할 수 있음.

