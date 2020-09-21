# EMAIL 전송 
ver 1.2

backend 로 이메일 발송을 요청합니다.

postman 참조
https://documenter.getpostman.com/view/4052929/TVCY6Bhh#34ecf972-9384-4847-b8d4-7308a1ffa5c9


## Template 종류 
- id : 설명 (전달값 key/value)
- sampleEmail : sample template (linkUrl/링크url)
- sampleEmail2 : sample template2(linkUrl/링크url)
- memberRegister : 회원 가입   (name/이름, memberType/회원타입  ) 
- memberApproval : 회원 승인 요청 (name/이름, memberId/회원아이디 , memberType/회원타입)
- memberResetPassword : 회원 비밀번호 초기화 (memberSeq/회원아이디, authCode/초기화인증코드) 
- memberEmailAuth : 메일인증 (memberSeq/회원아이디, authCode/인증코드, expireDate/만료시간)
- memberQnaRegister : 문의등록 (qnaSeq/문의아이디 , qnaTitle/문의제목, qnaContent/문의내용)
- memberQnaAnswer : 문의답변 (qnaSeq/문의아이디 , qnaTitle/문의제목, qnaContent/문의내용, ansTitle/답변제목, ansContent/답변내용)
  
## css 처리 
메일 수신자의 환경에 따른 변수가 크기 때문에 별도 css 파일 없이 메일 본문 내에 inline으로 style 지정 필요

## 첨부파일
### 허용 첨부 파일 종류  
이미지 파일 / pdf 파일 / ms office 일부 파일
### 첨부 방식 
API내에 파일 url 전달 -> base64 방식으로 변환 후 메일 첨부
첨부파일은 여러 개 첨부 가능


# send mail

### {{baseUrl}}/api/send-mail/send

메일 발송

## Headers

**Authorization** String **[required]** : 인증

  

## to

object **[required]** : 수신자 정보

-  **email** string **[required]** : 수신자 이메일

-  **name** string [optional] : 수신자 명

  

## from

object **[required]** : 발신자 정보

-  **email** string **[required]** : 발신자 이메일

-  **name** string [optional] : 발신자 명

## personalizations

array(object) [optional] : 수신 정보를 포함하는 배열

-  **to** array(object) : 수신자 명, 수신자email 주소를 포함하는 배열 수신자 명은 넣지 않아도 상관없다. 이 배열에 여러 명이 들어가 있는 경우 메일 받는 사람 모두 같은 수신 목록에 노출되기 때문에 고객에게 메일을 한꺼번에 보내고자 하는 경우 to 에 여러 명을 넣는 것보다는 to에 한 명을 넣고 personalization을 여러 번 추가 하는 것이 낫다.

**ex)**  *"to": [{ "email": "test01@yopmail.com", "name": "테스트01" } ]*

-  **subject** string [optional] : 메일 제목. personalizations 안에 제목을 쓰는 경우 수신자 별로 다른 제목 지정이 가능하다. 지정하지 않을 시 외부에 지정된 subject로 메일 제목이 정해진다.

**ex)**  *"subject": "[메일발송테스트] 안녕하세요 %NAME% 님"*

-  **substatutions** object [optional] : 수신자 별로 다른 내용을 넣고자 하는 경우 아이디 지정 후 선택된 아이디로 된 내용을 모두 내용으로 교체되어 전송된다. 아래 예제 대로 지정 시 메일 내용 및 제목에 *%ID%* 텍스트는 *test@yopmail.com* 로 내용이 대체되며, *%NAME%* 텍스트는 *홍길동*으로 대채된다.

**ex)**  *"substitutions" [optional] : { "%ID%": "test@yopmail.com", "%NAME%": "홍길동" }*

  

## subject

string **[required]** : 수신 되는 메일 제목

  

## emailTemplateId

String [optional] : 메일 템플릿 아이디. emailTemplateId / content 둘다 명시시 emailTemplateId를 우선시 하며 둘중 하나는 명시해야 한다

  

## content

String [optional] : 메일 본문. emailTemplateId / content 둘다 명시시 emailTemplateId를 우선시 하며 둘중 하나는 명시해야 한다

  

## filePathList

List[String]  [optional] : 첨부파일 경로

  
  

# ~~send mail multiple~~ [unused]

  
  

# Sendgird API

  
sendgrid API로 샌드그리드 서버로 바로 메일 발송을 요청합니다.
Azure Sendgrid 서비스의 경우 서비스 생성 후 Sendgrid 홈페이지로 이동하여 Key를 발급 받는 형식이라 가입 경로만 다를 뿐 실제 API-Key를 발급 받은 후 사용 방법은 일반 Sendgrid와 동일합니다.
postman 참조 : 
https://documenter.getpostman.com/view/4052929/TVCY6Bhh#34ecf972-9384-4847-b8d4-7308a1ffa5c9

  

## Headers

**Authorization** String **[required]** : 인증키. sendgrid 홈페이지에서 발급 후 삭제까지 별도 갱신 없이 사용가능

**ex)** Bearer {{Sendgrid API Key}}

  

## personalizations

array(object) **[required]** : 수신 정보를 포함하는 배열

-  **to** array(object) : 수신자 명, 수신자email 주소를 포함하는 배열 수신자 명은 넣지 않아도 상관없다. 이 배열에 여러 명이 들어가 있는 경우 메일 받는 사람 모두 같은 수신 목록에 노출되기 때문에 고객에게 메일을 한꺼번에 보내고자 하는 경우 to 에 여러 명을 넣는 것보다는 to에 한 명을 넣고 personalization을 여러 번 추가 하는 것이 낫다.

**ex)**  *"to": [{ "email": "test01@yopmail.com", "name": "테스트01" } ]*

-  **subject** string [optional] : 메일 제목. personalizations 안에 제목을 쓰는 경우 수신자 별로 다른 제목 지정이 가능하다. 지정하지 않을 시 외부에 지정된 subject로 메일 제목이 정해진다.

**ex)**  *"subject": "[메일발송테스트] 안녕하세요 %NAME% 님"*

-  **substatutions** object [optional] : 수신자 별로 다른 내용을 넣고자 하는 경우 아이디 지정 후 선택된 아이디로 된 내용을 모두 내용으로 교체되어 전송된다. 아래 예제 대로 지정 시 메일 내용 및 제목에 *%ID%* 텍스트는 *test@yopmail.com* 로 내용이 대체되며, *%NAME%* 텍스트는 *홍길동*으로 대채된다.

**ex)**  *"substitutions" [optional] : { "%ID%": "test@yopmail.com", "%NAME%": "홍길동" }*

  

## from

object **[required]** : 발신자 정보

-  **email** string **[required] ** : 발신자 이메일

-  **name** string [optional] : 발신자 명

## subject

string **[required]** : 수신 되는 메일 제목. personalizations 하위의 subject을 지정하지 않은 경우 이곳에 설정된 제목으로 메일이 발송된다

  

## content

array[object]  **[required]** : 메일 내용 본문

-  **type** string **[required]** : 메일 본문 mime type

**ex)**  *"type": "text/html"*

-  **value** string **[required]** : 메일 본문

**ex)**  *"value": "안녕하세요 %NAME%님<br> 본 메일은 메일 발송 테스트를 위해 %ID%로 전송된 메일입니다."*

  

## attachments

array[object]  [optional] : 첨부파일 추가

-  **content** string **[required]** : base64 방식으로 인코딩된 첨부 파일

-  **type** string [optional] : 첨부파일 mime 타입

-  **filename** string **[required]** :파일명
