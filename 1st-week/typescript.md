---
description: 왜 써요? VSCode에서 매우 편함
---

# Typescript

:thumbsup:

#### REPL

* Read-Eval(Evalution)-Print-Loop의 약자
* 코드를 입력하면 즉석에서 그 코드를 평가하고 코드의 실행결과를 출력해주는 것을 반복해주는 환경

###

### TypeScript

#### Interface vs Type

* Type Alias와 Interface는 서로 기능이 비슷하지만 다름.
* Interface :&#x20;
  * 동일한 이름으로 여러 번 선언해도 컴파일 시점에 합칠 수 있음. 이를 선언 병합이라 함.
  * 상호 간에 정의한 약속 혹은 규칙을 의미함. type 체크를 위해 사용
  * 인터페이스로 선언된 프로퍼티 또는 메소드 구현을 강제하여 일관성 유지 가능
  * 개방-폐쇄 원칙에 따라 확장이 열려있는 JavaScript 객체 동작 방식과 비슷하게 연결되도록 설계됨.
* Type :
  * 선언 병합 불가능
  * 새로운 유형을 정의하는 것이 아닌 기존 유형에 대한 대체 이름을 제공함. 기본 유형을 포함하여 유효한 유형을 참조하는 키워드 사용을 통해 만들 수 있음. 이를 통해 확장 Interface와 비슷하게 확장가능하게 됨.
  * 값을 담아두기 위해 사용

#### 타입 추론

* 타입을 지정하지 않고 처음 입력된 값의 타입을 추정하여 정하게 됨.

#### Union Type vs Intersection Type

* Union Type
  * OR 연산자(||) 의미의 타입.
  * function test(txt: string | number) { ... } 에서 txt 매개변수는 Union type으로 문자열 또는 숫자 타입이므로 두 가지 타입 모두 사용 가능함,
* Intersection Type
  * AND 연산자(&) 의미의 타입.
  * type Person = Birth & Name; 에서 Birth와 Name 타입 정의를 & 연산자를 이용하여 합친 것으로 모두 만족해야 함.
  * 집합에서 합집합(∪)과 같음

#### Optional Parameter

* parameter가 있는 함수에 아무런 값도 전달하지 않고 호출할 경우 undefined값이 나오는데, 다른 값이 자동으로 전달되도록 기본값을 설정할 수 있음. 이렇게 파라미터 값을 선택적으로 전달 받는 것을 Optional parameter라고 함.

