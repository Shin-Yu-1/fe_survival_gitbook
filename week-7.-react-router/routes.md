---
description: npm i react-router-dom 입력하여 설치하기
---

# Routes

#### 라우터란?

* 웹 애플리케이션에서 클라이언트 측 라우팅을 구현하는데 사용되는 표준 라이브러리
* 사용자의 URL 변경에 따라 다양한 컴포넌트를 렌더링함.

#### React Router

React 애플리케이션에서 페이지 라우팅을 구현하기 위한 라이브러리

사용자가 다른 주소로 이동했을 때, 새로고침 없이도 적절한 컴포넌트를 렌더링할 수 있음.

* Browser Router
  *   HTML5 히스토리 API를 사용하여 URL을 동기화하는 라우터 컴포넌트

      ```javascript
      // main.tsx

      import ReactDOM from 'react-dom/client';
      import React from 'react';

      import { BrowserRouter } from 'react-router-dom';

      import App from './App';

      function main() {
        const container = document.getElementById('root');
        if (!container) {
          return;
        }

        const root = ReactDOM.createRoot(container);
        root.render((
          <React.StrictMode>
            <BrowserRouter>
              <App />
            </BrowserRouter>
          </React.StrictMode>
        ));
      }

      main();
      ```

      * `App` 컴포넌트 내부에서 `Route`, `Link`, `Switch` 등 React Router의 다른 컴포넌트들을 사용하여 라우팅을 구성할 수 있음.


*   Route

    * 특정 경로와 매치될 때 렌더링할 컴포넌트를 정의
    * 현재 URL에 따라 다른 컴포넌트를 렌더링함.


* Memory Router
  * 테스팅이나 서버 사이드 렌더링 환경에서 사용
  *   브라우저의 주소 표시줄을 변경하지 않고, URL 상태를 메모리에 유지하여 사용자의 브라우저 히스토리에 영향을 주지 않으면서, 라우팅 상태의 변경과 관련된 로직을 테스트하거나 실행할 수 있음.

      ```javascript
      // App.test.tsx

      import { render, screen } from '@testing-library/react';
      import { MemoryRouter } from 'react-router-dom';

      import App from './App';

      const context = describe;

      describe('App', () => {
        context('renders home page by default', () => {
          it('home page', () => {
            render((
              <MemoryRouter initialEntries={['/']}>
                <App />
              </MemoryRouter>
            ));
            
            screen.getByText(/Welcome/i);
          });
        });
        
        context('renders about page when route is /about', () => {
          it('home page', () => {
            render((
              <MemoryRouter initialEntries={['/about']}>
                <App />
              </MemoryRouter>
            ));
            
            screen.getByText(/Welcome/i);
            });
        });
      });
      ```

