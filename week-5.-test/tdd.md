---
description: TDD
---

# TDD

#### TDD란

* Test-Driven Development는 소프트웨어 개발 프로세스의 한 형태로, 개발자가 실제 코드를 작성하기 전 테스트 케이스를 먼저 작성하는 방법론임.
* 대규모 프로젝트나 복잡한 시스템에서 코드의 품질을 유지하고 버그를 줄이는 데 매우 효과적인 방법론
* 과정
  * 실패하는 테스트 작성
  * 테스트를 통과하는 최소한의 코드 작성
  * 리팩토링
  * 반복
* 주요 이점
  * 버그감소
  * 코드 품질 향상
  * 문서화의 역할
  * 디자인 개선
  * 유지보수 용이
* 단점
  * 초기 개발 속도가 느려질 수 있음
  * 학습하고 효율적으로 사용하기까지 시간이 걸릴 수 있음

#### Jest

* Facebook에 의해 개발된 JavaScript 테스팅 프레임워크
* 유닛 테스팅, 통합 테스팅, 엔드-투-엔드 테스팅 지원

#### Describe - Context - It 패턴

* 테스트 코드를 구조화하고 읽기 쉽게 만드는데 사용되는 패턴
* Describe
  * 테스트를 그룹화하는 데 사용
  * 관련 있는 테스트 케이스들을 한 덩어리로 묶어서 관리함.
  * 테스트 코드의 구조를 명확하게 하고 가독성을 높임
  * describe 블록 안에는 다른 describe, context, it 블록이 들어갈 수 있음.
* Context
  * 테스트 케이스의 특정 상황이나 조건을 설명할 때 사용
  * describe와 context는 기능적으로는 차이가 없음. 의미적으로 context를 사용하면 테스트 상황에 따른 조건을 더 명확히 설명할 수 있음.
* It
  * 개별 테스트 케이스를 정의하는 데 사용
  * 실제 테스트 로직이 들어감. 이 안에서 검증(assertion)을 수행함.

```javascript
describe('Array', () => {
  context('when it has elements', () => {
    it('should return the number of elements', () => {
      const array = [1, 2, 3];
      const length = array.length;
      expect(length).to.equal(3);
    });
  });

  context('when it is empty', () => {
    it('should return 0 as the number of elements', () => {
      const array = [];
      const length = array.length;
      expect(length).to.equal(0);
    });
  });
});
```

#### 단위테스트란

* 단위 테스트(Unit Test)는 소프트웨어 개발 과정에서 코드의 특정 부분이 의도한 대로 작동하는지 검증하는 테스트 방법
* 여기서 단위란 함수, 메서드, 프로시저, 모듈 또는 객체와같은 소프트웨어의 가장 작은 부분을 의미하며, 각 단위가 예상대로 작동하는지 확인하기 위해 독립적으로 테스트함.
* 개발 초기 단계에서 시작하여 지속적으로 수행되며, 소프트웨어의 안정성을 유지하는 데 중요한 역할을 함.
* 목적
  * 버그 조기 발견
  * 안정성 보장
  * 설계 개선
  * 개발 속도 향상
  * 문서화 역할
* 특징
  * 자동화
  * 독립성
  * 반복 가능
  * 빠른 실행 속도
* 장점
  * 코드의 안정성과 신뢰성 향상
  * 버그 조기 발견 및 수정
  * 리팩토링과 코드 변경의 용이성
  * 개발 프로세스의 속도 향상
  * 새로운 기능 추가나 코드 변경 시 기존 기능이 올바르게 작동하는지 검증하는 데 도움
