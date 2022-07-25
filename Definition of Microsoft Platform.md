# Definition of Microsoft Platform

<br>

# Server & DB



<img width="612" alt="Screen Shot 2022-07-25 at 9 04 59 PM" src="https://user-images.githubusercontent.com/57430754/180773966-42482785-e98b-4176-be94-04b7f7b66cc4.png">

*[DB Lists](https://azure.microsoft.com/ko-kr/products/category/databases/)

<br>

### ETL / ELT

→ ELT 시 고객사의 사용 편리함은 있으나, 결과적으로 처리 성능 저하 및 비용 증가로 ETL이 우수함

<br>

<br>

## Server = DB(Data Warehouse) + 가상공간(SSIS, SSAS, SSRS)

- Server 32GB도 부족한 편

<br>

**Microsoft SSIS(SQL Server Integration Services)는 데이터 웨어하우징을 위한 ETL(추출, 변환 및 로드) 패키지를 비롯하여 고성능 데이터 통합 솔루션을 작성하기 위한 플랫폼**

**SSAS - DAX 식 (Data Mart 를 ssas로 만든다.)**

**SSRS(SQL Server Reporting Services)에서는 모바일 보고서와 페이지를 매긴 보고서를 만들고 배포 및 관리하는 일련의 온-프레미스 도구와 서비스를 제공합니다**

**유지관리**

<br>

### **OLTP 기간계**

**클라우드 버전 SSIS (X) → ADF(Azure Data Factory)**

**클라우드 버전 etl 도구 → adp, azure synapse analytics, azure databrics**

**클라우드 버전 분석 도구 → Azure Analytics Service**

<br>

<br>

# Gateway

- Power BI Gateway / 방화벽 오픈
- Integration Runtime, IR, Self Hosted IR / 방화벽 오픈, 1433 Port, 433 Port를 오픈해야 한다. → 포트는 뚫리는데, 입력되는 것은 없다. / 인터넷이 되어야 함

### 기간계 서버 → ETL → Azure 서버 → Power BI

- IR

<br>

### 기간계 서버 → Power BI

- Power BI Gateway

<br>

### 기간계 서버 ←→ 기간계 서버(중계 서버=프록시 서버) → (Azure 서버) → Power BI

- 프록시 서버 : 보안을 위해 타사가 바로 DB에 대지 못하게 함
- Azure 전용선 : 인터넷이 안 되어야 함 → Data가 인터넷으로 나가는 문제가 있음

<br>

## Azure 서버 → Power BI

- 호환이 되기 때문에 Gateway 설치를 하지 않아도 된다.