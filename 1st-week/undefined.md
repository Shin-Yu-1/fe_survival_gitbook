---
description: 대응할 수 있는 능력 키우기
---

# 환경 설정

#### Node.js

* 버전이 다양하므로 버전 관리 도구를 사용하는 것이 좋음.  버전 관리 도구에는  nvm, fnm이 있음. fnm이 빠름.
* LTS(Long Term Support, 장기 지원 버전) / Current로 나뉘는데 LTS는 말 그대로 장기 지원버전으로 안정적이라는 장점이 있음. Current는 현재 개발하는 최신 기능을 가졌다는 장점이 있으나, 일부 기능이 작동되지 않는 버그가 발생할 수 있으므로 되도록이면 LTS 사용하는 것을 권장함.

#### npm

* package.json / package-lock.json
  * package.json :&#x20;
    * 현재 프로그램에 대한 정보와 의존성을 관리하는 파일임.&#x20;
    * npm package를 받고 있을 때 수정하면 충돌로 인해 error 발생 할 수 있음
  * package-lock.json&#x20;
    * npm package를 받으면 자동으로 생성됨,
    * 파일이 생성되는 시점의 의존성 트리에 대한 정확한 정보를 가지고 있음.
* node\_modules
  * npm으로 외부 모듈 패키지를 설치할 때 생기는 폴더
* npx
  * Node Package eXecute의 약자
  * npm 패키지를 설치하지 않고 사용할 수 있게 해주는 도구

#### ES Modules vs CommonJS

* CommonJS
  * 내보내기 : module.exports, default exports / 가져오기 : require()
  * 초기 Node 버전부터 사용함
  * require()는 동기로 작동되기 때문에 promise나 callback 호출을 리턴하지 않음. 또한 require()를 읽는 즉시 실행하게 됨.
* ES Modules
  * 내보내기 : export / 가져오기 : import
  * package.json에 “type”: “module” 설정 필요
  * import는 비동기 환경에서 실행됨. 가져온 script를 바로 실행하지 않고 import, export를 파싱하고, 의존하고 있는 script까지 받아와 실행될 준비를 함. 실행 준비가 완전히 끝나야만 실행됨.
