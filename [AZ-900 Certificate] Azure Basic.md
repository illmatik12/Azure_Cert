[AZ-900 Certificate] Azure Basic

## 자본지출 (capital Expenditure, CapEx)
- 물리적 인프라를 구매하여 사용
- 서버 구매 후 서비스 운용
- 높은 초기 비용, 투자의 가치는 시간이 지남에 따라 줄어듬 (소모품)

## 운영 지출 (Operational Expenditure, OpEx)
- 필요에 따라 서비스나 제품을 구독
- 서비스에 필요한 제품을 즉시 구매
- 선결제 비용 없음, 사용량에 따라 지불(Pay-as-you-go)

## 소비기반 모델 (종량제)
- 선결제 비용 없음
- 고가의 인프라를 구매하고 관리 할 필요가 없음
- 필요에 따라 리소스를 추가 지불하고 사용 가능
- 더 이상 필요하지 않은 리소스에 대한 사용을 중지할 수 있음
- 사용한 만큼 결제


# IaaS, PaaS, SaaS 비교
- IaaS : 셀프서비스 포털, 프로비저닝 관리 컴퓨팅 인프라 제공, 
운영체제 부터 사용자가 관리 

- PaaS : application / data 
클라우드 제공자가 소프트웨어 응용프로그램을 구축,테스트,배포하기 위한 플랫폼을 제공
사용자는 운영체제, 플랫폼 관리 및 업데이트를 신경쓰지 않고 제품에 좀 더 집중함
운영체제게 접근할 수 없고 클라우드 제공자가 제공한 플랫폼에서만 서비스를 운영함. 
- SaaS : 클라우드 제공자가 응용프로그램을 제공 
사용자는 응용프로그램을 그대로 사용하고 데이터와 접근 관리만 가능 
사용자는 구독 모델로 사용

# 클라우드 모델 
Public cloud 
- 가장 많이 사용하는 클라우드 서비스 
- 클라우드 서비스 제공자 또는 호스팅 제공 업체가 소유 
- 특정되지 않은 사용자에게 리소스와 서비스를 제공 
- 보안된 네트워크 연결을 통해 액세스(인터넷)

Private Cloud 
- 클라우드 리소스를 조직에서 소유하고 관리/운영 
- 담당 조직은 데이터센터에 클라우드 환경을 만듦 
- 특정 사용자에게만 리소스와 서비스를 제공
- 제공되는 서비스의 운영을 책임지는 조직이 있음. 
- 보안된 네트워크를 통해 액세스 (사내망) 

Hybrid Cloud하이브리드 
- 공용 클라우드 + 사설
- 사내 데이터센터를 공용 클라우드로 확장
- 사설 클라우드의 단점을 공융 클라우드로 보완 
- 일반적으로 VPN 또는 전용선으로 연결
- 가장 유연한 모델
- 통합 관리 툴 필요 

# Azure 

## Region 
데이터센터 모음을 나타냄
사용자와 가장 가까운 지역에 리소스를 배포 가능
전 세계 55개 지역 140개국
리소스 배치시 지역 가용성에 유의
지역 독립적인 글로벌서비스 존재

## BCDR (Budisness continuity and disaster recovery)
Azure Region은 항상 쌍을 이루는 다른 지역이 있음.
데이터센터 간 300마일 이상의 분리를 선호 
일부 서비스의 경우 지역 쌍에 자동 복제를 제공 (Storage Account등) 

## Geography
- 데이터 상주 및 규정 준수 경계를 유지하는 개별 시장
일반적으로 둘 이상의 영역이 포함 됨
특정 지역 및 규정 준수 요구사항이 있는 고객은 데이터와 응용프로그램을 가까이에 두어야 함.
아메리카,유럽,아시아 태평양, 중동 및 아프리카로 분류 

## 가용성 옵션 
SLA 구분 

## 가용성 세트 
Update domain : 예약도니 유지 관리,성능,보안 업데이트는 업데이트 도메인을 통해 순서를 결정 
Fault domain : 데이터 센터의 여러 하드웨어에서 워크로드를 물리적으로 분리 

## 가용 영역 (Availability Zones) 
Azure 지역 내에서 물리적으로 위치를 구분
가용성 세트를 한 단계 끌어 올림
독립적인 전원, 냉각 및 네트워킹 기능을 갖춘 하나 이상의 데이터 센터를 포함
격리 경계 역할을 수행
한 가용 영역이 다운되면 다른 가용 영역이 계속작동
고가용성을 사용자가 관리 

## 재해 복구 (DR) 구현 
Region 1 -> site recovery -> Region 2 

