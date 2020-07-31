---
description: 관리자 소속
---

# ADMIN\_GROUP

{% api-method method="post" host="https://api.tikita.ca" path="/v1/admin/member/group" %}
{% api-method-summary %}
관리자 소속항목 등록 
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
jtw token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="history" type="object" required=false %}
history
{% endapi-method-parameter %}

{% api-method-parameter name="manager" type="string" required=false %}
등록자 
{% endapi-method-parameter %}

{% api-method-parameter name="group\_name" type="string" required=true %}
관리자 소속
{% endapi-method-parameter %}

{% api-method-parameter name="group\_code" type="string" required=true %}
관리자 소속 코드 
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
    "rstMsg": "소속 정보가 입력되었습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{
    "rstCode": "403",
    "rstMsg": "권한없"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "UUID": UUID,
    "group_Code": "P-00001",
    "group_Name": "개발부",
    "registDate": YYYY-MM-DD hh:mm:ss,
    "manager" : "SU",
    "is_use" : 1,
    "history" : {
                    "history_code" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }                
}
```



{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/member/group/:UUID" %}
{% api-method-summary %}
관리자 소속항목 수정 
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
{% api-method-parameter name="history\_manager" type="string" required=false %}
처리자 
{% endapi-method-parameter %}

{% api-method-parameter name="is\_use" type="boolean" required=false %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="group\_name" type="string" required=false %}
소속
{% endapi-method-parameter %}

{% api-method-parameter name="group\_code" type="string" required=false %}
소속코드 
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
    "rstMsg": "소속 정보가 변경되었습니다."
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
    "group_Code": "P-00001",
    "group_Name": "개발부",
    "is_use" : 0,
    "history" : {
                    "history_code" : 2,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }                
}
```

{% api-method method="delete" host="https://api.tikita.ca" path="/v1/admin/member/group/:UUID" %}
{% api-method-summary %}
관리자 소속정보 삭제 
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": "200",
    "rstMsg": "소속 정보가 삭되었습니다."
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
https://api.tikita.ca/v1/admin/member/group/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/member/group/:UUID" %}
{% api-method-summary %}
관리자 소속정보 호출 
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
    "rstCode": 200,
    "part_Code": "P-00001",
    "part_Name": "개발부",
    "registDate": YYYY-MM-DD hh:mm:ss,
    "manager" : "SU",
    "is_use" : 1,
    "history" : [{
                    "history_code" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                },
                {
                    "history_code" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }]               
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
https://api.tikita.ca/v1/admin/member/group/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

