## webapp request 
-  POST http://api.vrd-skgc.com/noti/pub
- eventType 및 userId 값으로 post 요청
- azure function endpoint 호출 후 결과로 eventId 수신
- response 데이터는 azure function 호출 응답결과인 eventId 를 반환
> Input
```
{
    "eventType": "TRAINING",
    "userId": "test@test.com"
}
```
> Output
```
{
    "eventId" : ""
}
```

## azure function request - event trigger
- azure-function-url: https://notifunc.azurewebsites.net/api/HttpTriggerTest 
- 임의의 eventId를 발행하여 event grid에 event publish( eventId 란 ML 작업에 대한 instance Id)
- redis cache에 eventId를 key로 해서 사용자식별ID 정보를 저장( ML 작업에 대해서 tagging 으로 사용자 식별이 가능하고 event grid에 tagging 정보를 수신 할 수 있다면 redis cache 프로세스는 제외)
Input
```
{
    "eventType": "TRAINING",
    "userId": "test@test.com"
}
```
Output
```
{
    "eventId" : ""  // 특정 작업에 대한 instance id. 테스트시에는 azure function에서 임시 uuid 값으로 return
}
```

## redis cache
> redis cache 스키마
```
{
   "eventId" : {
      "userId" : "test@test.com",
	    "eventType" : "TRAINING"
   }
}
```
## event grid
- topicEndPoint : 'https://notievent.koreacentral-1.eventgrid.azure.net/api/events'
```
{
    id: 2222,  // event id
    subject: 'VRD TEST EVENT',
    dataVersion: '2.0',
    eventType: 'VRD.ML.CompleteEvent',
    data: {
        desc : 'completed vrd ml....'
    },
    eventTime: '12121'
}
```

## azure function response - event handler
- event grid 로 부터 이벤트 수신
- event id로 redis cache 조회
- redis sse-topic 으로 event message publish

## redis pub/sub 
- redis.topic: sse-topic
> 메세지 스키마
```
{
  "eventId": "11",       // TRAINING, DEPLOY, TEST Request 요청시 발급받은 event id
  "eventStatus": "Y",        // Y : 성공 , N : 실패
  "eventDesc" : "",          // eventStatus 실패일때 실패 사유
  "eventType": "TRAINING",   // TRAINING, DEPLOY, TEST
  "userId": "test@test.com"  // 실적용시 사용자 식별ID로 대체
}
```
## SSE 이벤트 결과 수신
-  POST http://api.vrd-skgc.com/noti/sub/{id}
  
```
{
  "eventId": "11",       // TRAINING, DEPLOY, TEST Request 요청시 발급받은 event id
  "eventStatus": "Y",        // Y : 성공 , N : 실패
  "eventDesc" : "",          // eventStatus 실패일때 실패 사유
  "eventType": "TRAINING",   // TRAINING, DEPLOY, TEST
  "userId": "test@test.com"  // 실적용시 사용자 식별ID로 대체
}
