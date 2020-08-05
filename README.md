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
| 201 | POST |  |
| 204 | DELETE |  |

{% hint style="warning" %}
200계열에서의 RETURN\_CODE는 포함하지 않는다.

400계열서의 RETURN\_CODE는 별도로 작성한다.
{% endhint %}

| CODE | RST\_CODE | 설명  |
| :--- | :--- | :--- |
| 403 | 0 | 해당 API에 대한 요청 권한이 없는 경우 |
| 400 | 1 | 헤더정보가 올바르지 않을경 |
| 400 | 2 | 필수 인자가 포함되지 않은경 |
| 403 | 3 | 토큰정보가 올바르지 않은경 |

| 각 키별 상태 | value |
| :--- | :--- |
| 정상/사용/완료/게시/ | 0 |
| 대기/ | 1 |
| 보류/임시폐쇄/ | 2 |
| 삭제/탈퇴/폐쇄/ | 3 |
| 휴면/ | 4 |
| 관리자삭제/ | 5 |
| 처리중/ | 6 |
| 접수/ | 7 |

| 기본 key name | value |
| :--- | :--- |
| 작성자/등록자/ | register |
| 작성일/등록일/ | regist\_date |
| 사용유무/ | is\_use |
| history 내용/ | history\_memo |
| history 등록일/ | history\_date |
| history 등록자/ | history\_manager |



