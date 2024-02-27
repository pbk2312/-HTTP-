# HTTP 헤더

## HTTP BODY 

HTTP 응답 메시지:

     HTTP/1.1 200 OK
    Content-Type: text/html;charset=UTF-8 Content-Length: 3423
    <html> <body>...</body>
    </html>

표현 헤더:
     
    Content-Type: text/html;charset=UTF-8 
    Content-Length: 3423

표현 데이터:
     
    <html> <body>...</body>
    </html>

* 메시지 본문(페이로드)을 통해 표현 데이터 전달
* 표현은 요청이나 응답에서 전달할 실제 데이터
* 표현 헤더는 표현 데이터를 해석 가능한 정보 제공

### 표현
* Content-Type: 표현 데이터의 형식
  * 미디어 타입, 문자 인코딩(text/html; charset=utf-8; application/json; image/png;) 
* Content-Encoding: 표현 데이터의 압축 방식
  * 표현 데이터를 압축하기 위해 사용 
* Content-Language: 표현 데이터의 자연 언어
  * 표현 데이터의 자연 언어를 표현(ko,en)
* Content-Length: 표현 데이터의 길이

### 협상
**클라이언트가 선호하는 표현 요청**
* Accept: 클라이언트가 선호하는 미디어 타입 전달
* Accept-Charset: 클라이언트가 선호하는 문자 인코딩
* Accept-Encoding: 클라이언트가 선호하는 압축 인코딩
* Accept-Language: 클라이언트가 선호하는 자연 언어

### 협상 우선 순위

요청 메시지:

       GET /event
       Accept-Language: ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7

* 숫자가 클수록 우선 순위
* 생략하면 1

요청 메시지:

       GET /event
       Accept: text/*, text/plain, text/plain;format=flowed, */*

* 구체적인 것이 우선한다


## HOST 
* 요청에서 사용
* 필수
* 하나의 서버가 여러 도메인을 처리해야 할 때
* 하나의 IP 주소에 여러 도메인이 적용되어 있을 때

## Retry-After
**유저 에이전트가 다음 요청을 하기까지 기다려야 하는 시간** 

## 쿠키 
* Set-Cookie: 서버에서 클라이언트로 쿠키 전달(응답)
* Cookie: 클라이언트가 서버에서 받은 쿠키를 저장하고, HTTP 요청시 서버로 전달

* 사용처
  * 사용자 로그인 세션 관리
  * 광고 정보 트래킹
* 쿠키 정보는 항상 서버에 전송됨
  * 네트워크 트래픽 추가 유발
  * 최소한의 정보만 사용(세션 id, 인증 토큰)
* 보안에 민감한 데이터는 저장하면 안됨(주민번호, 신용카드 번호 등등)
* 생명주기
  * Set-Cookie: expires=Sat, 26-Dec-2020 04:39:21 GMT - 만료일이 되면 쿠키 삭제
  * Set-Cookie: max-age=3600 (3600초) - 시간되면 삭제
  * 세션 쿠키: 만료 날짜를 생략하면 브라우저 종료시 까지만 유지
  * 영속 쿠키: 만료 날짜를 입력하면 해당 날짜까지 유지
 
