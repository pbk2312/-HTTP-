# [URI와 웹 브라우저 요청 흐름]
* URI
* 웹 브라우저 요청 흐름

## URI(Uniform Resource Identifier)
**URI안에 URL(리소스가 여기있어요),URN(리소그 이름 그 자체)**

* URL: Uniform Resource Locator -> foo://example.com:8042/over/there?name=ferret#nose
* URN: Uniform Resource Name -> urn:example:animal:ferret:nose



### URI
* Uniform: 리소스 식별하는 통일된 방식
* Resource: 자원, URI로 식별할 수 있는 모든 것(제한 없음)
* Identifier: 다른 항목과 구분하는데 필요한 정보

## URL,URN
* URL - Locator : 리소스가 있는 위치를 지정
* URN - Name : 리소스에 이름 부여
* 위치는 변경 가능,하지만 이름 변함 X

## URL 
1. **전체문법**


-> scheme://[userinfo@]host[:port][/path][?query][#fragment]

-> https://www.google.com/search?q=hello&hl=ko

* 프로토콜(https)
* 호스트명(www.google.com)
* 포트번호(443)
* Path(/search)
* 쿼리 파리미터(q=hello&hl=ko)


2. **스키마**

* 주로 프로토콜 사용(ex> http,https,ftp 등등)
* http는 80포트,https는 443 포트 주로 사용,포트 생략 가능
* https는 http에 보안을 추가



## 웹 브라우저 요청 흐름

-> https://www.google.com/search?q=hello&hl=ko

HTTP 요청 메시지:

    GET /search?q=hello&hl=ko HTTP/1.1 Host: www.google.com


HTTP 응답 메시지:

     HTTP/1.1 200 OK
    Content-Type: text/html;charset=UTF-8 Content-Length: 3423
    <html> <body>...</body>
    </html>

클라이언트쪽에 응답 메시지에 있는 HTML이 렌더링되어 화면에 보여줌

    

  


  
