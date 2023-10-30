---
description: 환경설정, 마지막 이야기
---

# Parcel & ESLint

### Bundler(번들러)

#### 번들러란, 주로 웹 개발에서 코드와 의존성을 모듈화하고 패키징하는 데 사용되는 도구

Parcel, Vite 등 다양하게 존재함. 취향껏 골라서 쓰면 됨.

#### Parcel

* 특별한 설정 없이 바로 사용 가능한 빌드 도구
* npx parcel build : 빌드 + 정적 서버 실행
* npx servor dist : dist 파일 내 실행



### Lint(린트)

* 스타일 통일
* 잠재적 문제 발견
* 베스트 프랙티스 추천 (잠재적 문제에 대해서 지적해줌) → 최신 트랜드 학습하는데 활용 가능
* 코드에 문법적 오류, 포맷 오류, 스타일 불일치, 잠재적 버그, 비표준 패턴 및 다른 여러 문제점들을 자동으로 탐지

#### ESLint

* 자바스크립트 코드에서 발견되는 문제시되는 패턴들을 식별하기 위한 정적 코드 분석 도구
* VSCode에서 코드를 바꿀 때 마다 자동 반영되도록 설정하면 편-리

```
// .vscode/setting.json

{   
    "editor.rulers": [
        80
    ],
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true 
    },
    "trailing-spaces.trimOnSave": true
}
```

* 위 설정은 전역으로 설정되어 있음. 상세한 설명이 필요할 경우 아래 문서 참고&#x20;

{% embed url="https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint" %}
