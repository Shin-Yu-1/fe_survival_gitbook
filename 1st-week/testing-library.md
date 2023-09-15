# Testing Library

#### Jest

* facebook(현 meta)에서 만든 JavaScript testing library.
* 다양한 레벨에서 Mocking 사용 가능
* Mocking : 실제 구현이 없이 시뮬레이션을 할 수 있도록 하는 것. 프론트엔드 웹 애플리케이션이나 모바일 애플리케이션에서 실제 테스트가 아닌 가짜 테스트를 하게 되므로 원하는 기능에 대한 테스트를 진행할 수 있음.

#### Describe-Context-It 패턴

```typescript
function add(x: number, y: number): number {
	return x + y;
}

Test('Add Number', ()=>{
	expect(add(1, 2)).toBe(3) ;
});

describe('Add Function', () => {
	it('returns sum of tow numbers', () => {
		expect(add(1, 2)).toBe(3);
	});
});

```

* Describe: 테스트 대상이나 주제를 정의.
* Context: 특정 조건 또는 상황을 설명. jest에서는 context를 지원하지 않아 describe를 활용함.
* It: 특정 동작이나 예상되는 결과 기술.
* 이를 BDD(Behavior-Driven Development) 스타일이라 함.
  * BDD(Behavior-Driven Development)&#x20;
    * TDD (Test-Driven Development)에 기반을 둔 개발 접근법
    * 시스템의 동작에 초점을 맞춰 요구 사항의 명확한 이해와 그에 따른 테스트 코드 작성.
    * 사람이 읽을 수 있는 언어로 동작을 기술

```typescript
// DBB Style code example - made by chatGPT


// Button.tsx
import React from 'react';

type Props = {
    label: string;
    onClick: () => void;
};

const Button: React.FC<Props> = ({ label, onClick }) => {
    return <button onClick={onClick}>{label}</button>;
};

export default Button;


// Button.test.tsx
import React from 'react';
import { render, screen, fireEvent } from '@testing-library/react';
import Button from './Button';

const context = describe;

describe('Button component', () => {

    context('when it is rendered', () => {

        it('should display the correct label', () => {
            render(<Button label="Click me" onClick={jest.fn()} />);
            expect(screen.getByText('Click me')).toBeInTheDocument();
        });

    });

    context('when clicked', () => {

        it('should call the onClick function', () => {
            const mockOnClick = jest.fn();
            render(<Button label="Click me" onClick={mockOnClick} />);
            
            const buttonElement = screen.getByText('Click me');
            fireEvent.click(buttonElement);

            expect(mockOnClick).toHaveBeenCalled();
        });

    });

});
```

#### React Testing Library

* UI test에 특화된 라이브러리.
* React 구성 요소 작업을 위한 API를 추가하여 그 위에 구축함.
* 주요 목적은 사용자의 관점에서 컴포넌트와 관련된 테스트를 작성하는 것
* F/E Test === Only React Component Test가 되는 상황 ➢ 비용증가 초래



#### 제대로 된 테스트 케이스를 작성하기!

> 테스트 코드가 복잡할 수록 실제 코드를 짜는 시간보다 테스트 케이스를 추가하는 시간이 더 걸리기 십상이다. 실제 코드를 변경해 기존 테스트 케이스가 실패하기 시작하면, 지저분한 코드로 인해, 실패하는 테스트 케이스를 점점 더 통과시키기 어려워진다. 그래서 테스트 코드는 계속해서 늘어나는 부담이 되버린다. (Clean Code p.156)

