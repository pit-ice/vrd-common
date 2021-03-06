#  Project Repository 

## Frontend Application
 
서비스명 | 개발언어 |  Repository Name | 주요기능 | 도메인
---|---|---|---|---
Public portal web | vuejs | web-public | Public portal web | www.skvrd.com
Public Admin web | vuejs | web-admin | Admin web | admin.skvrd.com
Private portal web | vuejs | web-vrd | Private portal web | vrd.skvrd.com
Private Admin web | vuejs | web-vrdadmin | Private Admin web | vrdadmin.skvrd.com


참고 : 도메인명은 임의의 값이므로 추후 확정시 수정. Private Admin Web 분리 여부는 미정

## Backend Application ( api.skvrd.com )

서비스명 | 개발언어 |  Repository Name | 주요기능 | 패키지명
---|---|---|---|---
Auth | java | api-auth | 회원인증 및 권한 | com.skgc.vrd.auth
Member | java | api-member | 회원,기업 관리 | com.skgc.vrd.member
Product | java | api-product | 소재,소재사,소재제품 관리 | com.skgc.vrd.product
Vitual R&D Lab | java | api-vrdlab | 프로젝트,데이터셋,모델,시뮬레이션(Universal Model 포함) 관리 <span style="color:pink"> ( Public/Private 로 분리 가능성 검토)</span>  | com.skgc.vrd.vrdlab
Tech Support | java | api-tech-support | FAQ,QnA, Trouble Shooting, 지원요청, 매뉴얼 | com.skgc.vrd.techsupport
Notification | java | api-notification | 알림 및 메일링 기능 | com.skgc.vrd.notification
Admin | java | api-admin | Public Admin (민감정보 관련 관리 및 Audit 기능) | com.skgc.vrd.admin
File Manager | nodejs | api-file | 파일 업로드 및 다운로드 | -
Auto ML I/F | python | api-ml | ML I/F 및 evet handler | -
DevOps | - | devops | k8s 공통 설정 및 config 관리 | -

> ingress fanout은 repository name에서 *-app 접미사를 제외한 명칭 사용. 이와 관련된 구조는 별도 문서로 작성 예정
```
ex : GET api.skglobalchemical.com/member/users  사용자 전체 리스트 조회
```
