---
description: 게시글
---

# GALLERY\_BOARD

{% api-method method="post" host="https://api.tikita.ca" path="/v1/gallery/:gallery\_UUID" %}
{% api-method-summary %}
게시글 작성 
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
{% api-method-parameter name="write\_env" type="string" required=false %}
작성환경 웹/모바일웹 
{% endapi-method-parameter %}

{% api-method-parameter name="status\_flag" type="integer" required=false %}
상태값 정상/보류/삭제/관리자삭제 등 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_ip" type="string" required=false %}
등록 아이피 
{% endapi-method-parameter %}

{% api-method-parameter name="view\_count" type="string" required=false %}
조회수 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
작성일 
{% endapi-method-parameter %}

{% api-method-parameter name="register" type="string" required=true %}
작성자 
{% endapi-method-parameter %}

{% api-method-parameter name="only\_vs" type="object" required=false %}
VS전용 경쟁항목수/항목타이틀 등 
{% endapi-method-parameter %}

{% api-method-parameter name="action\_count" type="object" required=false %}
좋아요/싫어요/신고 카운트 
{% endapi-method-parameter %}

{% api-method-parameter name="contents" type="string" required=true %}
내용 
{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=true %}
제목 
{% endapi-method-parameter %}

{% api-method-parameter name="fixed\_flag" type="boolean" required=true %}
공지일 경우 상단고정 유무 
{% endapi-method-parameter %}

{% api-method-parameter name="content\_flag" type="integer" required=true %}
게시글 형식 공지/일반/VS
{% endapi-method-parameter %}

{% api-method-parameter name="content\_uuid" type="string" required=true %}
게시글 일련번호 
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
    "rstMsg": "게시글이 등록 되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
content\_flag - 0 : 공지, 1 : 일반, 2 : VS 

fixed\_flag - 0 : 기본, 1 : 상단 고정 
{% endhint %}

```text
{
    "gallery_uuid": UUID,
    "content_uuid": UUID,
    "content_flag": 0,
    "fixed_flag": 0,    
    "title": "빨간당",
    "contents": "빨간당 소개 내",
    "action_count" : {
                    "like" : 0,
                    "bad" : 0,
                    "police" : 0
                    },
    "only_vs" : {
                    "vs_count" : 3,
                    "vs_title" : ["제목1","제목2","제목3"],
                    "vs_image" : ["img1.jpg","img2.jpg","img3.jpg"],
                    "vs_poll_count": [0,0,0],
                    "vs_start" : YYYY-MM-DD hh:mm:ss,
                    "vs_end" : YYYY-MM-DD hh:mm:ss
                    },    
    "register": "nob98",
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "view_count": 0,
    "regist_ip": "127.0.0.1",
    "status_flag": 0,
    "write_env": 0
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/gallery/:gallery\_UUID/:content\_UUID" %}
{% api-method-summary %}
게시글 수정 
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
{% api-method-parameter name="status\_flag" type="integer" required=false %}
상태값 
{% endapi-method-parameter %}

{% api-method-parameter name="only\_vs" type="object" required=false %}
VS전용 
{% endapi-method-parameter %}

{% api-method-parameter name="contents" type="string" required=false %}
내용 
{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=false %}
제목 
{% endapi-method-parameter %}

{% api-method-parameter name="fixed\_flag" type="string" required=false %}
공지일 경우 상단 고정 유무 
{% endapi-method-parameter %}

{% api-method-parameter name="content\_flag" type="string" required=false %}
게시글 형식 
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
    "rstMsg": "게시글이 수 되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "content_flag": 0,
    "fixed_flag": 0,    
    "title": "빨간당",
    "contents": "빨간당 소개 내",
    "only_vs" : {
                    "vs_count" : 3,
                    "vs_title" : ["제목1","제목2","제목3"],
                    "vs_image" : ["img1.jpg","img2.jpg","img3.jpg"],
                    "vs_start" : YYYY-MM-DD hh:mm:ss,
                    "vs_end" : YYYY-MM-DD hh:mm:ss
                    }, 
    "status_flag": 0
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/gallery/:gallery\_UUID/:content\_UUID" %}
{% api-method-summary %}
게시글 호출 
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
    "rstCode": 200,
    "content_flag": 0,
    "fixed_flag": 0,    
    "title": "빨간당",
    "contents": "빨간당 소개 내",
    "action_count" : {
                    "like" : 0,
                    "bad" : 0,
                    "police" : 0
                    },
    "only_vs" : {
                    "vs_count" : 3,
                    "vs_title" : ["제목1","제목2","제목3"],
                    "vs_image" : ["img1.jpg","img2.jpg","img3.jpg"],
                    "vs_start" : YYYY-MM-DD hh:mm:ss,
                    "vs_end" : YYYY-MM-DD hh:mm:ss
                    },    
    "register": "nob98",
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "view_count": 0,
    "regist_ip": "127.0.0.1",
    "status_flag": 0,
    "write_env": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/gallery/b948e2be-9b7a-4963-bcff-34cee7c2e38a/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

