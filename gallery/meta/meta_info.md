---
description: 메타 정보
---

# META\_INFO

{% api-method method="post" host="https://api.tikita.ca" path="/v1/gallery/meta-info" %}
{% api-method-summary %}
갤러리 생성 
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
{% api-method-parameter name="register" type="string" required=true %}
갤러리 개설자 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_uuid" type="string" required=true %}
갤러리 고유번호 
{% endapi-method-parameter %}

{% api-method-parameter name="history" type="object" required=false %}
히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="owener\_info" type="object" required=true %}
관리자정보 관리자아이디/등급/상태/등
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_status" type="integer" required=true %}
갤러리 상태 정상/폐쇄/임시폐쇄 등 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=true %}
개설일 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_img" type="string" required=false %}
갤러리 대표 이미지 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_info" type="string" required=false %}
갤러리 소개 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_name" type="string" required=true %}
갤러리 이름 
{% endapi-method-parameter %}

{% api-method-parameter name="view\_sort" type="integer" required=false %}
노출순서 
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
    "rstMsg": "갤러리가 생성 되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

> 기본키

| gallery\_status | 1 |
| :--- | :--- |
| 정상  | 0 |
| 대기  | 1 |
| 보류\(임시폐쇄\)  | 2 |
| 폐쇄\(삭제\) | 3 |

```text
{
    "gallery_uuid": UUID,
    "view_sort": 0,
    "gallery_name": "빨간당",
    "gallery_info": "빨간당 소개 ",
    "gallery_img": "../img/src/....png",
    "register": "SU",
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "gallery_status": 0,
    "owener_info" : {
                    "owner_UUID" : MEMBER_UUID,
                    "owner_grade" : 0,
                    "owener_status" : 0,
                    "regist_date" : YYYY-MM-DD hh:mm:ss,
                    "register" : "SU"
                    },
    "history" : {
                    "history_memo" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

{% hint style="info" %}
owner\_grade - 0 : 소유자, 1 : 매니저, 2 : 부매니저 
{% endhint %}

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/gallery/meta-info/:gallery\_uuid" %}
{% api-method-summary %}
갤러리 수정 
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

{% api-method-parameter name="owener\_info" type="object" required=false %}
관리자 정보 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_status" type="integer" required=false %}
갤러리 상태 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_img" type="string" required=false %}
갤러리 대표 이미지 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_info" type="string" required=false %}
갤러리 소개 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_name" type="string" required=false %}
갤러리명 
{% endapi-method-parameter %}

{% api-method-parameter name="view\_sort" type="integer" required=false %}
노출순서 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "view_sort": 0,
    "gallery_name": "빨간당",
    "gallery_info": "빨간당 소개 ",
    "gallery_img": "../img/src/....png",
    "gallery_status": 0,
    "owener_info" : {
                    "owner_UUID" : MEMBER_UUID,
                    "owner_grade" : 0,
                    "owener_status" : 0,
                    "regist_date" : YYYY-MM-DD hh:mm:ss,
                    "register" : "SU"
                    },
    "history" : {
                    "history_memo" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/gallery/meta-info/:gallery\_uuid" %}
{% api-method-summary %}
갤러리 정보 호출 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": "200",
    "gallery_UUID": UUID,
    "view_sort": 0,
    "gallery_name": "빨간당",
    "gallery_info": "빨간당 소개 ",
    "gallery_img": "../img/src/....png",
    "register": "SU",
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "gallery_status": 0,
    "owener_info" : {
                    "owner_UUID" : MEMBER_UUID,
                    "owner_grade" : 0,
                    "owener_status" : 0,
                    "regist_date" : YYYY-MM-DD hh:mm:ss,
                    "register" : "SU"
                    },
    "history" : {
                    "history_memo" : 0,
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
https://api.tikita.ca/v1/gallery/meta-info/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```



