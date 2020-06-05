# Machine Learning Project
## Melon Playlist Continuation
### Multilabel Classification
#### Song에서 Tag를 Tag에서Song을 예측하는 Multilabel Classification을 만들어 보자

## 1. song -> tag 예측
<img src = "multilabel.png">
  
  - row
    - song(train + test)
  - feature
    - 노래의 장르, 
    - 노래가 발매된 연도, 
    - 노래가 들어있는 플레이 리스트의 좋아요의 합, 
    - 노래가 전체 플레이리스트에 몇번 담겨 있었는지
  - multilabel
    - tag(train)  

## 2. tag -> song 예측
<img src = "multilabel.png">

  - row
    - tag(train + test)
  - feature
    - tag에 맵핑된 노래들의 장르의 총합 
  - multilabel
    - song(train)

## 3. 제출 결과
- 기본 파라미터
<img src = "첫번째,두번째 파라미터.PNG">
-  첫번째 제출
<img src = "score_1.PNG">