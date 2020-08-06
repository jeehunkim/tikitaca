---
description: 갤러리 1차 카테고리 정보
---

# CATEGORY\_INFO

{% api-method method="post" host="https://api.tikita.ca" path="/v1/admin/gallery/category" %}
{% api-method-summary %}
1차 카테고리 등록 
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

{% api-method-parameter name="sort\_no" type="integer" required=true %}
노출순서 
{% endapi-method-parameter %}

{% api-method-parameter name="is\_use" type="boolean" required=true %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=true %}
생성일 
{% endapi-method-parameter %}

{% api-method-parameter name="category\_name" type="string" required=true %}
카테고리명 
{% endapi-method-parameter %}

{% api-method-parameter name="category\_code" type="string" required=true %}
카테고
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
HTTP/1.1 201 Created
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

> 기본키

| is\_use | 1 |
| :--- | :--- |
| 사용안함 | 0 |
| 사용  | 1 |

```text
{
    "category_uuid": UUID,
    "category_code": "AE",
    "category_name": "유머 ",
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "is_use" : 1,
    "sort_no" : 1,
    "history" : {
                    "history_memo" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }                
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/gallery/category/:UUID" %}
{% api-method-summary %}
1차 카테고리 수정 
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

{% api-method-parameter name="sort\_no" type="string" required=false %}
노출순서 
{% endapi-method-parameter %}

{% api-method-parameter name="is\_use" type="string" required=false %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="category\_name" type="string" required=true %}
카테고리 이름  
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
HTTP/1.1 200 OK
{
  "rst_msg": "카테고리정보가 수정되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
/* example */
{
    "category_name" : "음란물 신고 ",
    "is_use" : 0,
    "sort_no" : 0,    
    "history" : {
                    "history_code" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/gallery/category/:UUID" %}
{% api-method-summary %}
1차 카테고리 정보 호출 
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
HTTP/1.1 200 OK
{
    "category_code": "AE",
    "category_name": "유머 ",
    "make_date" : YYYY-MM-DD hh:mm:ss,
    "is_use" : 1,
    "sort_no" : 1,
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
https://api.tikita.ca/v1/admin/gallery/category/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```