## 리소스 그룹
동일한 수명주기를 가지는 리소스들의 묶음
리소스는 리소스 그룹을 이동할 수 있음. 
리소스는 하나의 리소스 그룹을 가짐
역할 기반 접근 제어(RBAC) 를 사용하여 리소스 그룹 레벨의 보안 유지 

## Azure Resource Manager
Azure를 관리하는 계층
리소스 또는 리소스 그룹을 생성, 구성, 관리, 삭제
리소스 조직화 및 자동화 
Azure AD를 통한 접근 제어 
Azure Portal, CLI, PowerShell, API 

## Azure Compute
Azure 에서 Compute 작업을 하는 서비스 
Web Server를 운영하거나 Application Server를 운영시 사용
기본적으로 Virtual Machine이 있음
사용자가 직접 프로세스에 관여 

- Azure Virtual Machine : IaaS의 대표적인 서비스
- VM Scale Sets - Azure VM Image를 이용하여 자동으로 확장 또는 축소 
- App Services - 사용자는 소스 파일만 업로드하면 알아서 동작하는 PaaS
- Func
Serverless computing 
# lab
https://microsoftlearningkoreanlab.github.io/

## Azure Container 서비스 
Azure Container Instances - Azure가 관리하는 Container Cluster에 Container Image를 업로드할 수 있는 PaaS서비스 

## Azure Kubernetes Service 
많은 수의 컨테이너를 관리하기 위한 Container Orchestrator. Azure VM에 Kubernetes Cluster를 구성해 주며, Master Node는 Azure에서 무료료 제공

## Azure Network
Azure에 사설 네트워크를 만들고 조작할 수 있는 서비스 
SDN 기반으로 동작하며 모든 네트워크는 격리됨.
Azure 가상 머신 등 가상 네트워크가 필요한 모든 리소스 구성 가능
On-premise와 연결하기 위한 기능 구현
부하 분산 장치를 이용하여 여러대의 서버로 부하 분산

* Azure Virtual Network - 논리적인 사설 네트워크를 구성할 수 있어 가상 머신과 같은 리소스간 보안 통신을 제공 
* Azure Load Balancder - 여러 대의 서버에 트래픽을 분산시켜 응용프로그램 또는 리소스에 대한 고가용성 액세스 제공
* VPN Gateway - On-primise 또는 다른 데이터센터로 네트워크를 확장할 수 있는 관리형 서비스로 고가용성을 지원 
* Application Gateway - 웹 응용프로그램에 대해 트래픽을 분산시켜 고가용성 액세스를 제공
* Azure CDN - 사용자에게 가장 가까운 POP에 정적 컨텐츠를 캐싱하여 웹 컨텐츠를 효율적으로 전달하는 분산 서버 네트워크 

# Storage Account
* Azure에서 데이터를 저장하고 관리할 수 있는 서비스 
* Blob(Container),File, Queue, Table로 이루어져 있음.
* Blob의 경우 비정형 데이터를 저장할 수 있는 Object Storage
* Filㄷs의 경우 SMB 3.0을 이용하여 가상 머신에 Mount가능 
* Blob에는 가상 머신의 DISK 파일도 저장 가능 

Object는 Storage가 Metadata가 관리. 
File system은 운영체제가 관리. 
## 데이터 범주
정형 데이터 : 행/열을 가지는 데이터 
반 정형화 데이터  : json, html
비정형 데이터  : PDF, JPG Word

## Azure Storage
- Blob - 비정형 데이터를 저장하는 스토리지 . REST 액세스 지원
- Files - SMB 및 REST액세스 지원, 가상 머신에 원격 스토리지로 mount 가능.
- Queue - 메시지를 저장하고 검색할 수 있음. 메시지는 비동기적으로 처리될 수 있음.
- Table - key-value 형식의 NoSQL 데이터 스토리지. 부하기반 동적 스케일링 지원.
Hot , Cool, Archive teer 존재 

## Azure Database 서비스 
Azure SQL Database
Azure Database for MySQL
Azure Database for PG

Azure Cosmos DB - 처리량과 스토리지를 탄력적이고 독립적으로 확장할 수 있는 NoSQL 관리형 서비스. 전세계에 분산을 손쉽게 구현 가능.

Azure Database Migration - 다운타임을 최소화하면서 여러 데이터베이스 엔진을 마이그레이션 할 수 있도록 설계된 완전 관리형 서비스. 이기종 데이터베이스 엔진 마이그레션도 지원하며 데이터만 마이그레이션 지원 (스키마는 별도 작업 필요) 


## Azure IoT 서비스 
Internet of Things 

