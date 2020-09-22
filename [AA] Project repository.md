#  프로젝트 레파지토리


## Frontend Application
 
서비스명 | 개발언어 |  Repository Name | 주요기능
---|---|---|---
Public portal web | vuejs | public-web | Public 포털 웹
Private portal web | vuejs | vrd-web | Private 포털 웹
Admin portal web | vuejs | admin-web | Admin 포털 웹


## Backend Application

서비스명 | 개발언어 |  Repository Name | 주요기능 | 패키지명
---|---|---|---|---
Auth | java | auth-app | 회원인증 및 권한 | com.skgc.vrd.auth
Member | java | member-app | 회원,기업 관리 | com.skgc.vrd.member
Product | java | product-app | 소재,소재사,소재제품 관리 | com.skgc.vrd.product
Vitual R&D | java | vrd-app | 프로젝트,데이터셋,모델,시뮬레이션(Universal Model 포함) 관리 <span style="color:pink"> ( Public/Private 로 분리 가능성 검토)</span>  | com.skgc.vrd
Tech Support | java | tech-support-app | FAQ,QnA, Trouble Shooting, 지원요청, 매뉴얼 | com.skgc.vrd.techsupport
Notification | java | notification-app | 알림기능 | com.skgc.vrd.notification
Admin | java | admin-app | Public Admin (민감정보 관련 관리 및 Audit 기능) | com.skgc.vrd.admin
File Manager | nodejs | file-app | 파일 업로드 및 다운로드 | -
Auto ML I/F | python | ml-app | ML I/F 및 evet handler | -
