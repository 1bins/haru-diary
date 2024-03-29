<img src="./public/haruDiary/intro.png">

<br/>

# 하루 하나, 감정다이어리
<a href="https://wonbin-haru-diary-project.web.app/" title="새 창으로 열기" target="_blank">https://wonbin-haru-diary-project.web.app/</a>
<blockquote>달력을 이용하여 하루에 한개 씩 나의 감정 일기장을 작성할 수 있는 리액트 앱입니다</blockquote>
<br/>

## 프로그래밍 언어 & 프레임워크
<p align="left">
  <img src="https://camo.githubusercontent.com/5d01ff32c8ff69d52e2e19e6f2d6c3dec2565398ab6a49d85451f46726224614/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f72656163742d3631444146423f6c6f676f3d7265616374266c6f676f436f6c6f723d7768697465" height="24px">
  <img src="https://camo.githubusercontent.com/64e3ed535b90fafa087dab829106804d76bd80a40ac55a542a4a51ff5dd440fa/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f48544d4c352d4533344632363f7374796c653d666c6174266c6f676f3d48544d4c35266c6f676f436f6c6f723d7768697465" height="24px">
  <img src="https://camo.githubusercontent.com/d6bf556d08b49b7bdeca54eaae43675eec1a6249b9f9ab589ed7b8c6393e182d/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f435353332d3135373242363f7374796c653d666c6174266c6f676f3d43535333266c6f676f436f6c6f723d7768697465" height="24px">
  <img src="https://camo.githubusercontent.com/a7eb481788fac742d0221a66cc189ac35c808e5389c353c8e5296c91cee336ce/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6a6176617363726970742d4637444631453f7374796c653d666c6174266c6f676f3d6a617661736372697074266c6f676f436f6c6f723d7768697465" height="24px">
</p>
- react-calendar: https://github.com/wojtekmaj/react-calendar<br>
- moment: https://www.npmjs.com/package/react-moment<br>
- react-router-dom: https://reactrouter.com/en/main
<br/>

### App
<img src="./public/haruDiary/app_1.png" width="100%">
<blockquote>수많은 이벤트 핸들러에 여러 상태 변경이 분산되면 가독성도 좋지 않을 뿐더러, 상태 변경 로직을 관리하는 것이 어려워지므로 useReducer를 사용하여 모든 상태 변경 로직을 옮겨 정리하였습니다.</blockquote>
<br/>
<img src="./public/haruDiary/app_2.png" width="100%">
<blockquote>dispatch액션을 통해 init, create, remove, edit함수를 생성하였습니다.</blockquote>
<br/>
<img src="./public/haruDiary/app_3.png" width="100%">
<blockquote>깊은 컴포넌트까지 값을 전달하기 위하여 createContext를 사용하였습니다.	</blockquote>
<br/>
<img src="./public/haruDiary/app_4.png" width="100%">
<blockquote>ReactRouterDom을 사용하여, SPA를 구현하였습니다.</blockquote>
<br/>

### HOME
<img src="./public/haruDiary/home.png" width="100%">
<blockquote>1) sort함수를 사용하여 해당하는 달의 가장 최신 날의 일기가 먼저 노출되도록 정렬하였습니다.
<br/>2) 일별과 월별 탭 클릭 상태를 알기 위해 tabs state를 설정하였습니다</blockquote>
<br/>

### MyCalendar
<img src="./public/haruDiary/calendar.png" width="100%">
<blockquote>1) 달력을 사용하기 위해 react-calendar를 사용하였고, 보다 쉽게 날짜 포맷을 사용하기 위해 moment.js를 사용하였습니다.
<br/>2) 달을 변경할 때 해당하는 달로 state를 변경하게 하는 함수를 작성하였습니다.
<br/>또한, 다음달과 이전달로 이동하게 될 경우 1일로 state가 고정되게 하였으며, 해당하는 달이 다시 이번달일 경우에는 오늘로 state가 고정되게 하였습니다.
<br/>3) diaryList의 데이터에 저장된 각 일기별 날짜와 react-calendar의 날짜들을 비교해 일치할 경우 달력 아래 점이 표시되게 구현하였습니다.</blockquote>
<br/>

### DiaryList
<img src="./public/haruDiary/diaryList_1.png" width="100%">
<blockquote>일별과 월별 탭을 클릭할 시 해당 탭의 name값을 가져와서 state를 true되게 만들어 주었습니다.</blockquote>
<br/>
<img src="./public/haruDiary/diaryList_2.png" width="100%">
<blockquote>true값에 따라 일별 리스트가 노출될지 월별 리스트가 노출될지 설정하였습니다.</blockquote>
<br/>

### DiaryEditor
<img src="./public/haruDiary/editor_1.png" width="100%">
<blockquote>쓰기와 수정 페이지는 동일 페이지이므로, 하나의 컴포넌트로 작성하였고, isEdit(boolean)을 통해 현재 쓰기 상태인지 수정 상태인지 구별되게 하였습니다.</blockquote>
<br/>
<img src="./public/haruDiary/editor_2.png" width="100%">
<blockquote>감정리스트를 담아 놓은 js를 호출하여 각각 하나의 EmotionItem 컴포넌트가 생성되게 하였습니다. 현재 감정 점수를 알기 위해 onClick={setEmotion}을 전달하였고, 또한 클릭한 감정을 알기 위해 emotion state와 클릭한 emotion.id를 비교해 일치하면 true가 반환되게 하였습니다.</blockquote>
<br/>

## 프로젝트 설명
### 오늘 하루의 기분과 일기를 작성할 수 있어요
<img src="./public/haruDiary/write_diary.gif">
<blockquote>오늘 작성한 일기가 없을 경우 일기 쓰기 버튼이 활성화돼요.<br>
작성한 일기가 있다면 해당 일기 아이템이 노출돼요.</blockquote>
<br>

### 작성된 일기가 있는 날에는 달력에 표시가 돼요
<img src="./public/haruDiary/calendar_check.png">
<br>

### 탭을 통해 일별과 월별로 작성된 일기 리스트를 볼 수 있어요
<img src="./public/haruDiary/dailyMonthly.gif" width="242px">
<br>

### 기록했던 일기를 수정/삭제 할 수 있어요
<img src="./public/haruDiary/editDelete_diary.gif" width="242px">
<br>

### 원하는 일자에 일기를 작성할 수 있어요
<img src="./public/haruDiary/choose_diary.gif">
<br>

### 한 달 간의 나의 감정 점수를 확인 할 수 있어요
<img src="./public/haruDiary/ratio.gif">
<blockquote>감정 점수는 1~3점을 긍정으로 보고, 해당 월 데이터를 기반으로 평균을 내요.</blockquote>
<br>

### 달력을 넘길때마다 해당 하는 달의 일기와 감정 점수를 볼 수 있어요
<img src="./public/haruDiary/prevNextMonth.gif">
<blockquote>달을 넘길 때 자동으로 매 달의 1일로 지정이 되고, 현재 달일 경우에는 자동으로 오늘로 지정이 돼요</blockquote>
