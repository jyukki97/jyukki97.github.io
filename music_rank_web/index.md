# [Project] 음원 순위 웹 - Music Rank web


**Flutter, Flask를 이용해 만든 음원 순위 웹**

<!--more-->

# 음원 순위 웹 - Music Rank web

- **지니, 벅스, 멜론, 바이브, 플로 5가지 사이트를 크롤링하여 얻은 순위를 평균내어 새로운 음원 순위를 만들어 보여주는 웹**
- **Heroku Flask 서버를 사용**



## 요구사항 

### 음원 순위

- ✅ 5가지 사이트에서 보여주는 1 ~ 100위 까지의 음원들을 각각 평균내어 보여 새로운 순위로 보여줍니다.
  - 매번 데이터를 가져올 때마다 크롤링을 할 수는 없으므로 매일 아침 7시에 크롤링하여 PostgreSQL에 크롤링한 데이터를 저장하는 방식을 사용

___

### 반응형 웹

- ✅ 큰 데스크톱 화면과 모바일 화면이 다르게 동작하도록 만듦

___

## 결과물 

### [음원 순위 웹](https://jyukki97.github.io/music_web)

- Heroku 서버를 계속 켜두기 싫어서 Sleep 상태에서 깨어나는 시간이 필요. 로딩시간 1분소요
