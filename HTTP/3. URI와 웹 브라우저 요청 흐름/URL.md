# URI

---

## URI(Uniform Resource Identifier)

- URI, URL, URN
    - URI는 로케이터, 이름 또는 둘 다 추가로 분류될 수 있다.
    - URI는 리소스를 식별
    - URI가 URL과 URN을 포함한다.
    URL (Resource Locator)  →  `foo://exam.com:8042/.........`
    URN (Resource Name)  →  `urn:example:animal:.........`
        - 거의 URL만 사용함 (이름을 부여하면 거의 찾을 수 없음)

- **URI**
Uniform : 리소스 식별하는 통일된 방식
Resource : 자원, URI로 식별할 수 있는 모든 것(제한 없음, ex.실시간 교통정보)
Identifier : 다른 항목과 구분하는데 필요한 정보

## URL, URN

- URL (Uniform Resource Locator)
: 리소스가 있는 위치를 지정
- URN (Uniform Resource Name)
: 리소스에 이름을 부여
- 위치는 변할 수 있지만, 이름은 변하지 않는다.
- URN 이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 ❌ ⇒ URL만 사용

## URL 분석

### scheme://[userinfo@]host[:port][/path][?query][#fragment]

1. scheme
    - 주로 프로토콜에 사용
    - 프로토콜 : 어떤 방식으로 자원에 접근할 것인가? 하는 클라이언트와 서버 간의 어떤 약속과 규칙
    예 ) http, https, ftp 등
    - http → 80포트 / https → 443포트를 주로 사용  ⇒  포트 생략 가능
    - https : http에 보안(secure) 추가
2. userinfo
    - URL에 사용자 정보를 포함해서 인정해야 될 떄 사용
    - 거의 사용 ❌
3. host
    - 호스트명
    - 도메인명 또는 IP주소를 직접 인용 가능
4. port
    - 접속 포트
    - 일반적으로 생략, 특정 서버에 따로 접근해야 할 때는 직접 입력 하기도 함
    생략시 http → 80포트 / https → 443포트
5. path
    - 리소스 경로
    - 계층적 구조로 되어있음 (이해하기 쉬움)
    - 예) /home/members/100,/items
6. query
    - `key=value`의 형태로 데이터 작성
    - ?로 시작
    &로 추가
    `?q=hello&hl=ko`
    - query parameter, query string 등으로 불림,
    웹 서버에 제공하는 파라미터, 문자 형태(다 문자로 넘김)
7. fragment
    - html 내부 북마크 등에서 사용
    - 서버에 전송하는 정보는 아님