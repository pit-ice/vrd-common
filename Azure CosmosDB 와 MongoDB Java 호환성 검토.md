# Azure CosmosDB 와 MongoDB Java 호환성 검토
Azure Cosmos DB에서 MongoDB API를 제공하므로 MongoDB API 기준으로 개발시 코드 변경없이 호환 가능함
## [Azure Cosmos DB에서 Spring Data MongoDB API를 사용하기](https://docs.microsoft.com/ko-kr/azure/developer/java/spring-framework/configure-spring-data-mongodb-with-cosmos-db?context=/azure/cosmos-db/context/context)

1. Azure Cosmos DB 생성 
> ![](https://docs.microsoft.com/ko-kr/azure/developer/java/spring-framework/media/configure-spring-data-mongodb-with-cosmos-db/create-cosmos-db-01.png)
2. Azure Cosmos DB for MongoDB API 선택

> ![](https://docs.microsoft.com/ko-kr/azure/developer/java/spring-framework/media/configure-spring-data-mongodb-with-cosmos-db/create-cosmos-db-02.png)

3. Azure Cosmos DB에서  Connection string 정보 조회

> ![](https://docs.microsoft.com/ko-kr/azure/developer/java/spring-framework/media/configure-spring-data-mongodb-with-cosmos-db/create-cosmos-db-06.png)

---
4. Java Application 개발 하기(Spring Boot 기준)
> pom.xml 에 mongodb dependency 추가
```
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-mongodb</artifactId>
		</dependency>
```


> application.yaml 파일내에 접속정보 추가
```
spring:
  data:
    mongodb:
      database: wingtiptoysmongodb
      uri: mongodb://wingtiptoysmongodb:AbCdEfGhIjKlMnOpQrStUvWxYz==@wingtiptoysmongodb.documents.azure.com:10255/?ssl=true&replicaSet=globaldb
```

> Java 이외의 다른 언어와의 호환성으로 고려하여 JSON 형태로 저장
```
String json = "{ 'name' : 'lokesh' , " +
                "'website' : 'howtodoinjava.com' , " +
                "'address' : { 'addressLine1' : 'Some address' , " +
                              "'addressLine2' : 'Karol Bagh' }" +
                            "}";

DBObject dbObject = (DBObject)JSON.parse(json);

collection.insert(dbObject);
```
