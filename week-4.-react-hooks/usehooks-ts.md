# usehooks-ts

#### usehooks-ts

* React의 Hooks 패턴을 TypeScript와 함께 사용할 때 도움을 주는 여러 가지 커스텀 Hooks를 제공하는 라이브러리
* useBoolean
  * 불린 상태를 관리하는 Hook
* useEffectOnce
  * React 컴포넌트가 마운트될 때 한 번만 부수 작용(side effect) 실행하도록 함.
  * useEffect 훅을 사용할 때 의존성 배열(dependency array)을 빈 배열로 설정하는 것과 유사함
* useFetch
  * HTTP 요청을 보내고 응답을 처리하는 Hook
* useInterval
  * 정해진 간격으로 함수를 반복적으로 실행
* useEventListener
  * DOM Event를 쉽게 다룰 수 있음.
* useLocalStorage
  * 로컬 스토리지에 값을 저장하고 불러오는 Hook
* useDarkMode
  * &#x20;사용자가 Dark mode를 사용하고 있는지 여부를 감지하고, 상태를 변경할 수 있음.

#### swr

* React Hooks를 사용하여 data fetching, caching, 동기화 및 업데이트를 간편하게 만들어주는 라이브러리
* stale-while-revalidate라는 HTTP 캐시 무효화 전략에서 유래함

#### react-query

* React 애플리케이션에서 서버 상태를 가져오고, 캐시하고, 동기화하고, 업데이트하는데 도움을 주는 라이브러리
* React Query는 데이터를 가져오고, 캐시하는 것을 자동화하여 상태 관리를 더욱 쉽게 만들어줌.
* 데이터를 최신 상태로 유지하는데 필요한 보일러플레이트 코드를 줄여줌
