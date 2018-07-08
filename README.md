# make-schedule

> 시간표 자동 생성 웹서비스

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev
```

## 추가 정보

- 백엔드 API 서버 필요
1. DB에 시리얼나이즈 또는 JSON 형태로 값이 저장되어있다고 가정합니다.
2. 백엔드서버는 API요청 발생 시 json형태로 전달 합니다.
3. 백엔드의 요청은 아래와 같이 사용 가능합니다.
- URL 첫번째 인자값
- DATA 두번째 인자값(JSON)

 ``` bash
 this.$http.get('localhost:3000/getSchedule').then(res => {
     this.timeTables = res.data;
 });
 ``` 

- 추가정보

1. 백엔드에서는 아래와 같은 JSON 형식으로 값을 전달 합니다.
 ``` bash
 {
     name : "컴퓨터공학부",
     subject : [
         {
             label : "수학1",
             credit : 3,
             time : [[1,2,3,4],[1,2,5,6],[3,4,5,6]]
         },
         {
             label : "전산학기초",
             credit : 3,
             time : [[7,8,9,10],[7,8,11,12],[9,10,11,12]]
         },
         {
             label : "프로그래밍기초",
             credit : 3,
             time : [[13,14,15,16],[13,14,17,18],[15,16,17,18]],
         },
         {
             label : "하드웨어기초",
             credit : 3,
             time : [[1,2,3,4],[13,14,1,2],[3,4,13,14]]
         }
     ]
 }
 ```   
2. time의 값은 총 3가지 강의시간 경우의수를 모두 저장한 값이라 가정 합니다.(백엔드에서 강의시간 등록시 처리를 필요로 함)

3. 위 JSON에서 time에 저장되는값은 아래와 같이 시간표에서의 위치를 나타냅니다.

 ``` bash
      월  화  수  목   금 
1교시  1   9  17  25  33
2교시  2  10  18  26  34
3교시  3  11  19  27  35
4교시  4  12  20  28  36
5교시  5  13  21  29  37
6교시  6  14  22  30  38
7교시  7  15  23  31  39
8교시  8  16  24  32  40
 ```   


 