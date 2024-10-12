# useEffect
- 마운트, 언마운트가 발생될 때 수행해야할 코드를 실행시킨다.
- 함수를 반환한다. ( 반환하는 함수 : `cleanup`함수 )

### 마운트와 언마운트
  - 마운트 : 컴포넌트가 화면에 나타나는 것
  - 언마운트 : 컴포넌트가 값이 바뀌거나 사라지는 것

### useEffect의 구조
- 첫 번재 매개변수 : 함수
- 두 번재 매개변수 : 배열 ( 매개변수가 되는 배열 : `deps`배열 )
- if. `deps`배열을 생략한다면
  => 컴포넌트가 리렌더링 될 때마다 호출된다.
- if. `deps`배열이 비어있다면
  => 컴포넌트가 처음 나타날때에만 등록한 함수가 호출된다.

### deps 배열
- **규칙**
  - useEffect 안에서 사용하는 상태나, props가 있다면, useEffect의 deps에 넣어야한다.
  ```js
  function HelloName({name}){
    useEffect(() => {
      console.log('이름이 설정됨');
      console.log(name);
      return () => {
        console.log('이름이 바뀌기 전..');
        console.log(name);
      };
    }, [name]);
  }
  ```

### cleanup함수
- 컴포넌트가 언마운트되거나 업데이트되기 전에 수행되는 뒷정리를 한다.
- if. `deps`배열이 비어있다면
  => 컴포넌트가 사라질 때 `cleanup`함수가 호출된다.