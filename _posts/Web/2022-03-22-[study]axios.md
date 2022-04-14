---
title: "Axios"
excerpt: "Axios"
excerpt_separator: "<!--more-->"
categories:
  - Web
tags:
  - Axios
  - Server
  - Network
last_modified_at: 2022-03-23T20:40:00
---

<!--more-->

<br>

## Axios

#### Axios란?

- Axios는 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동기 통신 라이브러리이다.
- React.js와 Vue.js에서 데이터를 fetch하는 기본 라이브러리이며, 현대 프론트엔드 프레임워크들은 Axios를 주로 사용하고 있다.
- 서버 측에서는 기본 node.js http 모듈을 사용하고, 클라이언트(브라우저)에서는 XMLHttpRequests를 사용한다.

#### Axios 특징

- 브라우저에서 XMLHttpRequests를 만든다.
- node.js에서 http요청을 만든다.
- Promise API를 지원한다.
- 요청 및 응답 가로채기가 가능하다.
- 요청 및 응답 데이터를 변환하는 것이 가능하다.
- HTTP 요청을 취소하는 것이 가능하다.
- HTTP 요청과 응답을 JSON 형태로 자동 변환을 해준다.

#### Axios 사용 방법

- 설치

```
/* npm 방법 */
npm install axios

/* bower 방법 */
bower install axios

/* yarn 방법 */
yarn add axios

/* jsDelivr CDN 방법 */
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

/* unpkg CDN 방법 */
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
```

- 사용 문법 예시

```javascript
axios({
  url: "https://www.JKPY.com/study/web",
  method: "get",
  data: {
    foo: "취직 좀 하자 좀!!!!!!!!!!!",
  },
});
```

- axios 요청 파라미터

  - **url**: 요청을 보내고자 하는 서버의 주소
  - **method**: 요청 방식(CRUD 중 하나)
  - **baseURL**: url을 상대 경로로 쓸 때 가장 앞에서 기반이 될 url
  - **headers**: 요청 헤더
  - **data**: 요청의 method에 따라 서버에 전달할 데이터를 담는 항목(body)
  - **params**: get 방식으로 요청을 보낼 때 query에 담을 내용
  - timeout: 요청이 전달되기 전 millisecond 단위의 시간을 요청
  - responseType: 서버가 응답해주는 데이터의 타입(arraybuffer, document, json, text, stream, blob)
  - responseEncoding: 디코딩 응답에 사용하기 위한 인코딩(utf-8)
  - transformRequest: 서버에 전달되기 전에 요청 데이터를 바꿀 수 있다.(PUT, POST, PATCH, DELETE의 경우만 가능)
  - transformResponse: 응답 데이터가 만들어지기 전에 변환 가능
  - **withCredentials**: cross-site access-control 요청 허용 유무
  - auth: HTTP의 기본 인증에 사용. auth를 통해서 HTTP의 기본 인증 구성 가능
  - maxContentLength: http 응답 내용의 max 사이즈를 지정하도록 하는 옵션
  - validateStatus: HTTP 응답 상태 코드에 대해 promise의 반환 값이 resolve 또는 reject할지 지정하도록 하는 옵션
  - maxRedirects: node.js에서 사용되는 리다이렉트 최대치를 지정
  - httpAgent / httpsAgent: node.js에서 http나 https를 요청할 때 사용자 정의 agent를 정의하는 옵션
  - proxy: proxy 서버의 hostname과 port를 정의하는 옵션
  - cancelToken: 요청을 취소하는데 사용되는 취소 토큰 명시

  #### Axios 응답 예시

  ```javascript
  {
    data: {},   // 서버 제공 응답

    status: 200,    // 서버 응답의 http 상태 코드

    statusText: 'OK',     // 서버 응답의 http 상태 메시지

    headers: {},      //

    config: {},     // 요청에 대해 axios에 설정된 구성

    request: {},    // 응답을 생성한 요청
  }
  ```
