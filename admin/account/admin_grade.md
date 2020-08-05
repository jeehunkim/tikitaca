---
description: 관리자 등급
---

# ADMIN\_GRADE

{% api-method method="post" host="https://api.tikita.ca" path="/v1/admin/member/grade" %}
{% api-method-summary %}
관리자 등급 등록 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="is\_use" type="boolean" required=false %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
등록일 
{% endapi-method-parameter %}

{% api-method-parameter name="grade\_code" type="string" required=true %}
등급코드 
{% endapi-method-parameter %}

{% api-method-parameter name="grade\_name" type="string" required=true %}
등급명 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "rstCode": "200",
    "rstMsg": "관리자 등급이 등록되었습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": "403",
    "rstMsg": "권한없음 "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
/* example */
{
    "grade_uuid" : UUID
    "grade_code" : "SU",
    "grade_name" : "최고관리자",
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "is_use": 0
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/member/grade/:grade\_uuid" %}
{% api-method-summary %}
관리자 등급 수정 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
jwt
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="is\_use" type="boolean" required=false %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="grade\_name" type="string" required=false %}
등급명 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": "200",
    "rstMsg": "관리자 코드/등급명이 변경되었습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": "403",
    "rstMsg": "권한없음 "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "is_use" : 0,
    "grade_name" : "최고관리자2"
}
```

```text
/* in case sql */
update "tables" set is_use = 0, grade_name = '최고관리자2' where grade_code = 'SU'
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/member/grade/:grade\_uuid" %}
{% api-method-summary %}
관리자 등급 삭제 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="is\_use" type="boolean" required=false %}
사용유무 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": "200",
    "rstMsg": "관리자 코드가 삭제되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/admin/member/grade/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

```text
/* in case sql */
update "tables" set is_use = 3 where grade_uuid = 'b948e2be-9b7a-4963-bcff-34cee7c2e38a'
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/member/grade/:grade\_uuid" %}
{% api-method-summary %}
관리자 등급 조회 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
/* example */
{
    "rstCode" : 200,
    "grade_uuid" : UUID
    "grade_code" : "SU",
    "grade_name" : "최고관리자",
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "is_use": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/admin/member/grade/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

```text
/* in case sql */
select * from "tables" where grade_uuid = 'b948e2be-9b7a-4963-bcff-34cee7c2e38a'
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/member/grade" %}
{% api-method-summary %}
관리자 등급 전체 리스트 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
/* example */
{
    "grade_uuid" : UUID
    "grade_code" : "SU",
    "grade_name" : "최고관리자",
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "is_use": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

