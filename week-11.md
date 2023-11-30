# Week 11

#### [Fiber](https://github.com/acdlite/react-fiber-architecture)란?

####

&#x20;React v16에서 더 나은 성능 특히 더 나은 애니메이션, 레이아웃, 제스처 처리를 목표로 개발되었음.&#x20;



React 최적화 전략의 핵심은 기존 state가 다음 state와 바라보는 주소값이 같을 경우 리렌더링을 건너뜀.&#x20;



상태는 불변성(Immutability)을 유지해야 함.&#x20;

기존 객체와 새로운 객체가 동일한 객체인지 비교할 수 있음.&#x20;

이를 위해 개존 객체가 아닌 새로운 객체를 생성해야 함.(setter function)
