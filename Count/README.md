# Machine Learning Project
## Melon Playlist Continuation
### tag and song count
#### 노래에서 많이 언급된 태그를 유추하고, 태그에서 많이 언급된 노래를 찾아, 제출하여 보자.

- song에 매칭된 tags와 tag에 매칭된 songs를 기록한 데이터프레임 생성
  - 노래에 매칭된 태그들

    <img src = "https://user-images.githubusercontent.com/60168331/83352343-c3d95700-a385-11ea-8926-d9e2ead9cb7c.PNG">

  - 태그에 매칭된 노래들 
  
    <img src = "https://user-images.githubusercontent.com/60168331/83352345-c50a8400-a385-11ea-909d-ab289fa967d9.PNG">

- Val data
    - 제출해야할 데이터의 기본 모습
    - tag와 song이 몇 개씩만 채워져 있음
    - 해당 tag와 song을 각각 10개, 100개씩 꽉 채워야함
    <img src = "https://user-images.githubusercontent.com/60168331/83352346-c50a8400-a385-11ea-8027-f4729dd7b56d.PNG">

- song에서 tag 10개를 유추
   - playlist에 수록되어있는 노래들을 기준으로, 가장 많이 언급된 tag 10개를 생성
    <img src = "https://user-images.githubusercontent.com/60168331/83352347-c5a31a80-a385-11ea-8e97-073754c9206f.PNG">

- tag에서 song 100개를 유추
   - playlist에 수록되어 있는 태그들을 기준으로, 가장 많이 언급된 노래 100개를 생성
    <img src = "https://user-images.githubusercontent.com/60168331/83352348-c5a31a80-a385-11ea-95be-651a9869c52c.PNG">

- 그럼에도 불구하고 태그를 10개, 노래를 100개 못채운 데이터
  - tag에 연결된 song과 song에 연결된 tag가 각 10개, 100개가 안되는 playlist가 있음
  <img src = "https://user-images.githubusercontent.com/60168331/83352349-c63bb100-a385-11ea-96cd-6379593a22ac.PNG">

- playtitle에서 tag를 유추
  - playtitle에서 konlpy를 이용하여 명사만 추출하여 tag화
  <img src = "https://user-images.githubusercontent.com/60168331/83352350-c6d44780-a385-11ea-86f1-1e66aa12e4dd.PNG">

- 위의 1920개의 playlist를 tag에서 song을 100개, song에서 tag 10개를 채우고 난뒤에 다 못채운 playlist는 324개
  - 보면 굉장히 이상한 playtitle를 가지는 것 playlist가 있음
  - <img src = "https://user-images.githubusercontent.com/60168331/83352352-c6d44780-a385-11ea-9b59-6c48d3ab61d4.PNG">

- 324개의 playlist의 playtitle의 영문을 tag화
  - <img src = "https://user-images.githubusercontent.com/60168331/83352353-c76cde00-a385-11ea-9be7-2db3716f847d.PNG">

- 영어로된 tag들 중에 한글로 변경만 해주면 다시 태그가 붙을만한것이 있어 변경
  - 변경전
<img src = "https://user-images.githubusercontent.com/60168331/83352354-c76cde00-a385-11ea-87af-5da4463553bc.PNG">
  - 변경후
<img src = "https://user-images.githubusercontent.com/60168331/83352355-c8057480-a385-11ea-9c7b-6d833d41dd0d.PNG">

- 이렇게까지 했는데도 태그 10개, 노래 100개가 안되는 플레이리스트가 있음
  - tag가 10개가 아닌것
<img src = "https://user-images.githubusercontent.com/60168331/83352356-c8057480-a385-11ea-9478-48dc275a00bc.PNG">
  - song이 100개가 아닌것
<img src = "https://user-images.githubusercontent.com/60168331/83352357-c89e0b00-a385-11ea-81af-c8e0601256de.PNG">
  - 결국 Random으로 tag를 10개, song을 100개를 채움...

- 마지막으로 tag가 중복으로 들어가있는것 중복 제거
  
<img src = "https://user-images.githubusercontent.com/60168331/83352358-c89e0b00-a385-11ea-96d2-8bf01698def1.PNG">

- 위의 내용을 정리하자면
  - song에서 많이 언급된 tag를 예측하고, tag에서 많이 언급된 song을 예측하여 결과로 내놓았지만, 생각보다 tag가 10개, song이 100개가 되지 않는 playlist가 많았다. 그들은 playtitle를 이용하여 다시 tag를 10개, song을 100개 채웠으며, 마지막까지 채워지지 않는것은 random으로 추출하여 채우고 제출하였다. 
  - 위에서 설명이 길었지만, 그냥 그림으로 설명하자면 아래와 같다.     
<img src = "https://user-images.githubusercontent.com/60168331/83352362-c9cf3800-a385-11ea-8e96-be3e9c692c91.png">
  - 이렇게 보면 어려우니까 간단히 만들어 보긴했는데 별로인것 같다.
<img src = "https://user-images.githubusercontent.com/60168331/83352361-c936a180-a385-11ea-9748-7159113870c9.png">

- 최종 제출 결과 (5월 18일 제출일 기준)
  - 전체 순위 22위 (22/82)
  - song 단독 순위 62위 (62/82)
  - tag 단독 순위 7위 (7/82)
<img src = "https://user-images.githubusercontent.com/60168331/83352360-c936a180-a385-11ea-97e7-8b208f0dd029.png">

- 회고
  - Machine Learing 기법등이 들어가지 않은, 단순 tag의 count와 song의 count를 기반으로 tag와 song을 예측하였고, 결국 채워지지 않는 tag와 song이 있어서, 이들을 랜덤으로 채웠으나, 그럼에도 불구하고  의외로 tag에서 좋은 결과를 가져왔다.
  - 이를 기반으로 다른 Machine Learing 기법을 생각하여 제출하면 좋을듯 하다.