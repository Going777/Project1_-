# Project_Game Trend Insight

### 📍분석 주제 : 다음 분기에 어떤 게임을 설계해야 할 것인가?
---
### 📍사용 변수
* Name : 게임의 이름
* Platform : 게임이 지원되는 플랫폼의 이름
* Year : 게임이 출시된 연도
* Genre : 게임의 장르
* Publisher : 게임을 제작한 회사
* NA_Sales : 북미지역에서의 출고량
* EU_Sales : 유럽지역에서의 출고량
* JP_Sales : 일본지역에서의 출고량
* Other_Sales : 기타지역에서의 출고량
---
### 📍분석 흐름
1. 데이터 정제
2. Feature Engineering
3. 데이터 분석 및 시각화
4. 결론 도출
---
### 📍3. 데이터 분석 및 시각화 세부 토픽
#### 1) 연도별 게임 출고량에 트렌드가 존재하는가?
![image](https://user-images.githubusercontent.com/109488657/193433829-7b5e8c26-a929-4b24-a4a0-0a91abe7d880.png)

* 연도별 출시한 게임 출고량 현황 살펴봤을 때, 1996년에 전년도 대비 게임 출고량이 2배이상 상승했고, 그 이후 계속해서 증가하는 추세를 보이다가 2008,9년에 정점을 찍고나서 점차 하락하는 추세이다.
* 출고량이 많았다는 것은 그만큼 게임 수요가 많았다는 것으로 이해할 수 있다.
* `이를 바탕으로 2000년대 초,중반엔 게임 시장이 활발했지만, 점차 시장이 위축되고 있음을 추론할 수 있다.`
* 이런 상황에서 게임 출시를 앞두고 있기 때문에, 우리는 `최근` 게임 데이터 동향 분석이 굉장히 중요하다. (최근 데이터의 기준은 2014년부터의 데이터로 선정, 자세한 이유는 코드파일 참조)

#### 2) 국가별 출고량 변수 간 상관정도는 어떠한가?
![image](https://user-images.githubusercontent.com/109488657/193433860-8392afa2-7afd-4d2e-b5e2-34130e051fd5.png)
* 파란색으로 갈수록 변수 간 연관성이 높은 것
* 출고량 변수 간 상관관계표를 살펴봤을 때, 일본에서의 출고량을 제외하고 나머지 국가의 출고량 간의 상관정도는 꽤 높은 것으로 나왔다.
* 이를 토대로 일본을 제외한 북미, 유럽, 그리고 기타지역에서의 출고량 분포는 비슷하게 나올 것으로 예측된다.

#### 3) 장르별 게임 출고량은 어떠한가?
![image](https://user-images.githubusercontent.com/109488657/193433874-dcfa89de-daa3-4da8-ad17-d303d9261338.png)
* 전체 데이터 : Action - Shooter - Sports - Role-Playing 순서로 상위랭크
* 최근 데이터(2014년~) : Action - Sports - Shooter - Role-Playing의 순서로 상위랭크
* 약간의 순위변동만 있을 뿐, 상위에 랭크되는 장르는 변함이 없다. -> 다음에 출시하게 될 장르는 이 중 하나가되지 않을까
* `Action은 여전히 최근까지도 출고량이 가장 높은 장르이다.`
* `Sports장르가 최근들어 부상하고 있다.`

#### 4) 지역별(북미/유럽/일본/기타지역)로 선호하는 장르는 어떠한가?
![image](https://user-images.githubusercontent.com/109488657/193433898-3ea65cad-41a4-4b50-87f4-20f01fbeb3f0.png)
* 북미 : Shooter - Action - Sports - Role-Playing
* 유럽 : Action - Shooter - Sports - Role-Playing
* 일본 : Role-Playing - Action - Fighting - Misc
* 기타지역 : Action - Shooter - Sports - Role-Playing
* 위의 상관분석에서 추론했듯이 일본을 제외한 다른 국가들의 출고량 분포는 비슷하다.

#### 5) 국가별 출고량은 총 출고량 대비 어느정도인가?
![image](https://user-images.githubusercontent.com/109488657/193433918-92c666ae-b39d-408d-8382-2c44a4973717.png)
* 최근들어 북미시장은 하락하는 추세이고, 유럽시장은 꾸준하게 성장하는 추세이다.
* `일본 및 기타지역은 상대적으로 낮은 비중을 차지하고 있기 때문에 북미와 유럽지역에서 선호하는 장르의 게임을 출고하는 것이 바람직해 보인다.`
* 두 지역에서 선호하는 게임 장르는 Shooter와 Action 장르이다.
* 북미지역에서 선호도 1위가 Shooter이지만 2위인 Action과 큰 차이가 없고, 유럽지역에서의 선호도 1위가 Action 장르이기 때문에 종합적으로 고려했을 때, `다음 분기에 Action 장르의 게임을 출고하면 좋지 않을까`라고 생각한다.
* 이를 뒷받침하기 위해 통계적 가설검정을 실시했다.(자세한 내용은 코드파일 참조)
  * 가설검정결과, Action 장르의 게임 평균 출고량이 Shooter 장르의 게임 평균 출고량보다 높은 것을 알 수 있다.
  * 이를 근거로 `다음 분기에 Action 장르의 게임을 설계해야 한다`는 결론을 도출할 수 있다.
  * 그리고 `성장세 측면에서 유럽시장이 북미시장을 따라잡고 있기 때문에, 다음 분기에 유럽 시장을 타겟팅하는 것도 좋은 시도`로 보인다.
  
#### 6) 어떤 플랫폼을 통해서 Action 장르 게임을 발매하는 것이 효과적인가?
![image](https://user-images.githubusercontent.com/109488657/193433973-4b78b8f7-c9e0-435b-bf94-4eae17994958.png)
* 최근 Action 장르를 지원하는 플랫폼 중에서 가장 높은 비중을 차지하는 플랫폼은 PS4이다.
![image](https://user-images.githubusercontent.com/109488657/193433979-a776da03-d587-4325-95b4-c76d844436c2.png)
* PS4 플랫폼에서 출시한 게임 중 Action 장르의 비중이 가장 높다.
* Action 게임에 많은 공을 들이고, 나름의 전문적인 사양으로 게임을 지원하는 것으로 판단된다
* `Action 장르의 게임을 출시할 때 PS4 플랫폼을 활용하면 될 것`으로 보인다.

#### 7) 어느 제작회사와 협업하는 것이 효과적인가?
![image](https://user-images.githubusercontent.com/109488657/193434009-99eb97c2-ebe2-4294-b7a0-9da996b69804.png)
* Action 게임을 가장 많이 출시한 제작회사는 Namco Bandai Games이고 다음으로 Warner Bros. Interactive Entertainment이다.
* 그런데 Action 게임 출고량을 살펴보면 Warner Bros. Interactive Entertainment가 가장 높다.
* 이는 Warner Bros.사가 비록 Namco Bandai Games사보다 출시한 게임은 적지만 출고량은 더 많음, 즉 더 인기가 좋은 게임을 만들어냈다는 뜻으로 이해할 수 있다.
* 때문에 우리는 `Warner Bros. Interactive Entertainment와 손을 잡고 게임을 출고하는 것이 바람직`하다.
![image](https://user-images.githubusercontent.com/109488657/193434021-3e3bf97c-15b6-4005-a7fb-6b0e1aa5f643.png)
* Warner Bro. Interactive Entertainment사는 다양한 플랫폼을 고르게 사용한다(그중에서 우리가 필요로하는 플랫폼인 PS4는 1등)
* 대부분 Action 장르의 게임을 출고한다(94% 이상) -> Action 장르에 대한 전문성이 기대된다

### 📍4. 결론 도출(분석 결과)
* 장르 : Action
* 제작회사 : Warner Bros. Interactive Entertainment
* 플랫폼 : PS4
* 출고지역 : 유럽지역
