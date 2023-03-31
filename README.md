# ESG Grade EDA

## Summary

- 최근 ESG 관련 지표에 관심을 가지는 기업과 투자자들이 많아지는 추세이며, 통해 ESG가 기업의 지속가능성 및 장기적인 가치 창출을 평가하는 중요한 기준이 된다는 연구도 있다. 하지만, 비효율적 경영이라는 부정적인 견해도 있는 실정이다.
    
    해당 프로젝트에서 ESG 평가 등급이 시간에 따라 어떻게 변화하고 있는 지 분석해보고, 등급의 변화가 주가나 제무정보와 같은 다른 데이터와 상관이 있는지를 분석하고, KOSPI200 KOSPI200ESG 지수를 비교하여 분석하였다.
    
- 분석 과정
    - 활용 데이터 선정 및 수집
    - ESG 등급 현황 분석
    - KOSPI200과 KOSPI200ESG 지수 비교 분석
    - 연도, ESG 등급 별 주식 가격 분석
    - 연도, ESG 등급 별 재무제표 분석
    - 상관분석

- 연도별 ESG종합 등급을 분석했을 때, 매년 기업체 수가 증가하는 것으로 보아 기업들의 ESG 활동에 대한 관심이 커지고 있는 것으로 보인다.
    연도별, ESG등급별 주가를 분석했을 때, 대체로 높은 ESG등급을 받은 경우에 주가도 높게 나타나는 경향이 있다.
    연도별, ESG등급별 재무제표를 분석했을 때, ESG등급과 재무제표는 상관성이 없는 것으로 보인다.


## Team member

