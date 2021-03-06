---
description: 게시물 댓글
---

# GALLERY\_REPLY

{% api-method method="post" host="https://api.tikita.ca" path="/v1/gallery/reply" %}
{% api-method-summary %}
댓글 입력 
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
{% api-method-parameter name="content\_uuid" type="string" required=true %}
게시글 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_uuid" type="string" required=true %}
갤러리 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_status" type="integer" required=true %}
리플 상태값\(정상/삭제/관리자 삭제\)
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_ip" type="string" required=false %}
작성 IP
{% endapi-method-parameter %}

{% api-method-parameter name="modify\_date" type="string" required=false %}
수정일 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
작성일 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_comment" type="string" required=false %}
리플내용 
{% endapi-method-parameter %}

{% api-method-parameter name="vs\_reply" type="integer" required=false %}
VS갤러리의 1:1일 경우 찬/반/중립 선택시 
{% endapi-method-parameter %}

{% api-method-parameter name="register" type="string" required=true %}
작성자 
{% endapi-method-parameter %}

{% api-method-parameter name="action\_count" type="object" required=false %}
좋아요/싫어요/신고 count 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_depth" type="integer" required=false %}
대댓을 위한 순서 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_group\_sort" type="integer" required=false %}
동일한 게시글 일련번호에 대한 순서 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_group\_id" type="string" required=false %}
게시글 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_uuid" type="string" required=false %}
댓글 일련번호 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
HTTP/1.1 201 Created
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

> 기본키

{% tabs %}
{% tab title="vs\_reply" %}
| default | 0 |
| :--- | :--- |
| 찬성  | 0 |
| 반대  | 1 |
| 중 | 2 |
{% endtab %}

{% tab title="reply\_status" %}
| default | 0 |
| :--- | :--- |
| 정 | 0 |
| 삭제  | 1 |
| 관리자삭제  | 2 |
{% endtab %}
{% endtabs %}

```text
{
    "gallery_uuid": UUID,
    "content_uuid": UUID,    
    "reply_uuid": UUID,        
    "reply_group_id": content_UUID,    
    "reply_group_sort": 0,    
    "reply_depth": 0,      
    "action_count" : {
                "like" : 0,
                "bad" : 0,
                "police" : 0
                },    
    "register": "nob98",
    "vs_reply": 2,
    "reply_comment": "리플내용",      
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "modify_date": YYYY-MM-DD hh:mm:ss,   
    "reply_ip": "127.0.0.1",
    "reply_status": 0
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/gallery/reply/:reply\_UUID" %}
{% api-method-summary %}
댓글 수정 
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
{% api-method-parameter name="reply\_status" type="string" required=false %}
리플 상태 
{% endapi-method-parameter %}

{% api-method-parameter name="modify\_date" type="string" required=false %}
수정일 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_comment" type="string" required=false %}
리플내용 
{% endapi-method-parameter %}

{% api-method-parameter name="vs\_reply" type="string" required=false %}
VS갤러리의 1:1일 경우 찬/반/중립 선택시 
{% endapi-method-parameter %}

{% api-method-parameter name="action\_count" type="object" required=false %}
좋아요/싫어오/신고 count 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rst_msg": "댓글이 수정 되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{ 
    "action_count" : {
                "like" : 0,
                "bad" : 0,
                "police" : 0
                },    
    "vs_reply": 2,
    "reply_comment": "리플내용",   
    "modify_date": YYYY-MM-DD hh:mm:ss,  
    "reply_status": 0
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/gallery/reply/:reply\_UUID" %}
{% api-method-summary %}
댓글 호출 
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
    "gallery_UUID": UUID,
    "content_UUID": UUID,    
    "reply_UUID": UUID,        
    "reply_group_id": content_UUID,    
    "reply_group_sort": 0,    
    "reply_depth": 0,      
    "action_count" : {
                "like" : 0,
                "bad" : 0,
                "police" : 0
                },    
    "register": "nob98",
    "vs_reply": 2,
    "reply_comment": "리플내용",      
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "modify_date": YYYY-MM-DD hh:mm:ss,   
    "reply_ip": "127.0.0.1",
    "reply_status": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

