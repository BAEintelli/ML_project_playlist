# Matrix Factorization + Cosine Similarity

- 노래는 협업필터링 방식을 통해 채우고, 태그는 Cosine 유사도를 구해서 채워넣는 방식으로 진행

- Technical Skills : Python, Implict, Pandas, Numpy

- **Matrix factorization with Implicit feedback - binary sparse matrix**


<img src="/Users/yoohowon/Desktop/Data_Science/melon_playlist/ML_project_playlist/Cosine_similarity/image/img1.png" width=100%>

- implicit 패키지의 Alternating Least Squares를 활용하여 노래 100곡을 채움

- **태그별 가중치를 적용하여 Cosine 유사도를 계산**

- Playlist X Tags 행렬에서 x, y, z는 플레이리스트의 태그 존재 유무를 표현

<img src="/Users/yoohowon/Desktop/Data_Science/melon_playlist/ML_project_playlist/Cosine_similarity/image/img2.png" width=50%>

- 각 플레이리스트별로 가중치로 나누어 정규화 함

<img src="/Users/yoohowon/Desktop/Data_Science/melon_playlist/ML_project_playlist/Cosine_similarity/image/img3.png" width=50%>

- 이후 행렬은 0과 1이 아닌, 0~1 사이의 실수값을 가지게됨
- 이후 Cosine Similarity Matrix를 이용해 Tag 10개를 치움

<img src="/Users/yoohowon/Desktop/Data_Science/melon_playlist/ML_project_playlist/Cosine_similarity/image/img4.png" width=100%>

- 노래 예측 순위 93위(93/101)
- Tag 예측 순위 16위 (16/101)
- 대회 연재 진행중

