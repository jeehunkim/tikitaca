---
description: '1:1 문의유형(카테고리)'
---

# INQUIRY\_CATEGORY

{% api-method method="post" host="https://api.tikita.ca" path="/v1/admin/inquiry/category" %}
{% api-method-summary %}
카테고리 등록 
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
{% api-method-parameter name="category\_uuid" type="string" required=false %}
카테고리 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="history" type="object" required=false %}
히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="is\_use" type="boolean" required=true %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
등록일 
{% endapi-method-parameter %}

{% api-method-parameter name="register" type="string" required=true %}
등록자 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_kind" type="string" required=true %}
문의유형 제목 
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
    "rstMsg": "문의 유형 등록되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

> 기본키

| is\_use | 1 |
| :--- | :--- |
| 사용안함  | 0 |
| 사용  | 1 |

```text
/* example */
{
    "inquiry_kind" : "과금관련 ",
    "register" : "SU",
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "is_use" : 1,
    "history" : {
                    "history_memo" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/inquiry/category/:category\_uuid" %}
{% api-method-summary %}
카테고리 수정/삭제 
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

{% api-method-parameter name="inquiry\_kind" type="string" required=false %}
문의유형 제목 
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
    "rstMsg": "문의유형이 수정 되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
/* example */
{
    "inquiry_kind" : "음란물 신고 ",
    "is_use" : 0,
    "history" : {
                    "history_memo" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/inquiry/category/:category\_uuid" %}
{% api-method-summary %}
카테고리 정보 호출 
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
    "inquiry_title" : "과금관련 ",
    "register" : "SU",
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "is_use" : 1,
    "history" : {
                    "history_memo" : 1,
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
https://api.tikita.ca/v1/admin/inquiry/category/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```



{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/inquiry/category" %}
{% api-method-summary %}
카테고리 리스트 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authentication" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
/* example */
[
{
    "inquiry_title" : "과금관련 ",
     "register" : "SU",
    .
    .
    .
},
{
    "inquiry_title" : "민원관련 ",
     "register" : "SU",
    .
    .
    .
}
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

