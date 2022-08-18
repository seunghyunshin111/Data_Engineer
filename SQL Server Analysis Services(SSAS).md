# SQL Server Analysis Services(SSAS)

- 데이터 아키텍처 : 데이터 가공 및 처리 작업 Process 
- 작업 위치 : Japan

→ 가공 처리를 모두 SSAS에서 할 경우, Power BI 내에서 Filter 조건 시, SSAS 로 [데이터 / 쿼리] 이동 후 가공 완료된 화면 최종 화면 업로드

→ 사용 목적에 따라, 해당 방법이 [좋을수도 / Import 및 다른 방식이 더 효율적일수도] 있어, 초기 "데이터 아키텍처" 설계가 중요하다.

<br>

- SSAS 퍼포먼스 상승을 위해 BI 내 / 데이터 용량 감소 등의 방법을 시도.
  - BI 내 Performance analyzer 기반 dax/차트 내 처리 속도 개선
  - 데이터 용량 감소 - 가급적 'yes/no' -> '0/1' 등 처리 (상세 작업 내용은 추가 정리 노트 확인)

- 그러나 기본적으로 SSAS 퍼포먼스 상승을 위해서는 상기 내용들 외에 SSAS 내 퍼포먼스 상승이 필요. (참조 링크 : [SQL Server Analysis Services Performance Tips (mssqltips.com)](https://www.mssqltips.com/sql-server-tip-category/154/analysis-services-performance/))