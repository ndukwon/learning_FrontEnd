## 02. 텍스트 관련 태그들
1. 텍스트를 덩어리로 묶어주는 태그
```html
	- <h1> ~ <h6> : 텍스트 제목
	- <p> : 문단
	- <br> : 줄바꿈
	- <hr> : 선긋기
	- <blockquote> : 인용구 표현
	- <pre> : 입력하는 그대로
```
2. 텍스트를 한 줄로 표시하는 태그
```html
	- <strong> : 굵게
	- <b> : bold
	- <em> : italic + bold
	- <i> : italic
	- <q> : quote, 따옴표 표시
	- <mark> : 형광펜
	- <span> : 줄바꿈 없이 영역 묶기
	- <ruby> : 동아시아 활자 중 글자의 주석을 다는 기능
	- <abbr> : abbreviation/acronym 약자 설명 표기
	- <cite> : 인용구를 표시
	- <code> : 소스코드 표현
	- <kbd> : 사용자가 입력할 버튼?
	- <small> : 작은 텍스트
	- <sub> : subscript 아래첨자
	- <sup> : superscript 윗첨자
	- <s> : 취소선
	- <u> : 밑줄
```
3. 목록을 만드는 태그
```html
	- <ul> : unordered list 번호 없는 목록
	- <ol> : ordered list 번호 있는 목록
		- https://www.w3schools.com/tags/tag_ol.asp
		- type: 순서의 기호을 지정할 수 있다. 1/A/a/I/i
		- start: 순서의 시작을 지정할 수 있다.
	- <li> : list item 목록의 각 항목
```
4. 표를 만드는 태그
```html
	- <table border="1"> : 표의 시작과 끝.
		- 위에서 아래로, 왼쪽에서 오른쪽으로 요소를 구성한다.
		- table -> caption
		- table -> figcaption
		- table -> (thead -> tbody -> tfoot) -> tr -> th/td
	- <tr> : table row, 행
		- https://www.w3schools.com/tags/tag_tr.asp
	- <td> : table column, Standard cell, 열
		- https://www.w3schools.com/tags/tag_td.asp
	- <th> : table column, Header cell, 헤더 열
		- https://www.w3schools.com/tags/tag_th.asp
	- <caption> : table caption, 표의 제목
	- <thead> : table header, 항목에 대한 설명이 필요한 첫번째 줄, 브라우저에서 첫줄에 대한 스크롤 지원 가능
	- <tbody> : table body
	- <tfoot> : table footer, 마지막 줄, 브라우저에서 마지막 줄에 대한 스크롤 지원 가능
	- <colgroup> : column group, column 설정을 관리
	- <col> : column 단위로 설정한다.
		- span: 가로(오른쪽)로 개수만큼 동일하게 적용
```
