---
description: 웹 애플리케이션에서 사용자의 요청(URL)을 특정 엔드포인트나 컴포넌트와 연결하는 과정
---

# Routing

#### HTML DOM API

HTML DOM (Document Object Model) API란, 웹 브라우저가 HTML 문서를 조작하고 상호 작용하는 방법을 제공하는 프로그래밍 인터페이스임.

*   Location

    ```javascript
    window.location

    // ex) https://fe-servival.gitbook.io/megatera/ 
    // => Location {ancestorOrigins: DOMStringList, href: 'https://fe-servival.gitbook.io/megatera/', origin: 'https://fe-servival.gitbook.io', protocol: 'https:', host: 'fe-servival.gitbook.io', …} 출력됨
    ```

    * 현재 문서의 URL을 나타내고, 현재 문서와 관련된 다양한 작업을 수행할 수 있는 방법을 제공하는 객체임.
    * 페이지를 리다이렉트하거나, URL의 구성 요소에 접근하거나, 새로고침하는 등의 작업을 수행함.
*   pathname

    ```javascript
    window.location.pathname
    // ex) https://fe-servival.gitbook.io/megatera/ => /megatera/' 출력됨
    ```

    * 웹 페이지의 URL에서 도메인 이름 다음에 오는 부분
    * 읽기와 쓰기 모두 가능한 프로퍼티

