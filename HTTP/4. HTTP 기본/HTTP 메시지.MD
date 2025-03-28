# HTTP 메시지

---

## HTTP 메시지 구조

| start-line 시작 라인 |
| --- |
| header 헤더 |
| empty line 공백 라인 (CRLF)  ⇒  무조건 들어가야함 |
| message body |

## HTTP 요청 메시지

| GET/search?q=hello&hl=ko HTTP/1. |
| --- |
| HOST:www.google.com |
| (공백 - 필수) |
| (body 본문 - 필요시) |

## HTTP 응답 메시지

| HTTP/1.1 200 OK |
| --- |
| Content-Type: text/html;charset=UTF-8
Content-Length: 3423 |
| (공백 - 필수) |
| <html>
    <body>…</body>
</html> |
- 공식 스팩
    
    ```python
    start-line
    *( header-field CRLF )
    CRLF
    [ message-body ]
    ```
    

---

## 시작 라인

### **start-line = request-line / status-line**

### <request-line>

⇒ `method SP(공백) request-target SP HTTP-version CRLF(엔터)`

1. HTTP 메서드
    - 종류 : GET, POST, PUT, DELETE…등
    - 서버가 수행해야 할 동작 지정
        - GET : 리소스 조회
        - POST : 요청 내역 처리
        - PUT
        - DELETE : 삭제
2. Request-target (요청 대상)  (/search?q=hello&hl=ko)
    - absolute-path[?query]  (절대 경로[?쿼리])
    절대경로 : “/”로 시작하는 경로
    - 다른 유형의 경로 지정 방법도 있음
3. HTTP Version

### <status-line>

⇒ `HTTP-version SP status-code SP reason-phrase CRLF`

1. HTTP 버전
2. HTTP 상태 코드 : 요청 성공, 실패를 나타냄
    - 200 : 성공
    - 400 : 클라이언트 요청 오류
    - 500 : 서버 내부 오류(장애)
3. 이유 문구 : 사람이 이해할 수 있는 짧은 상태 코드 설명 글

---

## HTTP 헤더

### header-field = field-name“:” OWS field-value OWS

- OWS : 띄어쓰기 허용
- field-name 뒤에 “:” 무조건 붙여서
- field-name은 대소문자 구분 X
- field-value는 대소문자 구분 O

- HTTP 헤더의 용도
    - HTTP 전송에 필요한 모든 부가정보가 다 들어있음
        - 예) 메시지 바디의 내용/크기, 압축, 인증, 요청 클라이언트(브라우저) 정보, 서버 애플리케이션 정보, 캐시 관리 정보 등…
        메시지 바디 빼고 필요한 메타 데이터는 다 들어있음
    - 표준 헤더가 너무 많음
    - 필요시 임의의 헤더 추가 가능

---

## HTTP 메시지 Body

- 용도
    - 실제 전송할 데이터
    - HTML 문서, 이미지 영상 JSON 등등
    byte로 표현 할 수 있는 모든 데이터 전송 가능

---

## 단순함 확장 가능

- HTTP는 단순하다
- HTTP 메시지도 매우 단순
- 크게 성공하는 표준 기술을 단순하지만 확장 가능한 기술