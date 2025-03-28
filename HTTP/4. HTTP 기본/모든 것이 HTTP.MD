# 모든 것이 HTTP

---

## HTTP (HyperTextTransferProtocol)

모든 것을 HTTP 메시지에 모든 것을 전송

- HTML, TEXT
- IMAGE, 음성, 영상, 파일
- JSON, XML (API)
- 서버 간에 데이터를 주고 받을 때도 대부분 HTTP 사용

⇒ 거의 모든 형태의 데이터 전송 가능

- HTTP 역사
    - HTTP/1.1 1997년
     : 가장 많이 사용, **우리에게 가장 중요한 버전**
    - HTTP/2, HTTP/3 → 성능 개선에 초점

## 기반 프로토콜

- TCP: HTTP/1.1, HTTP/2
- UDP: HTTP/3
- 현재 HTTP/1.1 주로사용
    - HTTP/2, HTTP/3도 점점 증가

## HTTP 특징

- 클라이언트 서버 구조로 기본적으로 동작함
- 무상태 프로토콜을 지향, 비연결성
- HTTP 메시지로 통신
- 단순함, 확장 가능