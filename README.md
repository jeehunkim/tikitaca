# API

{% hint style="info" %}
 API 기본설계 방향 
{% endhint %}

1. URI는 정보의 자원을 표현해야 한다.
2. 자원에 대한 행위는 HTTP Method\(GET, POST, PUT, DELETE\)로 표현한다.
3. 슬래시 구분자\(/\)는 계층 관계를 나타내는 데 사용한다.
4. URI 마지막 문자로 슬래시\(/\)를 포함하지 않는다.
5. 하이픈\(-\)은 URI 가독성을 높이는데 사용된다.
6. 밑줄\(\_\)은 URI에 사용하지 않는다.
7. URI 경로에는 소문자가 적합하다.
8. 파일 확장자는 URI에 포함시키지 않는다.
9. REST API에서는 메시지 바디 내용의 포맷을 나타내기 위한 파일 확장자를 URI 안에 포함시키지 않습니다. Accept header를 사용하도록 합시다.
10. Content-Type = application/json
11. json 키값은 소문자+\(\_\)로 사용한다.
12. 올바른 http\_status를 제공한다.

| CODE | METHOD | BODY |
| :--- | :--- | :--- |
| 200 | GET | OK |
| 201 | POST, PUT |  |
| 204 | DELETE |  |

```text
HTTP/1.1 200 OK
{
  "rst_code": 0,
  "rst_msg": "",
  "user_name": "nob98"
}
```

```text
HTTP/1.1 201 OK
```

```text
HTTP/1.1 204 OK
```

| CODE | RST\_CODE | 설명  |
| :--- | :--- | :--- |
| 400 | 1 | 헤더정보가 올바르지 않을경우  |
| 400 | 2 | 필수 인자가 포함되지 않은경우  |
| 403 | 1 | 해당 API에 대한 요청 권한이 없는 경우  |
| 403 | 2 | 토큰정보가 올바르지 않은경우  |
| 405 | 1 | 허용되지 않는 방법\(POST와 GET등 사용되지 않는 방법에 대한 요청\) |

| 기본 key name | value |
| :--- | :--- |
| 작성자/등록자/ | register |
| 작성일/등록일/ | regist\_date |
| 사용유무/ | is\_use |
| history 내용/ | history\_memo |
| history 등록일/ | history\_date |
| history 등록자/ | history\_manager |



