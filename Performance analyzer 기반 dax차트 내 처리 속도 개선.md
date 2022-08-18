## Performance analyzer 기반 dax/차트 내 처리 속도 개선

### 1.

![image-20220817101603925](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220817101603925.png)

주석 삭제 후,

![image-20220817101730506](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220817101730506.png)



**-2.12% 속도 개선**



---------------



### 주의

![image-20220817102117556](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220817102117556.png)



- 같은 페이지 Performance analyzer Refresh 해도, 이전과 처리 Duration (ms) 가 다름
- 근본적으로 데이터 리프레쉬 부분에서 파티션 등의 변화가 필요

-- 혹시 원본 및 가공 데이터 가져오는 시간대가 고정이라면,

- **데이터 리프레시 시간 : 서버가 가장 놀고 있는 새벽 시간대 추천 (오전 8시 등 부하 많을 시간대 제외..)**

---



### 2.

- **다중 VAR 처리의 함수식 VS 단일 측정값 여러개 // 성능 test**



### 결과

- ![image-20220818093236616](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220818093236616.png)
- VAR 사용 측정 값: 7666
- VAR 사용하지 않은 개별 측정 값: 1721
  - 최종 Return 값만 해당 측정 값 내부(6)에 삽입.

### 속도 **77.55% 감소**

-> 해당 내용 진짜 맞는지, 전체 등 꽤 여러 개 작업 개선해보면 좋을 듯.



---



## 슬라이서 필터 변경

![image-20220818100049350](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20220818100049350.png)

- 해당 슬라이서가 Duration (ms) 조금 작용하기 때문에, 이 페이지 Filters로 변경해보겠음
- 페이지 전체 Duration (ms) 감소 목적



---



## 성능 Test 시도 방법

- **각각 다른 보고서 모바일 게시 후, 다른 보고서 접속 시, QTD 수치?**  -> 일단은 2명이서 한 결과 10 이하로 확인 되나, 35까지 튄 경우도 있어.. 추가로 확인해보면 좋을 듯. (한 보고서 3명 동시 접속했을 때, Max 45 였음)

  - **이게 되면, 지점별로 보고서 나눌 것. (한 지점에 접속인원이 얼마 없을 것이기 때문)**

  

<위 방법이 안 된다면...>

- **제시 방법: 1인당 부하 QTD 수치 제시 및 접속 시간 정하여 사용자가 시간대별로 접속하도록 제안**

- AS 상에서 주석 전부 삭제해볼 것



[**Please refer to the following 5 Quick Ways To Speed Up Your Power BI Dashboard：**]([5 Quick Ways To Speed Up Your Power BI Dashboard | by ZhongTr0n | Towards Data Science](https://towardsdatascience.com/5-quick-ways-to-speed-up-your-power-bi-dashboard-41af7b46ea25)) [링크 참조]

- Use Integers Whenever Possible.

  - Data = 0/1  값 형식으로 변경 (yes/no 대신에)

  - ## 1. Use Integers Whenever Possible

    Searching through rows of numbers is way faster than searching through strings. So whenever possible, make use of integers. For example, it would be better to use 0 / 1 values instead of “*Yes/No*”. Or 1/2/3 instead of “*low/medium/high*”. And pay attention, because a digit is not necessarily an integer. You could have 1/2/3 as values, but they can still be considered strings. So always check the data format in the query editor.

- Remove Anything That Is Not Used.

  - **안 쓰는 테이블 삭제, 안 쓰는 컬럼, 행 삭제로 데이터 용량 줄이기!** 

  - Whether it’s tables, columns or rows, if you are not using it, it should not be in your dashboard. So during data (pre)-processing stick to what you need for your dashboard, everything else will only slow down performance.

- Stick To The Default Power Bi Widgets.

- Use Tabs.

- Use Top-N Rows In Tables.





