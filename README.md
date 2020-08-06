# API

{% hint style="info" %}
 API 기본설계 방향 
{% endhint %}

### 1. URI는 정보의 자원을 표현해야 한다.

### 2. 자원에 대한 행위는 HTTP Method로 표현한다.

> POST

* 지정된 URI에 리소스를 추가\(생성\)한다.

> GET

* 지정된 URI에 리소스를 조회한다.

> PUT

* 지정된 URI에 리소스를 생성하거나 전체 업데이트 한다.\(단 참조된 Collection을 제외한 나머지는 초기화 된다\)

> PATCH

* 지정된 URI에 리소스의 일부분을 업데이트 한다.

> DELETE

* 지정된 URI의 리소스를 삭제한다.

### 3. URI의 슬래시 구분자\(/\)는 계층관계를 나타내는데 사용한다.

### 4. URI의 마지막 문자로 슬래시\(/\)를 포함하지 않는다.

### 5. 하이픈\(-\)은 URI의 가독성을 높이는데 사용된다.

### 6. 언더바\(\_\)는 URI에 사용하지 않는다.

### 7. URI의 문는 소문자로 사용한다.

### 8. GET요청시 파일 확장자는 URI에 포함하지 않는다.

### 9. Content-Type = application/json 을 사용한다.

### 10. json 키값은 소문자 혹 언더바\(\_\)를 포함하여 사용한다.

### 11. RETURN 되는 API는 각 속성에 맞는 HTTP\_STATUS를 제공한다.

| CODE | METHOD | BODY |
| :--- | :--- | :--- |
| 200 | GET, PUT, PATCH | OK |
| 201 | POST |  |
| 204 | DELETE |  |

```text
HTTP/1.1 200 OK
{
  "rst_msg": "",
  "user_name": "nob98"
}
```

```text
HTTP/1.1 201 Created
```

```text
HTTP/1.1 204 No Content
```

| CODE | RST\_CODE | 설명  |
| :--- | :--- | :--- |
| 400 | 1 | 헤더정보가 올바르지 않을경우  |
| 400 | 2 | 필수 인자가 포함되지 않은경우  |
| 401 | 1 | 인증이 필요한 리소스에 인증없이 접근했을 경우  |
| 403 | 1 | 해당 API에 대한 요청 권한이 없는 경우  |
| 403 | 2 | 토큰정보가 올바르지 않은경우  |
| 405 | 1 | 허용되지 않는 방법\(POST와 GET등 사용되지 않는 방법에 대한 요청\) |

```text
HTTP/1.1 400 Bad Request
{
  "rst_code": 2,
  "rst_msg": "필수 인자값이 누락되었습니다."
}
```

```text
HTTP/1.1 401 Unauthorized
{
  "rst_code": 1,
  "rst_msg": "토큰값이 누락되었습니다."
}
```

```text
HTTP/1.1 403 Forbidden
{
  "rst_code": 1,
  "rst_msg": "해당 API에 대한 접근권한이 없습니다."
}
```

```text
HTTP/1.1 403 Forbidden
{
  "rst_code": 2,
  "rst_msg": "토큰정보가 올바르지 않습니다."
}
```

```text
HTTP/1.1 405 Method Not Allowed
{
  "rst_code": 1,
  "rst_msg": "잘못된 요청입니다."
}
```

### 12. 공통으로 사용하는 JSON 키값에 대한 정리.

| 기본 key name | value |
| :--- | :--- |
| 작성자/등록자/ | register |
| 작성일/등록일/ | regist\_date |
| 사용유무/ | is\_use |
| history 내용/ | history\_memo |
| history 등록일/ | history\_date |
| history 등록자/ | history\_manager |



