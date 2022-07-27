# Azure & ADF & SSAS & Power BI

- ADF: Azure Data Factory (Azure Cloud's ETL Service)
- SSAS: Server Analysis Services (Visual Studio 2019)
  - 현재 Analysis가 2019까지 설치되어 있기 때문에, Visual Studio도 2019년도로 설치

# Azure

1. 리소스 그룹 만들기
2. 스토리지계정 만들기
3. 컨테이너 생성
4. 만든 컨테이너에 excel파일 업로드
5. 만든 Server에 sql데이터베이스 만들기
6. 서버 방화벽 설정
7. 클라이언트 ip 추가 + Azure 서비스 및 리소스가 이 서버에 액세스할 수 있도록 허용 "예"
8. 데이터 팩터리 만들기
9. Analysis Services만들기
10. ssms에서 데이터 테이블 생성
11. 데이터 팩토리에 azure data factory열기
12. 왼쪽 관리 선택
13. 통합 런타임 새로만들기 -> 자체 호ㅅ팅
14. 만약 나중에 다시 할거면 ir(자체 호스팅)은 지우고 다시 까는게 좋음
15. 빠른설치 클릭
16. 연결된 서비스 -> 새로만들기 Azure Blob Storage, Azure Sql Database
17. 만든이로 이동
18. 데이터 세트 Azure Blob Storage -> excel
19. 파이프 라인 새파이프 라인 데이터복사
20. 매개변수 까지 완료 후 디버그
21. 모두게시
22. vs(Visual Studio) 실행
23. analysis services 테이블 형식 프로젝트 선택
24. 데이터 원본에서 데이터 원본가져오기
25. 데이터 불러와서 수정
26. 오른쪽에 솔루션 탐색기에서 솔루션 아래 마우스 우클릭후 서버이름에 azure analysis services에 만든 서버이름 복붙후 확인
27. 우클릭후 배포

