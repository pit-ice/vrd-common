# Sendgird API 

Azure Sendgrid 서비스의 경우 서비스 생성 후 Sendgrid 홈페이지로 이동하여  Key를 발급 받는 형식이라 가입 경로만 다를 뿐 실제 API-Key를  발급 받은 후 사용 방법은 일반 Sendgrid와 동일합니다.

## Headers
**Authorization** String   **[required]** :  인증키.  sendgrid 홈페이지에서 발급 후 삭제까지 별도 갱신 없이 사용가능
**ex)** Bearer {{Sendgrid API Key}}

##  personalizations
 array(object)  **[required]**  : 수신 정보를 포함하는 배열
 - **to** array(object) : 수신자 명, 수신자email 주소를 포함하는 배열 수신자 명은 넣지 않아도 상관없다. 이 배열에 여러 명이 들어가 있는 경우 메일 받는 사람 모두 같은 수신 목록에 노출되기 때문에 고객에게 메일을 한꺼번에 보내고자 하는 경우 to 에 여러 명을 넣는 것보다는 to에 한 명을 넣고 personalization을 여러 번 추가 하는 것이 낫다.
**ex)**   *"to": [{ "email": "test01@yopmail.com",  "name": "테스트01" } ]*
 - **subject** string [optional] : 메일 제목. personalizations 안에 제목을 쓰는 경우 수신자 별로 다른 제목 지정이 가능하다. 지정하지 않을 시 외부에 지정된 subject로 메일 제목이 정해진다.
 **ex)**  *"subject": "[메일발송테스트] 안녕하세요 %NAME% 님"*
- **substatutions** object [optional]  :  수신자 별로 다른 내용을 넣고자 하는 경우 아이디 지정 후 선택된 아이디로 된 내용을 모두 내용으로 교체되어 전송된다. 아래 예제 대로 지정 시 메일 내용 및 제목에 *%ID%* 텍스트는 *test@yopmail.com* 로 내용이 대체되며, *%NAME%* 텍스트는 *홍길동*으로 대채된다.
 **ex)**  *"substitutions" [optional] : { "%ID%": "test@yopmail.com", "%NAME%": "홍길동" }*

## from 
object **[required]** : 발신자 정보 sendgird 인증 아이디가 무료 도메인(gmail.com 등) 인 경우는 인증 아이디 왜 다른 아이디로 메일 발신 주소 변경 시 오류
 - **email** string **[required] ** : 발신자 이메일
 -  **name** string [optional] : 발신자 명  
 
## subject
string **[required]**  :  수신 되는 메일 제목.  personalizations 하위의 subject을 지정하지 않은 경우 이곳에 설정된 제목으로 메일이 발송된다

## content
array[object] **[required]** : 메일 내용 본문
- **type** string **[required]** : 메일 본문 mime type 
**ex)** *"type": "text/html"*
- **value** string **[required]** : 메일 본문
**ex)**  *"value": "안녕하세요 %NAME%님<br> 본 메일은 메일 발송 테스트를 위해 %ID%로 전송된 메일입니다."*

## attachments
array[object] [optional]  : 첨부파일 추가
- **content** string **[required]** : base64 방식으로 인코딩된 첨부 파일 
- **type** string [optional] : 첨부파일 mime 타입
- **filename** string **[required]** :파일명



# send mail
### {{baseUrl}}/api/send-mail/send
단일 메일 발송
## Headers
**Authorization** String   **[required]** :  인증

## to
object **[required] ** : 수신자 정보 
 - **email** string **[required] ** : 수신자 이메일
 -  **name** string [optional] : 수신자 명  

## from 
object **[required] ** : 발신자 정보 sendgird 인증 아이디가 무료 도메인(gmail.com 등) 인 경우는 인증 아이디 왜 다른 아이디로 메일 발신 주소 변경 시 오류
 - **email** string **[required] ** : 발신자 이메일
 -  **name** string [optional] : 발신자 명  
 
## subject
string **[required]**  :  수신 되는 메일 제목

## content
String **[required]** : 메일 본문

## filePathList
List[String] [optional]  : 첨부파일 경로


# send mail multiple
### {{baseUrl}}/api/send-mail/send-multiple
여러 개의 메일 발송
## Headers
**Authorization** String   **[required]** :  인증

##  personalizations
 array(object)  **[required]**  : 수신 정보를 포함하는 배열
 - **to** array(object) : 수신자 명, 수신자email 주소를 포함하는 배열 수신자 명은 넣지 않아도 상관없다. 이 배열에 여러 명이 들어가 있는 경우 메일 받는 사람 모두 같은 수신 목록에 노출되기 때문에 고객에게 메일을 한꺼번에 보내고자 하는 경우 to 에 여러 명을 넣는 것보다는 to에 한 명을 넣고 personalization을 여러 번 추가 하는 것이 낫다.
**ex)**   *"to": [{ "email": "test01@yopmail.com",  "name": "테스트01" } ]*
 - **subject** string [optional] : 메일 제목. personalizations 안에 제목을 쓰는 경우 수신자 별로 다른 제목 지정이 가능하다. 지정하지 않을 시 외부에 지정된 subject로 메일 제목이 정해진다.
 **ex)**  *"subject": "[메일발송테스트] 안녕하세요 %NAME% 님"*
- **substatutions** object [optional]  :  수신자 별로 다른 내용을 넣고자 하는 경우 아이디 지정 후 선택된 아이디로 된 내용을 모두 내용으로 교체되어 전송된다. 아래 예제 대로 지정 시 메일 내용 및 제목에 *%ID%* 텍스트는 *test@yopmail.com* 로 내용이 대체되며, *%NAME%* 텍스트는 *홍길동*으로 대채된다.
 **ex)**  *"substitutions" [optional] : { "%ID%": "test@yopmail.com", "%NAME%": "홍길동" }*


## to
object **[required] ** : 수신자 정보  
 - **email** string **[required] ** : 수신자 이메일
 -  **name** string [optional] : 수신자 명  

## from 
object **[required] ** : 발신자 정보 sendgird 인증 아이디가 무료 도메인(gmail.com 등) 인 경우는 인증 아이디 왜 다른 아이디로 메일 발신 주소 변경 시 오류
 - **email** string **[required] ** : 발신자 이메일
 -  **name** string [optional] : 발신자 명  
 
## subject
string **[required]**  :  수신 되는 메일 제목

## content
String **[required]** : 메일 본문

## filePathList
List[String] [optional]  : 첨부 파일 경로
