---
description: React Router v6부터는 RouterProvider 컴포넌트를 사용하여 라우터를 설정할 수 있음.
---

# Router

#### ReactRouter - RouterProvider

* 애플리케이션의 라우팅 상태를 관리하고, React 컴포넌트 트리에 라우터의 컨텍스트를 제공
* 하위 컴포넌트들에게 라우터의 상태와 기능을 전달하므로, 이를 사용하여 다양한 라우팅 관련 작업을 수행함.
*   BrowserRouter 또는 MemoryRouter와 같이 특정 라우터 구현과 함께 사용됨.

    ```javascript
    import React from 'react';
    import { createBrowserRouter, RouterProvider, Route } from 'react-router-dom';

    function Home() {
      return (
        <h1>Home Page</h1>;
      )
    }

    function About() {
      return (
        <h1>About Page</h1>;
      )
    }

    const router = createBrowserRouter([
      { path: '/', element: <Home /> },
      { path: '/about', element: <About />, },
    ]);

    function App() {
      return <RouterProvider router={router} />;
    }

    export default App;
    ```
