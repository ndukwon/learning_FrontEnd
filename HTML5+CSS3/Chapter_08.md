## 08. 레이아웃을 위한 스타일
1. CSS와 박스모델
	- block VS inline: 혼자서 한줄을 차지 or not
		- block:
			```
			<p>, <h1> ~ <h6>, <ul>, <ol>, <div>, <blockquote>, <form>, <hr>, <table>, <fieldset>, <address>
			```
		- inline:
			```
			<img>, <object>, <br>, <sub>, <sup>, <span>, <input>, <textarea>, <label>, <button>
			```
	- Box 모델: margin, border, padding, content 영역 존재
	- width / height: 가로 / 세로 크기
		- 설정 단위: px(픽셀), cm(센티미터), %(부모 기준 백분율), auto(컨텐츠의 양에 따라 결정, default)
	- display: 요소의 화면 배치 방법
		- block: 요소들을 블록 레벨로 지정
		- inline: 요소들을 인라인 레벨로 지정
		- inline-block: 요소들의 배치는 인라인 + 요소들은 블록 레벨
		- none: 화면에 표시하지 않고 공간도 없음(!= visibility: hidden; 공간 있음)
		- inherit: 상위 요소의 display 상속
		- table 형태로 변형
			- table: 블록 레벨의 표로 만듦
			- inline-table: 인라인 레벨의 표
			- table-row: <tr> 사용 한 것 처럼 표의 행으로 만듦
			- table-row-group: <tbody> 처럼 표의 행 그룹으로 만듦
			- table-header-group: <thead> 처럼 표의 제목영역 그룹으로 만듦
			- table-footer-group: <tfoot> 처럼 표의 요약 영역 그룹으로 만듦
			- table-column: <col> 처럼 표의 열로 만듦
			- table-column-group: <colgroup> 표의 열 그룹으로 만듦
			- table-cell: <td>, <th> 처럼 표 하나의 셀로 만듦
			- table-caption: <caption> 처럼 표의 캡션으로 만듦
		- list-item: <li>처럼 block 박스와 표시자 박스(bullet)를 만든다.

2. 테두리 관련 속성들
	- border-style : 테두리의 스타일
		- none: 기본값, 테두리 없음
		- hidden 테두리가 나타나지 않음
		- dashed: 긴 점선
		- dotted: 점선
		- double: 이중선 (border-width로 선 사이의 간격)
		- groove: 홈이 파인듯 입체적으로
		- inset: border-collapse: separate/collapse 에 따라
			- separate: 테두리가 창에 박혀있는 느낌
			- collapse: groove와 동일
		- outset: border-collapse: separate/collapse 에 따라
			- separate: 전체 테두리가 창에서 튀어나온 느낌
			- collapse: ridge와 동일
		- ridge: 테두리를 창에서 튀어나온 느낌
		- solid: 테두리를 실선으로
	- border-width: 테두리 두께 지정
		- border-top/right/bottom/left-width
	- border-color: 테두리 색상 지정
		- border-top/right/bottom/left-color
	- border: 테두리 스타일 묶어서 지정
		- border-top/right/bottom/left
		- width | color | style 순서 상관 없음
	- border-radius: 박스 모서리 둥글게
		- border-top-left/top-right/bottom-right/bottom-left-radius
		- 설정 단위: px, em, % 등
		- 타원만들기: 가로 | 세로 크기 지정
	- box-shadow: 그림자 효과
		- 수평 거리 | 수직 거리 | 흐림 정도 | 번짐 정도 | 색상 | inset

3. 여백을 조절하는 속성들
	- margin: 요소 주변 여백
		- px, cm / % / auto
		- 1px: 전체
		- 1px 2px: 위아래 좌우
		- 1px 2px 3px: 위 좌우 아래
		- 1px 2px 3px 4px: 위 오른쪽 아래 왼쪽
		- auto: display 속성에 따라 적절한 값?
			- 좌우를 auto로 두면 너비의 나머지를 똑같이 맞춰서 중앙정렬이 된다.
	- padding: content와 border 사이 여백
