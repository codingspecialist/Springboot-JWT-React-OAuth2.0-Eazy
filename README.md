# Spring JWT 서버로 OAuth까지 React와 연동

## 주의사항

- 시큐리티가 동작할 때만 CORS가 작동하여 차단함.
- SecurityConfig.java에 addFilter()로 cors 설정을 걸어줘야 함.

## Client Credentails Grant Type 방식 사용

- https://cheese10yun.github.io/spring-oauth2-provider/

- 기본구성은 Spingboot서버는 JWT토큰 생성기
- OAuth2.0 로그인은 React에서 함. https://www.npmjs.com/package/react-google-login
- React에서 로그인되면 그 정보를 그대로 스프링으로 던짐
- 스프링에서 그걸 받아서 회원가입 시키고 회원정보를 세션에 담음
- 그리고 JWT 토큰 만들어서 response의 body에 담아서 전송
- React에서 JWT 토큰 받아서 localStorage에 저장.
- 인증이 필요한 요청시마다 header에 JWT토큰 담아서 요청.

![blog](https://postfiles.pstatic.net/MjAyMDA4MTlfMTA0/MDAxNTk3NzY2MzA0Nzk2.lP9wYniN_9lQrAnkG5gmPWlDS1cNhLr8JUgk5cXwnAUg.ALy_HtvN3xvy4KAC14PNOq0H0I7-yZT78E3L1ciRilQg.JPEG.getinthere/Screenshot_2.jpg?type=w773)

## 라이브러리

- yarn add axios
- npm install react-google-login

## 설치 및 환경설정

- git에서 내려 받으면 node-module 폴더가 없음.
- npm install 명령어 입력하여 node-module 폴더 생성해서 테스트 해야함.

## 참고

- https://velog.io/@seize/React-%EC%B9%B4%EC%B9%B4%EC%98%A4-%EC%86%8C%EC%85%9C-%EB%A1%9C%EA%B7%B8%EC%9D%B8#8-kakaoauthlogin-%ED%95%A8%EC%88%98%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%B9%B4%EC%B9%B4%EC%98%A4-%EB%A1%9C%EA%B7%B8%EC%9D%B8-%ED%8C%9D%EC%97%85%EC%B0%BD-%EC%B6%9C%EB%A0%A5-%EB%B0%8F-%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EC%B2%98%EB%A6%AC