|팀원|역할|
|:---:|---|
|[조현준(팀장)](https://github.com/chohj118)|데이터 수집 · 전처리 · 시각화(코스피200 기업 주가), PPT, 발표|
|[이혜빈](https://github.com/dkssudgb)|데이터 수집 · 전처리 · 시각화(코스피200 기업 ESG지수)| 
|[박성용](https://github.com/mols3131d)|데이터 수집 · 전처리 · 시각화(재무제표, 코스피200 개별 종목 ESG 평가 전처리)| 
|[노나은](https://github.com/better-noh)|데이터 수집 · 전처리 · 시각화(ESG 평가등급, 네이버 ESG 관련 뉴스기사)| 
|이주민|데이터 수집 · 전처리 · 시각화(코스피200), PPT|


---


# 1. 개요


## 소개
기업의 KCGS ESG 등급을 통해 기업의 주식가격과 재무제표를 분석하고, KOSPI200과 KOSPI200ESG 지수를 비교하여 분석하는 프로젝트


## 배경
- 최근 ESG 관련 지표에 관심을 가지는 기업과 투자자들이 많아지는 추세이며, 다양한 연구를 통해 **ESG가 기업의 지속가능성 및 장기적인 가치 창출을 평가하는 중요한 기준**이 된다고 보고있다.
- ESG 평가 등급과 다른 평가 지표와의 비교를 통해 인사이트를 도출해보기 위해 주제를 선정하였습니다.


### 선행연구

- 황성준 and 오상희. (2021). [코스피 200 ESG 지수의 종목변경에 대한 시장반응](https://www.kyungnam.ac.kr/riim/5339/subview.do?enc=Zm5jdDF8QEB8JTJGYmJzJTJGcmlpbSUyRjg5MCUyRjk1NzIwJTJGYXJ0Y2xWaWV3LmRvJTNGcGFnZSUzRDElMjZzcmNoQ29sdW1uJTNEJTI2c3JjaFdyZCUzRCUyNmJic0NsU2VxJTNEJTI2YmJzT3BlbldyZFNlcSUzRCUyNnJnc0JnbmRlU3RyJTNEJTI2cmdzRW5kZGVTdHIlM0QlMjZpc1ZpZXdNaW5lJTNEZmFsc2UlMjZwYXNzd29yZCUzRCUyNg%3D%3D). 지역산업연구, 44(4), 241-262.
    - 위 연구는 한국거래소(KRX) 코스피 200 ESG 지수 편입과 퇴출에 대한 주가반응 분석하였다.
    - 기업의 평균초과수익률과 코스피 200 ESG 지수 구성종목편입 유무를 보았을 때, 편입의 경우 유의한 양의 관계를 나타낸 반면, 퇴출은 음의 관계를 나타냈다.
    - 위 연구에서는 ESG 성과에 대한 시장의 부정적인 인식 전환과 기업들의 ESG 개선 활동 유도를 기대하였다.
- 황성준. (2022). [기업의 ESG 활동과 주가동조성](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002876301). 전산회계연구, 20(2), 83-101.
    - 위 연구에서는 2018년~2021년의 코스피, 코스닥의 12월 결산기업을 연구표본으로 설정하여 ESG 활동 성과와 시장수익률 및 산업수익률의 변동성의 영향 관계에 대해 실증분석하였다.
    - 기업의 ESG 활동은 주가동조성과 유의한 양(＋)의 관련성이 있고, ESG 활동 기업은 개별기업의 고유정보가 주가에 충분히 반영되어 정보효율성이 높았다.
    - 위 연구에서는 ESG를 수행하는 기업은 주가에 충분한 정보가 반영된 것으로 보았다.
    
    
### 기대효과
ESG 등급과 관련된 데이터를 분석하여 기업 평가에 적절한지에 대해 인사이트를 도출

# 2. 분석

## 활용 데이터 선정 및 수집

- 활용 데이터
    | 이름 | 설명 | Method | Source |
    | --- | --- | --- | --- |
    | KCGS ESG Rating | 한국ESG기준원 ESG등급 데이터<br>- 기간 : 2011년~2018년 |Web Scraping|[KRX 정보데이터시스템](https://data.krx.co.kr/contents/MDC/HARD/hardController/MDCHARD050.cmd#none)|   
    | KRX KOSPI 200 Index Components | KRX KOSPI 200 지수 구성종목 정보<br>- 기간 : 2010-06-30~2018-06-31<br>- 매년 06월 말일과 12월 말일에 대한 데이터 | Download | [KRX 정보데이터시스템](http://data.krx.co.kr/contents/MDC/MDI/mdiLoader/index.cmd?menuId=MDC0201010106) |
    | KRX KOSPI 200 Index Components Stock Price | KRX KOSPI 200 지수 구성종목의 주식가격 데이터<br>- 기간 : 2011년~2018년 | API | [FinanceDataReader](https://github.com/financedata-org/FinanceDataReader) |
    | DART corpCode | 금융감독원 고유번호 | API |[금융감독원 고유번호](https://opendart.fss.or.kr/guide/detail.do?apiGrpCd=DS001&apiId=2019018)|
    | DART company | 금융감독원 공시정보 기업개황 | API | [금융감독원 공시정보 기업개황](https://opendart.fss.or.kr/guide/detail.do?apiGrpCd=DS001&apiId=2019002) |
    | FSC FinaStatInfo | 금융위원회 기업재무정보 (요약재무제표)<br>- 기간 : 2011년~2018년 | API | [금융위원회 기업 재무정보](https://www.data.go.kr/tcs/dss/selectApiDataDetailView.do?publicDataPk=15043459) |
    | KRX KOSPI 200 Index Price | 한국거래소 KOSPI 200 지수 가격 데이터<br>- 기간 : 2010-06-31~2022-06-31 | Download | [KRX 정보데이터시스템](http://data.krx.co.kr/contents/MDC/MDI/mdiLoader/index.cmd?menuId=MDC0201010105) |
    | KRX KOSPI 200 ESG Index Price | 한국거래소 KOSPI 200 ESG 지수 가격 데이터<br>- 기간 : 2010-06-31~2022-06-31 | Download | [KRX 정보데이터시스템](http://data.krx.co.kr/contents/MDC/MDI/mdiLoader/index.cmd?menuId=MDC0201010105) |


## EDA

### `KCGS ESG Rating`

- 2011년~2018년 기준, ESG종합 등급별 평균 기업체 수 확인

    분석한 기간 중 **대다수의 기업체가 B등급**으로 **약 80%의 비중을 차지**했다.
    
    **[Fig 2-1]**  
    2011년~2018년, ESG종합 등급별 평균 기업체 수  
    ![[Fig 2-1] 2011년~2018년, ESG종합 등급별 평균 기업체 수](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-1.png)
    
- 2011년~2018년 기준, ESG종합 등급 추이

    ESG종합 등급을 받는 기업체 수는 매년 증가 추세를 보이며,  **매년 ESG종합 등급에서 B등급을 받은 기업체 수가 많다**는 것을 알 수 있다.
    
    **[Fig 2-2]**  
    2011년~2018년, ESG종합 등급 추이  
    ![[Fig 2-2] 2011년~2018년, ESG종합 등급 추이](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-2.png)

- 2011년~2018년 기준, E(환경) 등급 추이

    매년 E(환경) 등급에서 B등급을 받은 기업체 수가 많으며, **2017년 유일하게 S등급을 받은 기업체 1곳이 등장**했다.

    **[Fig 2-3]**  
    2011년~2018년 기준, E(환경) 등급 추이  
    ![[Fig 2-3] 2011년~2018년 기준, E(환경) 등급 추이](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-3.png)

- 2011년~2018년 기준, S(사회적구조) 등급 추이

    매년 S(사회적구조) 등급에서 **B등급을 받은 기업체 수가 많다**.

    **[Fig 2-4]**  
    2011년~2018년, S(사회적구조) 등급 추이  
    ![[Fig 2-4] 2011년~2018년, S(사회적구조) 등급 추이](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-4.png)

- 2011년~2018년 기준, G(지배구조) 등급 추이

    매년 G(지배구조) 등급에서 **B등급을 받은 기업체 수가 많다**.

    **[Fig 2-5]**  
    2011년~2018년, G(지배구조) 등급 추이  
    ![[Fig 2-5] 2011년~2018년, G(지배구조) 등급 추이](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-5.png)



### `KOSPI 200 Index VS KOSPI 200 ESG Index`

- 연도별 종가 비교

    KOSPI 200 지수와 KOSPI 200 ESG 지수의 종가가 거의 유사하게 나타나는 것을 볼 수 있다.
    
    이는 KOSPI 200 ESG 지수가 KOSPI 200 기업들 중 ESG 등급이 우수한 기업들을 기준으로 산출했기 때문으로 보인다.
    
    **[Fig 2-6]**  
    `KOSPI 200 Index VS KOSPI 200 ESG Index` 종가
    ![[Fig 2-6] `KOSPI 200 Index VS KOSPI 200 ESG Index` 종가](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-6.png)
    

- 연도별 등락률 비교

    두 지수 간의 등락률 또한 매우 유사하게 움직이는 것으로 보인다.
    
    **[Fig 2-7]**  
    `KOSPI 200 Index VS KOSPI 200 ESG Index` 등락률  
    ![[Fig 2-7] `KOSPI 200 Index VS KOSPI 200 ESG Index` 등락률 ](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-7.png)



### 연도, ESG 등급별 주가

- 종목별로 주식의 가격 규모가 다르기 때문에 종목 별로 Min-Max Scaling 적용 후 분석하였다.
- 대체로 등급이 높을 때 주가가 높은 것으로 보이는데, 상대적으로 ESG가 관심이 높은 시기인 2017년 이후 더 경향이 큰 것으로 보인다.
    
    **[Fig 2-8]**  
    연도, ESG 등급별 주가 - ESG종합 등급  
    ![[Fig 2-8] 연도, ESG 등급별 주가 - ESG종합 등급](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-8.png)
    
    **[Fig 2-9]**  
    연도, ESG 등급별 주가 - E(환경) 등급  
    ![[Fig 2-9] 연도, ESG 등급별 주가 - E(환경) 등급](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-9.png)
    
    **[Fig 2-10]**  
    연도, ESG 등급별 주가 - S(사회적구조) 등급  
    ![[Fig 2-10] 연도, ESG 등급별 주가 - S(사회적구조) 등급](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-10.png)
    
    **[Fig 2-11]**  
    연도, ESG 등급별 주가 - G(지배구조) 등급  
    ![[Fig 2-11] 연도, ESG 등급별 주가 - G(지배구조) 등급](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-11.png)
    
    

### 연도, ESG 등급별 재무제표

- 매출과 영업이익 등 높은 등급(A+, A)의 경우가 더 높은 것으로 보인다.
    
    **[Fig 2-12]**  
    연도, ESG 등급별 기업매출금액 - ESG종합 등급  
    ![[Fig 2-12] 연도, ESG 등급별 기업매출금액 - ESG종합 등급](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-12.png)
    
    **[Fig 2-13]**  
    연도, ESG 등급별 기업영업이익 - ESG종합 등급  
    ![[Fig 2-13] 연도, ESG 등급별 기업영업이익 - ESG종합 등급](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-13.png)


- 종목 별로 Min-Max Scaling 적용

    하지만, 종목 별로 MinMax 스케일링을 적용한 데이터로 보았을 때, 차이는 미미한 것으로 보여,  
    위의 경우는 높은 등급에 상대적으로 큰 규모의 회사들이 많이 분포하여 나타난 것으로 보인다.

    - 기업매출금액
    
        **[Fig 2-14]**        
        연도, ESG 등급별 기업매출금액 - ESG종합 등급 (Min-Max Scaling)  
        ![[Fig 2-14] 연도, ESG 등급별 기업매출금액 - ESG종합 등급 (Min-Max Scaling)](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-14.png)

    - 기업영업이익
    
        **[Fig 2-15]**  
        연도, ESG 등급별 기업영업이익 - ESG종합 등급 (Min-Max Scaling)  
        ![[Fig 2-15] 연도, ESG 등급별 기업영업이익 - ESG종합 등급 (Min-Max Scaling)](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-15.png)

        
### 연도, ESG 등급별 주가, 재무제표 상관계수

ESG등급 간의 양의 상관관계가 있는 것으로 보이지만, 종가나 제무재표 데이터와는 상관관계가 거의 없는것으로 보인다.

- heatmap

    **[Fig 2-16]**  
    연도, ESG 등급별 주가, 재무제표 상관계수 - heatmap  
    ![[Fig 2-16] 연도, ESG 등급별 주가, 재무제표 상관계수 - heatmap](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-16.png)

- regplot

    **[Fig 2-17]**  
    연도, ESG 등급별 주가, 재무제표 상관계수 - regplot  
    ![[Fig 2-17] 연도, ESG 등급별 기업영업이익 - ESG종합 등급 (Min-Max Scaling)](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-17.png)

- p-value

    **[Fig 2-18]**  
    연도, ESG 등급별 주가, 재무제표 상관계수 - p-value  
    ![[Fig 2-18] 연도, ESG 등급별 주가, 재무제표 상관계수 - p-value](https://github.com/mols3131d/ESG_Grade-EDA/blob/main/fig/md/Fig2-18.png)

# 결론

## 분석 결과

- 연도별 ESG종합 등급을 분석했을 때, 매년 기업체 수가 증가하는 것으로 보아 기업들의 ESG 활동에 대한 관심이 커지고 있는 것으로 보인다.
- 연도별, ESG등급별 주가를 분석했을 때, 대체로 높은 ESG등급을 받은 경우에 주가도 높게 나타나는 경향이 있다.
- 연도별, ESG등급별 재무제표를 분석했을 때, ESG등급과 재무제표는 상관성이 없는 것으로 보인다.


---

# 부록

## data 폴더의 파일 설명
- ESG_KOSPI200_ca.csv : 코스피200 기업들의 연도별 ESG등급
- KOSPI200.csv : 코스피200 지수
- KOSPI200_ESG.csv : 코스피200 기업의 ESG 지수
- KOSPI_ESG_MERGE.csv : 코스피200 지수와 코스피200 기업의 ESG 지수 데이터를 병합
- ESG_KOSPI200_ca.csv : 코스피200 기업의 ESG 등급

## 참고자료
- https://esg.krx.co.kr/contents/02/02020000/ESG02020000.jsp
- http://www.cgs.or.kr/business/esg_tab01.jsp
- http://data.krx.co.kr/contents/MDC/MDI/mdiLoader/index.cmd?menuId=MDC0201010105&idxCd=1&idxCd2=180
- http://data.krx.co.kr/contents/MDC/HARD/hardController/MDCHARD050.cmd#none
- http://www.cgs.or.kr/business/esg_tab04.jsp?pg=%7B%7D&pp=10&skey=&svalue=&sfyear=2021&styear=2021&sgtype=&sgrade=#ui_contents
