# Ref

### Ref란
- DOM 요소에 직접 접근한다.
- 클래스형 컴포넌트 : `React.createRef`
- 함수형 컴포넌트 : `useRef`(Hook함수)

### useRef()를 이용한 DOM요소를 가르키는 방법
1. `useRef()`를 사용해 Ref 객체를 생성한다.
2. 선택할 DOM요소의 `ref` 값에 생성한 객체를 설정한다.
3. `.current`를 이용하여 선택한 DOM요소를 가르킨다.

### 메소드 종류
- `focus()` : 요소에 포커스를 준다.
- `blur()` : 요소에 포커스를 제거한다.
- `click()` : 요소를 클릭한 것 처럼 동작한다.
- `scrollIntoView()` : 요소가 보이도록 화면을 조정(스크롤)한다.
- `setAttribute()` : 요소에 속성을 준다.
- `classList.add()` : 요소에 클래스를 추가한다.
- `classList.remove()` : 요소에서 클래스를 제거한다.

### useRef()를 이용한 컴포넌트 속 변수 관리
- 조회 및 수정 할 수 있는 변수를 관리한다.
  - `.current`를 이용하여 수정, 조회한다.
- 변수의 값이 바뀌어도 컴포넌트가 리렌더링 되지 않는다.
- 관리할 수 있는 값
  - setTimeout, setInterval 을 통해서 만들어진 id
  - 외부 라이브러리를 사용하여 생성된 인스턴스
  - scroll 위치