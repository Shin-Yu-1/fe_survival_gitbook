---
description: Mock Service Worker는 서버 스팩은 나왔지만 구현이 덜 됐을 때 사용하기 좋음
---

# MSW

#### Service worker

* 웹 브라우저에서 백그라운드에서 실행되는 스크립트임. 웹 페이지와는 별도로 동작함.
* 웹 애플리케이션의 성능 향상, 오프라인 경험 제공, 네트워크 요청 관리, 푸시 알림 및 백그라운드 동기화와 같은 기능을 구현하는 데 사용됨.
* 특징
  * 백그라운드 실행
    * 웹 페이지가 닫혀 있어도 백그라운드에서 실행됨
  * 네트워크 프록시
    * 네트워크 요청을 가로채어 캐싱, 수정 또는 대체 응답 제공
  * 오프라인 지원
    * 오프라인에서도 웹 애플리케이션 사용 가능
  * 이벤트 기반
    * 이벤트 기반으로 작동하며 특정 이벤트에 반응하여 작업을 수행할 수 있음
  * 프로그래밍 방식 캐싱
    * 프로그래밍 방식으로 어떤 리소스를 캐시 할지, 언제 캐시를 업데이트할지 등을 결정할 수 있음.
  * 푸시 알림
    * 웹 애플리케이션이 닫혀 있더라도 사용자에게 푸시 알림을 보낼 수 있음.

#### MSW(Mock Service Worker)

* 브라우저와 Node.js에서 HTTP 요청을 가로채어 모의 응답을 반환하는 라이브러리
* 실제 백엔드 서버에 의존하지 않고도 네트워크 요청을 테스트하고, 개발 과정을 더 효율적으로 만들 수 있음.

#### polyfill(폴리필)

* 오래된 브라우저 또는 지원하지 않는 브라우저에서 최신 JavaScript API나 CSS 기능을 사용할 수 있도록 해주는 코드 조각이나 플러그인을 의미함.
* polyfill을 사용하면 개발자는 최신 기술을 사용하면서도, 이전 버전의 브라우저에서도 웹 애플리케이션이 정상적으로 작동하도록 할 수 있음.