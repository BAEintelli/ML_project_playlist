### Just one Song & Tag

#### Tag와 Song이 없는 플레이리스트를 최소한 한개씩이라도 채워보자
- Step 1. 태그가 없는 플레이리스트 중, 노래는 있는 플레이리스트
- Step 2. 제목만 있는 플레이리스트
- Step 3. 태그, 노래, 제목이 모두 없는 플레이리스트
- Step 4. 노래가 없는 플레이리스트

#### Step 1. 태그가 없는 플레이리스트 중, 노래는 있는 플레이리스트
1. 노래들의 세부장르를 모두 추출한 뒤 가장 많이 언급된 세부장르 하나를 선택
2. 해당 세부장르와 함께 언급된 태그 중에 가장 많이 언급된 태그 하나를 추가

![세부장르별태그갯수](https://user-images.githubusercontent.com/60166693/83378470-bcf92580-a413-11ea-9fad-7d8e7a398a02.png)
![세부장르로태그채운것](https://user-images.githubusercontent.com/60166693/83378560-034e8480-a414-11ea-8afc-24013aacf6e6.png)

#### Step 2. 제목만 있는 플레이리스트
1. 명사와 형태소를 추출하고 그 명사와 형태소의 이름을 가진 태그를 추가

![명사 형태소 추출](https://user-images.githubusercontent.com/60166693/83378658-59232c80-a414-11ea-8b64-d409898fa896.png)
![명사, 형태소로 채운 플레이리스트](https://user-images.githubusercontent.com/60166693/83378671-64765800-a414-11ea-8944-bf509d6afe6d.png)


2. 모든 태그를 TF-IDF로 벡터화 시킨 후 제목과의 거리를 비교해 가장 가까운 태그 추가

![명사형태소로 못채운 플레이리스트](https://user-images.githubusercontent.com/60166693/83378722-88399e00-a414-11ea-8a8f-7c5eb01dd24b.png)
![TFIDF로 태그채운것](https://user-images.githubusercontent.com/60166693/83378764-b3bc8880-a414-11ea-8e7f-1f121381aa94.png)

#### Step 3. 태그, 노래, 제목이 모두 없는 플레이리스트
1. 전체 플레이리스트에서 가장 많이 언급된 태그를 추가

![세개 모두없는 플레이리스트](https://user-images.githubusercontent.com/60166693/83378783-cc2ca300-a414-11ea-8911-abf662b326eb.png)
![세개 모두없는 플레이리스트 채운것](https://user-images.githubusercontent.com/60166693/83378789-d5b60b00-a414-11ea-8341-2c84dc56f367.png)

#### Step 4. 노래가 없는 플레이리스트
1. 태그 별 가장 많이 언급된 상위 10개의 노래 추가

![노래가 없는 플레이리스트](https://user-images.githubusercontent.com/60166693/83378829-f2524300-a414-11ea-8392-733eacebd955.png)
![모두 채워진 데이터](https://user-images.githubusercontent.com/60166693/83378875-10b83e80-a415-11ea-8a5e-abfcbc8ab88f.png)

#### 그림으로 설명하자면
![그림](https://user-images.githubusercontent.com/60166693/83379155-d0a58b80-a415-11ea-82ae-fe0caf6004be.png)

#### 필요한 파일
- tag_list.txt (Train에 있는 모든 태그 리스트)
- genre_tag1.json (세부장르별 가장 많이 언급된 태그 1개씩 붙어있는 데이터프레임)
- testval_tag.txt (test와 validation에만 있는 태그 리스트)
- tagsong.json (태그 별 가장 많이 언급된 노래 10개)
