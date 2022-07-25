# DW vs DB



| ** Data Warehouse (데이터 웨어하우스)** | **Data Base (데이터 베이스)**                          |                                                              |
| ------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------ |
| 목적                                        | 데이터 분석용                                          | 서비스용                                                     |
| 주요 기술                                   | OLAP(On-Line Analytical Processing) : 온라인 분석 처리 | OLTP(On-Line Transactional Processing) : 온라인 트랜잭션 처리 |
| 데이터 및 테이블 형태                       | subject-oriented, historical, 대용량, 반정규화         | application-oriented, real-time, 정규화                      |
| 성능 및 최적화                              | 정확성 < 속도 중시 읽기 최적화                         | 정확성 > 속도 중시 쓰기 최적화                               |
| 주요 제품                                   | Big Query, Amazon Redshift 등                          | MySQL, Oracle 등                                             |