* Azure IoT Central - IoT 리소스를 대규모로 쉽게 연결하고 모니터링 , 관리 완전 관리형 IoT SaaS 
* Azure IoT Hub - IoT 응용프로그램과 IoT 디바이스 간의 양방향 통신을 위한 중앙 허브 역할을 한다. 클라우드에서 호스팅되는 완전 관리형 서비스 


## Bigdata 

Azure SQL Data Warehouse - 엔터프라이즈 데이터 웨어하우스 
Azure HDInsight - Hadoop 파일시스템을 사용하는 완전 관리형 분석 서비스 
Azure Data Lake Analysis - 주문형 분산 작업 서비스 
Azure Databricks - Apache Spark 환경을 사용하여 AI 솔루션 빌드. 

# Machine Learning 
예측 모델 

Azure Machine Learning Service 
Azure Machine Learning Studio 

## Azure Serverless 서비스 
* 클라우드 서비스 공급자가 서버를 실행하고 머신의 리소스를 동적으로 관리하는 클라우드 컴퓨팅 실행 모델 
* 용량 단위 구매가 아닌 소비 단위 구매 
* 일반적으로 실행 횟수, 실행 시간 (CPU) , 실행 용량(Memory)을 기반으로 과금 됨.

* Azure Functions - 기본 플랫폼이나 인프라를 구성하지 않고 소스 코드를 실행할 수 있는 서비스. 이벤트 기반으로 동작
* Azure Logic App - 앱,데이터, 시스템 서비스를 통합하여 작업 또는 비즈니스 프로세스 및 워크플로를 자동화할 수 있는 서비스.
* Azure Event Grid - 균일 한 이벤트 소비를 위해 발행 - 구독 모델을 사용하는 완전 관리형 지능형 이벤트 라우팅 서비스 

## App Service Plan 
과금 단위 
### Web app 
웹 어플리케이션을 호스팅하는 완전 관리형 서비스 
code만 업로드 하거나 container를 이용하여 운영 


## Azure DevOps
개발과 운영을 결합 , 응용프로그램 품질을 지속적으로 제공하기 위한 방법론
CI/CD 툴 사용 

### Azure DevOps Service
Git 리포지터리, Pipeline, Kanban 보드
### Azure DevTest Labs 
낭비를 최소화하기 위해 셀프 서비스 

## Azure 관리 방법
### Azure Powershell
### Azure CLI 

### Azure Cloud Shell
Azure 에서 지원하는 Shell
스토리지 계정 필요
PowerShell / Bash 
Idle time out 

# Azure Marketplace

# Azure Advisor


# Azure 보안 

## Azure DDos Protection
## Azure Firewall
네트워크 리소스를 보호하기 위해 IP 또는 Domain 주소를 기반으로 접근 허용/거부를 할 수 있는 관리형 서비스 
## Network Security Group 
가상 네트워크에 있는 리소스에서 네트워크 트래픽을 필터링
기본 정책이 정의되어 있음. 
우선 순위를 지정할 수 있으며 Allow 또는 Deny 설정. 
Azure에서 지정한 Tag 기반 필터링
네트워크 인터페이스 또는 서브넷에 연결

## Application Security Group
가상 컴퓨터를 그룹화하여 네트워크 보안 그룹의 정책에 적용 
유사항 정책을 가지는 서버를 그룹화 
명시적인 IP 주소를 수동으로 관리하지 않아도 보안 정책 사용 가능
정책 간소화 

## Network 보안하기 
응용프로그램에 맞는 네트워크 보안을 구성할 수 있어야 한다.
가상 컴퓨터에는 운영체제 방화벽 또는 백신 등의 응용프로그램 보안
가상 네트워크에서는 네트워크 보안 그룹
인터넷 통신에서는 Azure 방화벽 또는 DDos 보호, WAF 등을 사용
이외 3rd party 제품 사용 고려 

# Azure 계정 보안 

## 인증 (Authentication)
User 또는 Service 계정 식별
정상적인 요청으로 액세스 자격 증명 획득 
애겟스 제어 규칙을 만들기 위한 기초 
## 권한 (Authorizatio) 
인증된 User 또는 Service의 액세스 수준 정의
액세스 할 수 있는 리소스와 함께 수행할수 있는 작업을 정의 

### Azure Active Directory 
클라우드 기반 ID 관리 및 접근 제어 서비스 

인증지원 
Single Signed On 
Application 관리 
B2B
B2C ID 서비스 
장비 관리 

## Azure Multi-Factor Authentication (MFA) 
인증을 위해 두 개 이상의 요소를 요구하여 시원 확인 
MFA를 이용하여 보안을 추가 제공 

# Azure Tenant 
Azure의 기준이 되는 환경을 의미하며 회사 또는 조직을 의미 
Azure에 접근할 수 있는 사용자 또는 서비스는 Tenant 내에 존재
모든 구독은 Tenant 내에 존재
모든 리소스 그룹과 리소스는 구독 내에 존재


