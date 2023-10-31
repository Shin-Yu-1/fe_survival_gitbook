---
description: 어디로 가야 하죠?
---

# Navigation

#### Web APIs - History

* History 인터페이스는 사용자의 브라우저 세션의 브라우징 기록을 다루는 방법을 제공함.
* window.history 객체를 통해 접근함.
*   페이지 뒤로가기, 앞으로 가기, 특정 페이지로 이동하는 기능을 조작할 수 있음.

    ```javascript
    // 현재 기록에 상태 추가
    history.pushState({ page: 1 }, "title 1", "?page=1");

    // 상태 교체
    history.replaceState({ page: 2 }, "title 2", "?page=2");

    // 이전 페이지로 이동
    history.back();

    // 다음 페이지로 이동
    history.forward();

    // 현재 기록의 상태 객체 출력
    console.log(history.state);
    ```

#### React Router - NavLink, Link, Navigate, useNavigate

* #### Link
  * 페이지를 리로드하지 않고 애플리케이션 내에서의 네비게이션을 가능하게 함.
  * `a` 태그와 비슷하지만, `a` 태그는 페이지를 새로 불러오면서 네비게이션하는 반면, `Link`는 클라이언트 사이드에서 라우팅을 처리
* #### NavLink
  * Link와 유사하지만, 현재 경로와 일치할 때 스타일이나 클래스를 적용할 수 있는 기능이 추가된 컴포넌트
  * 메뉴나 탭에서 현재 활성화된 항목을 표시할 때 사용
* #### Navigate
  * 컴포넌트를 렌더링할 때 특정 경로로 리디렉션을 수행
  * 로그인 페이지로 리디렉션하거나, 404 페이지로 리디렉션할 때 사용
* #### useNavigate
  * 함수형 컴포넌트에서 프로그래매틱 네비게이션을 수행할 수 있게 해주는 훅
  * 폼 제출 후 결과 페이지로 이동, 사용자 인터랙션에 의해 동적으로 경로를 변경하고 싶을 때 사용
