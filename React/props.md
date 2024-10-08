# Props

### props란?
- 어떠한 값을 컴포넌트에게 전달해줘야 할 때 사용한다.

### 사용 방법
1. 전달 할 때
  - `<'컴포넌트 이름' '속성명="속성값"' />`

```
<Hello name="react" />
```
<br>

1. 전달 받아 사용할 때
  - 객체 형태의 데이터를 전달 받는다.
  - `{props.속성이름}`

```
function Hello(props) {
  return <div>안녕하세요 {props.name}</div>
}
```

<br>

### 비구조화 할당
- 데이터를 전달 받을 때 사용할 속성만 추출하여 전달 받는다.

```
function Hello({name}) {
  return <div>안녕하세요 {name}</div>
}
```

<br>

### 기본값 설정
- `defaultProps`라는 값을 컴포넌트에 설정하면 props를 지정하지 않았을 때 기본적으로 사용할 값을 설정한다.

```
Hello.defaultProps = {
  name: '기본값'
}
```

<br>

### 컴포넌트 태그 사이 값 조회
- `props.children`을 조회한다.

```
function Hello({children}) {
  return (
    <div>
      {children}
    </div>
  )
}
```