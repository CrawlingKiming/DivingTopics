
# 전체 코드 정리 

### Raw Data :

>SNS데이터 

>카드매출데이터

>서울 일별 평균 대기 오염 정보 

>일별 대기 오염 정보 2018_1 

>유동인구데이터


서울 일별 평균 대기 오염 정보와 일별 대기 오염 정보는 서울시 공공데이터이며 해당 데이터의 엑셀을 필터링을 이용해 해당되는 날짜만 남긴후 사용

## Code : 

### 전처리, Feature Extraction 관련 

#### ExtractStopwords
전반적인 SNS 데이터를 보고 앞으로의 데이터 가공방향을 가늠하는 코드이다. 
불용어를 판단하기 쉽게 코드가 짜여있으며, 
불용어를 과하게 제거해서도, 너무 적게 제거해서도 안 된다. 
때문에 원하는 수준까지 유도한 후 KoreanStopwords.txt 를 작성

#### Adjusting_SNS
한국어 자연어처리는 형태소 분석과정이 필수적이다. 
그러나 SNS 데이터의 양이 매우 많고 형태소 분석과정을 높은 RAM과 많은 시간을 요구함으로 이를 저장할 수 있는 방안이 필요하다. 

또한 SNS 결측치나 불용어 처리가 잘 되었는지, 형태소 분석 결과를 판단할 수 있는 코드이다. 

#### EDA_card_sales 
카드 매출 데이터를 가공하고 분석하는 코드이다. 
이상치를 발견하고 제거할 수 있으며, Plot을 통해 다양한 경향성을 판단해볼 수 있다.

### LDA Topic Modeling 관련 

#### Main_Run 
LDA를 train 하는 코드이다. 
이 코드를 실행하면 lda_trained.model을 비롯한 파일을 생성할 수 있다.
빠른 속도와 안전성을 위해 gensim LDA multicore 를 사용했다. 
또한 말뭉치 사전과 Document 말뭉치를 얻을 수 있다. 

#### Make_Dict 
Train 된 LDA를 가지고 Topic Model Vector를 추출하게 한다. 
또한 구현되는 ddict 은 dictionary 자료구조로 매우 편리한 접근성과 활용방안을 갖추고 있다. 

#### LDAvisualized 
LDA Topic은 시각화 하기 어렵다. 
이 코드는 pyLDAvis를 통해 topic에 대한 직관을 제공해주고, 도출된 Topic이 의미 있는지 판단할 수 있는 근거를 제공해주는 코드이다. 

### Data Analysis 관련 

#### Dictplot 
기본적인 Topic Vector 분석을 도와주는 코드이다. 
또한 구현된 결과를 보고 Topic Vector 구간 정보를 생성할 수 있다.
해당 정보는 ordernumpy, temnp_1 에 저장이 된다. 

#### Add_OrderNWeek 
평일, 휴일 데이터를 카드 매출 dataframe에 Topic Vecotr 구간 정보, 평일 / 휴일 정보 추가. 

#### DustPike 
Dust Pike는 미세먼지 농도 데이터를 이용해 기본적인 분석과 미세먼지 정보를 추출하여 Dataframe에 추가한다. 

#### Get_lever 
Get_lever 는 가장 핵심적인 시각화 및 데이터 분석 코드이다. 
이 코드에서 lever 는 Topic K 에 대한 상위 50% / 하위 50% 를 통해 추출된 비율을 이야기한다. 
이 코드는 가능한 거의 모든 방법을 동원해서 요인분석을 실시하며 시각화를 도와준다. 


##### 첨언

상기한 모든 코드들은 구동을 확인했습니다. 
혹시 추가적인 질문이나 의문사항은 언제든지 dkcho819@naver.com / 조동규로 문의주시면 됩니다. 
감사합니다. 




```python

```
