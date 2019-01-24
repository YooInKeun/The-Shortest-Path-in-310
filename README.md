The-Shortest-Path-in-310
=========================

Dynamic Map on @100(Team Project)
---------------------------------

<br/>

## 프로젝트 소개

![310](https://user-images.githubusercontent.com/41741539/51649799-3c2d4c80-1fc9-11e9-8776-226841371363.png)

### 기본 주제 : "The Shortest Path in 310" 
### (중앙대학교 310관 건물에서 최적의 경로 찾기)

&nbsp;&nbsp;중앙대학교 310관 건물에는 강의실이 많고, 그만큼 많은 학생들이 수업을 듣는다. 이때 310관 내의 요일별, 시간대별 유동인구를 고려해서 **엘리베이터나 계단과 같이 현재 갖추어진 이동 수단으로 갈 수 있는 최적의 경로와 그 시간**을 구하는 것을 목표로 한다. 예를 들어, 7층의 강의실에서 수업이 끝나고 점심 시간에 지하 4층에 있는 뚜레쥬르를 가고자 한다고 가정하자. 이때 그 날, 그 시간대에 7층에서 지하 4층으로 갈 수 있는 최적의 경로와 시간을 구하는 것이다. 경로의 대략적인 예시로 "(7층에서 모든 엘리베이터에 사람들이 많으므로) 7층에서 1층까지 A구역에 있는 계단을 이용해 내려간다 -> (1층에서 계단으로 지하 4층을 가는 것보다 C구역에 있는 엘리베이터를 이용하는 것이 빠르므로) 1층에서 지하 4층까지 C구역에 있는 엘리베이터를 이용해 내려간다"와 같은 상황이 있다.

<br/>

### 추가 주제 : "Improving the Inefficiency of Means of Transportation"
### (이동 수단의 비효율적인 부분 개선하기)

&nbsp;&nbsp;이동 수단의 효율적이지 못한 부분을 개선하기 위한 방법을 찾고, 임의의 위치에 엘리베이터를 설치할 수 있다면 어느 위치에 설치하는 것이 가장 효율적일지에 대해 문제를 해결하고자 한다. 이때 비효율성 문제는 주로 엘리베이터의 운용 방법에 초점을 둘 것이다.

<br/>

### 전제조건

① 특정 시간의 강의 인원은 강의 시작 전 15분, 종료 후 15분 동안 영향을 준다.

② 학생 각각의 시간표를 알 수 없으므로, 연강이나 공강 등의 불특정 상황을 배제한다.

③ 강의 인원은 시작 전과 종료 후, 무조건 엘리베이터를 이용하려 시도한다. 

<br/>

## 구현 방법

### 자료구조

![default](https://user-images.githubusercontent.com/41741539/51649861-6c74eb00-1fc9-11e9-83c5-f27ca7f240f4.png)

```
- Data Structure : 부분 방향성 그래프

- Node : 교차점, 엘리베이터 및 계단

- Subordinate  Node: 강의실 등 특정 시설

- Edge : 길
```

<br/>

### 강의 인원 데이터

![default](https://user-images.githubusercontent.com/41741539/51649864-6d0d8180-1fc9-11e9-8240-f074967f18b6.png)

```
- CSV 파일로 가공하여 저장

- 2차원 배열 형태로 저장

- UP, DOWN Table로 세분화

 (UP Table : 1층에서 올라가는 인원 / DOWN Table : n층에서 1층으로 내려오는 인원)
```

<br/>

### 알고리즘

```
- Algorithm : 다익스트라 알고리즘
```

<br/>

### 엘리베이터 이동 시간 공식

![default](https://user-images.githubusercontent.com/41741539/51650531-e7d79c00-1fcb-11e9-9e81-714c2673bec3.png)

```
- 총 x번 정차하고, n층간 이동에 소요되는 시간

- 엘리베이터 이용의 여러 경우의 수를 실측하고, 해당 데이터를 통해 공식 유도
```

<br/>