## Azure Key Vault 
중요한 데이터를 암호화하여 저장하고 필요할 때 액세스 하는 서비스 
접근 제어를 통해 안전한 권한 관리와 로깅 
저장 가능한 유형 

- 인증 값 
- 문자 열 
- 인증서 
- 하드웨어 보안 모듈(HSM Hardware Secure Module)

## Azure Information Protection (AIP)
레이블을 적용하여 문서 또는 전자메일을 분류하고 보호 

## Azure Advanced Thread Protection (ATP)
지능형 위협, 손상된 ID 및 악의적인 내부자 작업을 식별, 탐지 및 조사하기 위한 클라우드 기반 보안 솔루션 

# 거버넌스 방법론 

## Azure 정책 이니셔티브 
* 이니셔티브 정의 


## Azure Role Base Access Control(RBAC)
* Azure 리소스에 권한을 설정하여 접근 제어 관리 
* 특정 리소스에 특정 작업만 하도록 구성 가능
* 리소스가 RBAC를 사용할 경우 리소스간 접근 제어 구성 가능
* 내장된 기본 정책이 있음 
 소유자 
 기여자
 읽기 전용
* 추가 비용 없이 사용 


## Azure 리소스 잠금 
리소스를 삭제하거나 수정하는 것을 방지하는 기능
사용자의 실수를 방지할 수 있음
소유자가 리소스 잠금을 설정할 시 기여자는 리소스 잠금을 조작할 수 없음
readonly
delete 

## Advisor Security assistance 
기존에 azure 정책에 정의된 정책을 위반하는지 모니터링

## Azure Blueprint 
Azure 리소스를 다시 만들고 즉시 적용할 수 있는 재사용 가능한 환경 정의를 만듬


# 모니터링과 리포팅 
## Monitor 
Azure에서 모니터링 할 수 있는 리소스들의 지표 모음
Azure에 리소스를 만든 즉시 모니터링 데이터 수집
수집된 모니터링 데이터를 기반으로 알람 설정 등을 할수 있음. 

## Tag 
Azure 리소스에 Key-value 형식의 tag 추가 
tag를 기반으로 리소스를 그룹화 

## Azure Service Health 
개인화된 대시보드 , 사용자 소유 리소스에 이슈가 있을시 알람을 주는 서비스


## 응용프로그램 및 서비스 모니터링
분석 
알림 
시각화 - Power BI 활용 
통합 

# 규정준수 
CJIS (형사법 보안 정책)
HIPAA(건강 보험 이식성 및 책임 Act)
CSA STAR(Cloud Security Alliance Security, Trust & Assurance Registry)
ISO/IEC 27018(국제 표준화 기구)
GDPR(유럽 정보 보호법)
NIST(미국 국내 표준 및 기술) 


# Azure 비용 계획과 관리 
## Enterprise 
Azure 서비스를 협상한 금액을 지불하여 서비스 구매 (계약 단위 청구/일반적으로 매년) 
## Web Direct 
고객이 직접 Azure Web 사이트를 통해서 서비스 구매 (월 단위 청구) 

## Cloud solution providers 
CSP 업체를 통한 Azure 서비스 구매(월 청구 단위 / CSP 업체가 결제 및 청구 진행)

## 무료 구독 

## 비용에 미치는 요소
리소스 유형
서비스 
위치 : 지역별로 가격이 다름.

# 청구 영역 
대역폭은 데이터 센터의 인바운드 데이터 전송은 무료 

# 비용 계산기 

# Azure TCO 계산기 
On-premise의 인프라를 Azure로 마이그레이션 할 때의 비용 절감 예측 도구



# SLA (Service License Agreements )
가용성에 대한 보장 정책 설명 
Azure 제품 및 서비스에 대한 별도의 SLA가 적용 
SLA 미준수시 보상도 진행. 


복합 SLA  (ex : APP(99.95) x Data base (99.94) = 99.94% )

## 응용프로그램 SLA 디자인
워크로드 및 사용파악
사용 패턴 계획 
MTTR 및 MTBF 예상
RPO 및 RTO 설정
워크로드 가용성 대상 결정
SLA 이해

단일리전? 멀티리전? 멀티클라우드? 

## Azure Preview 
Private 
Public 

기존 서비스의 Preview
새로운 서비스를 통한 미리보기 

preview => GA 
General Availability
새로운 기능이 평가되고 테스트 
버그 및 라이프사이클을 통해 활성 및 해결
일반 가용성은 모든 azure 고객에게 성공적으로 테스트된 제품을 제공 



