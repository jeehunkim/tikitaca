---
description: 관리자 등급
---

# ADMIN\_GRADE

{% api-method method="post" host="https://api.tikita.ca" path="/v1/admin/member/grade" %}
{% api-method-summary %}
관리자 등급 등록 
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
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
    "grade_code" : "SU",
    "grade_name" : "최고관리자"
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/member/grade/:grade\_code" %}
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

{% api-method method="delete" host="https://api.tikita.ca" path="/v1/admin/member/grade/:grade\_code" %}
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
https://api.tikita.ca/v1/admin/member/grade/SU
```

```text
/* in case sql */
update "tables" set is_use = 0 where grade_code = 'SU'
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/member/grade/:grade\_code" %}
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
    "serial_no" : "일련번호",
    "grade_name" : "최고관리자",
    "make_date" : "2020-07-30",
    "is_use" : true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/admin/member/grade/SU
```

```text
/* in case sql */
select * from "tables" where grade_code = 'SU'
```

