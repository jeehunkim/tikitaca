---
description: '1:1 예상 답변'
---

# INQUIRY\_ANSWER

{% api-method method="post" host="https://api.tikita.ca" path="/v1/admin/inquiry/answer" %}
{% api-method-summary %}
1:1 예상답변 입력 
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
{% api-method-parameter name="history" type="object" required=false %}
히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="is\_use" type="boolean" required=true %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="make\_date" type="string" required=false %}
등록일 
{% endapi-method-parameter %}

{% api-method-parameter name="manager" type="string" required=false %}
등록자 
{% endapi-method-parameter %}

{% api-method-parameter name="answer\_comment" type="string" required=true %}
예상답변 내용 
{% endapi-method-parameter %}

{% api-method-parameter name="answer\_title" type="string" required=true %}
예상답변 제목 
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
    "rstMsg": "예상답변이 등록되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
/* example */
{
    "answer_title" : "예상답변 제목 ",
    "answer_comment" : "안녕하세요 고객님 ... ",
    "manager" : "SU",    
    "make_date" : YYYY-MM-DD hh:mm:ss,
    "is_use" : 1,
    "history" : {
                    "history_code" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/inquiry/answer/:UUID" %}
{% api-method-summary %}
1:1 예상답변 수정 
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
{% api-method-parameter name="history" type="object" required=false %}
히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="is\_use" type="boolean" required=false %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="answer\_comment" type="string" required=false %}
예상답변 내용 
{% endapi-method-parameter %}

{% api-method-parameter name="answer\_title" type="string" required=false %}
예상답변 제목 
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
    "rstMsg": "예상답변 수정 되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
/* example */
{
    "answer_title" : "예상답변 제 ",
    "answer_comment" : "예상답변 내용  ",    
    "is_use" : 0,
    "history" : {
                    "history_code" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/inquiry/answer/:UUID" %}
{% api-method-summary %}
1:1 예상답변 호출 
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
    "rstCode": 200,
    "answer_title" : "과금관련 ",
    "answer_comment" : "과금관련 ",
    "manager" : "SU",    
    "make_date" : YYYY-MM-DD hh:mm:ss,
    "is_use" : 1,
    "history" : {
                    "history_code" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



```text
https://api.tikita.ca/v1/admin/inquiry/answer/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

