---
description: 회원정보
---

# MEMBER\_INFO

{% api-method method="post" host="https://api.tikita.ca" path="/v1/member/account" %}
{% api-method-summary %}
회원정보 입력 
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
{% api-method-parameter name="member\_uuid" type="string" required=true %}
회원 고유 UUID
{% endapi-method-parameter %}

{% api-method-parameter name="history" type="object" required=false %}
히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="detail\_info" type="object" required=false %}
민감정보 이름/성별/생년월일/전화번호 
{% endapi-method-parameter %}

{% api-method-parameter name="sns\_check" type="boolean" required=false %}
회원구분 일반/SNS 
{% endapi-method-parameter %}

{% api-method-parameter name="adult\_check" type="boolean" required=false %}
성인인증 
{% endapi-method-parameter %}

{% api-method-parameter name="personal\_check" type="boolean" required=false %}
본인인증 
{% endapi-method-parameter %}

{% api-method-parameter name="check\_date" type="object" required=false %}
가입일/최종로그인/비밀번호변경일 
{% endapi-method-parameter %}

{% api-method-parameter name="ad\_check" type="boolean" required=true %}
이벤트/광고 등 수신동의 
{% endapi-method-parameter %}

{% api-method-parameter name="child\_check" type="boolean" required=true %}
14세 미만 체크 
{% endapi-method-parameter %}

{% api-method-parameter name="level" type="integer" required=true %}
회원 등급 
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="integer" required=true %}
회원상태 유효/휴면/탈퇴 
{% endapi-method-parameter %}

{% api-method-parameter name="pwd" type="string" required=false %}
비밀번호 
{% endapi-method-parameter %}

{% api-method-parameter name="nick" type="string" required=true %}
닉네임 
{% endapi-method-parameter %}

{% api-method-parameter name="email\_auth\_check" type="boolean" required=true %}
이메일 인증 여부 
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
이메일 
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
    "rstMsg": "회 정보가 입력되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

> 기본키

{% tabs %}
{% tab title="email\_auth\_check" %}
| default | 0 |
| :--- | :--- |
| 미인증  | 0 |
| 인증  | 1 |
{% endtab %}

{% tab title="status" %}
| default | 0 |
| :--- | :--- |
| 정상\(유효\) | 0 |
| 휴면  | 1 |
| 정지  | 2 |
| 탈퇴  | 3 |
{% endtab %}

{% tab title="child\_check" %}
| default | 0 |
| :--- | :--- |
| 14세 이상  | 0 |
| 14세 미만  | 1 |
{% endtab %}

{% tab title="ad\_check" %}
| default | 0 |
| :--- | :--- |
| 광고 수 거부  | 0 |
| 광고 수신 동의  | 1 |
{% endtab %}

{% tab title="personal\_check" %}
| default | 0 |
| :--- | :--- |
| 본인인증\(X\) | 0 |
| 본인인증 완료  | 1 |
{% endtab %}
{% endtabs %}

```text
{
    "member_uuid": UUID,
    "email": "nob98@naver.com",
    "email_auth_check": 1,
    "nick": "수아짱",
    "pwd" : "1234",
    "status" : 0,   
    "level" : 1,    
    "child_check" : 0,    
    "ad_check" : 1,
    "check_date" : {
                    "join_date" : YYYY-MM-DD hh:mm:ss,
                    "login_date" : YYYY-MM-DD hh:mm:ss,
                    "password_date" : YYYY-MM-DD hh:mm:ss
                    },
    "personal_check" : 1,
    "adult_check" : 1,
    "sns_check" : 0,
    "detail_info" : {
                    "name" : "김지훈",
                    "ismale" : 1,
                    "birthday" : YYYY-MM-DD,
                    "phoneno" : "0000000000",
                },                
    "history" : {
                    "history_memo" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }    
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/member/account/:member\_uuid" %}
{% api-method-summary %}
회원정보 수정 
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
{% api-method-parameter name="email\_auth\_check" type="boolean" required=false %}
이메일 인증 체크 
{% endapi-method-parameter %}

{% api-method-parameter name="ad\_check" type="boolean" required=false %}
이벤트/광고 등 수신동의 
{% endapi-method-parameter %}

{% api-method-parameter name="history" type="object" required=false %}
히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="detail\_info" type="object" required=false %}
민감정보 이름/성별/생년월일/전화번호 
{% endapi-method-parameter %}

{% api-method-parameter name="adult\_check" type="boolean" required=false %}
성인인증 
{% endapi-method-parameter %}

{% api-method-parameter name="personal\_check" type="boolean" required=false %}
본인인증 
{% endapi-method-parameter %}

{% api-method-parameter name="child\_check" type="boolean" required=false %}
14세 미만 체크 
{% endapi-method-parameter %}

{% api-method-parameter name="level" type="integer" required=false %}
회원 등급 
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="integer" required=false %}
회원상태 유효/휴면/탈퇴 
{% endapi-method-parameter %}

{% api-method-parameter name="pwd" type="string" required=false %}
비밀번호 
{% endapi-method-parameter %}

{% api-method-parameter name="nick" type="string" required=false %}
닉네임 
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
    "rstMsg": "회원 정보가 수되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "nick": "수아짱",
    "pwd" : "1234",
    "status" : 1,   
    "level" : 1,    
    "child_check" : 0,    
    "ad_check" : 1,
    "personal_check" : 1,
    "adult_check" : 1,
    "detail_info" : {
                    "name" : "김지훈",
                    "ismale" : 1,
                    "birthday" : YYYY-MM-DD,
                    "phoneno" : "0000000000",
                },                
    "history" : {
                    "history_memo" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }    
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/member/account/:member\_uuid" %}
{% api-method-summary %}
회원정보 호출 
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
    "member_uuid": UUID,
    "email": "nob98@naver.com",
    "email_auth_check": 1,
    "nick": "수아짱",
    "pwd" : "1234",
    "status" : 0,   
    "level" : 1,    
    "child_check" : 0,    
    "ad_check" : 1,
    "check_date" : {
                    "join_date" : YYYY-MM-DD hh:mm:ss,
                    "login_date" : YYYY-MM-DD hh:mm:ss,
                    "password_date" : YYYY-MM-DD hh:mm:ss
                    },
    "personal_check" : 1,
    "adult_check" : 1,
    "sns_check" : 0,
    "detail_info" : {
                    "name" : "김지훈",
                    "ismale" : 1,
                    "birthday" : YYYY-MM-DD,
                    "phoneno" : "0000000000",
                },                
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
https://api.tikita.ca/v1/member/account/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/member/account/checkdate/:member\_uuid" %}
{% api-method-summary %}
최종로그인/비밀번호 변경일 업데이트 
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
{% api-method-parameter name="change\_date" type="string" required=true %}
변경일 
{% endapi-method-parameter %}

{% api-method-parameter name="check\_job" type="integer" required=true %}
로그인/비밀번호변경일 구분 
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
    "rstMsg": "날짜가 업데이트 되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
check\_job  - 0 : 로그인, 1 : 비밀번호 
{% endhint %}

```text
{
    "check_job": 0,
    "change_date" : YYYY-MM-DD hh:mm:ss
}
```



