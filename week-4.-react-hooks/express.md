---
description: Front-end라도 Back-End를 알아야 한다!
---

# Express

#### Express 란

* Node.js 웹 애플리케이션 프레임워크
* API 서버, 네트워크 소프트웨어 개발 시 유용함.
* 개발 속도와 생산성을 향상시킬 수 있음

#### URL 구조

* URL(Uniform Resource Locator)은 인터넷상의 리소스를 찾기위한 주소
* ex) http://localhost:3000/login
* 구성
  * Scheme(스킴)
    * 리소스에 접근하기 위한 프로토콜
    * ex) http, https, ftp 등 / http://
  * Host(호스트)
    * 리소스가 호스팅되어 있는 서버의 도메인 이름 또는 IP 주소
    * ex) www.google.com, 0.0.0.0, localhost 등
  * Port(포트)
    * 서버상 특정 포트 지정하여 사용
    * ex) :8080 등
  * Path(경로)
    * 서버에서 리소스의 위치
    * ex) /ko/pages1

#### REST API

* REST API (Representational State Transfer Application Programming Interface)는 웹 서비스를 구축하기 위한 아키텍처 스타일
* Client - Server Architecture 기반으로, 상태가 없고 캐시 가능한 커뮤니케이션 지원
* HTTP Protocol 사용 및 HTTP Method(GET, POST, PUT, DELETE 등)을 통해 리소스에 대한 작업 수행

#### HTTP Method(CRUD)

* Ceate, Read, Update, Delete를 위한 메소드
* 각 메소드는 RESTful 서비스에서 적절한 상황에서 올바르게 사용해야 함.
* GET
  * 리소스를 조회하거나 검색하기 위해 사용
  * 서버에 데이터를 변경하지 않고 단순히 정보를 요청함
* POST
  * 새로운 리소스를 생성하거나 데이터를 서버에 제출하기 위해 사용
* PUT
  * 기존 리소스를 완전히 업데이트하거나 존재하지 않는 경우 새 리소스 생성하기 위해 사용
* PATCH
  * 기존 리소스의 일부만 업데이트하기 위해 사용
* DELETE
  * 리소스를 삭제하기 위해 사용
* HEAD
  * 응답 본문 없이 HTTP 헤더 정보만을 반환함.
* OPTIONS
  * 대상 리소스의 통신 옵션을 설명하기 위해 사용
  * 서버가 지원하는 HTTP Method를 확인하는데 사용
* TRACE
  * 서버에 메시지를 보내고, 서버가 받은 메세지를 다시 클라이언트로 돌려보내는 에코 서비스
