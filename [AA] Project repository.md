#  Project Repository 

## Frontend Application
 
서비스명 | 개발언어 |  Repository Name | 주요기능 | 도메인
---|---|---|---|---
Public portal web | vuejs | public-web | Public portal web | www.skvrd.com
Public Admin web | vuejs | admin-web | Admin web | admin.skvrd.com
Private portal web | vuejs | vrd-web | Private portal web | vrd.skvrd.com
Private Admin web | vuejs | vrdadmin-web | Private Admin web | vrdadmin.skvrd.com


참고 : 도메인명은 임의의 값이므로 추후 확정시 수정. Private Admin Web 분리 여부는 미정

## Backend Application ( api.skvrd.com )

서비스명 | 개발언어 |  Repository Name | 주요기능 | 패키지명
---|---|---|---|---
Auth | java | auth-app | 회원인증 및 권한 | com.skgc.vrd.auth
Member | java | member-app | 회원,기업 관리 | com.skgc.vrd.member
Product | java | product-app | 소재,소재사,소재제품 관리 | com.skgc.vrd.product
Vitual R&D | java | vrd-app | 프로젝트,데이터셋,모델,시뮬레이션(Universal Model 포함) 관리 <span style="color:pink"> ( Public/Private 로 분리 가능성 검토)</span>  | com.skgc.vrd
Tech Support | java | tech-support-app | FAQ,QnA, Trouble Shooting, 지원요청, 매뉴얼 | com.skgc.vrd.techsupport
Notification | java | notification-app | 알림 및 메일링 기능 | com.skgc.vrd.notification
Admin | java | admin-app | Public Admin (민감정보 관련 관리 및 Audit 기능) | com.skgc.vrd.admin
File Manager | nodejs | file-app | 파일 업로드 및 다운로드 | -
Auto ML I/F | python | ml-app | ML I/F 및 evet handler | -
DevOps | - | devops | k8s 공통 설정 및 config 관리 | -

> ingress fanout은 repository name에서 *-app 접미사를 제외한 명칭 사용. 이와 관련된 구조는 별도 문서로 작성 예정
```
ex : GET api.skglobalchemical.com/member/users  사용자 전체 리스트 조회
```
