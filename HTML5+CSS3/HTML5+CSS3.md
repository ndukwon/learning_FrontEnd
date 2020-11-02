# Do it! HTML5 + CSS3 웹표준의 정석
- https://www.coupang.com/vp/products/69096427?itemId=231125641&vendorItemId=3564292720&q=html+css&itemsCount=36&searchId=a73ef92e67d1427dbec130b3d88dab08&rank=1&isAddedCart=
- 저자: 고경희
- 출판: 이지스 퍼블리싱

## 목차
01. HTML 기본기 다지기
02. 텍스트 관련 태그들
03. 이미지와 하이퍼링크
04. 폼 관련 태그들
05. CSS 기초
06. 텍스트 관련 스타일
07. 색상과 배경을 위한 스타일
08. 레이아웃을 위한 스타일
09. CSS 포지셔닝
10. HTML5와 시맨틱 태그
11. HTML5와 멀티미디어
12. 다재다능한 CSS3 선택자
13. CSS3와 애니매에션
14. 반응형 웹이란?
15. 반응형 웹 사이트 만들기

## 01. HTML 기본기 다지기
1. HTML과의 첫 만남
2. 웹 브라우저와 웹 편집기
3. HTML 기본 분서 구조
4. 웹 문서 만들고 업로드하기

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

## 03. 이미지와 하이퍼링크
1. 이미지
	- 웹에서 사용하는 이미지 형식
		- gif : Graphic Interchange Form
			- 최대 256컬러
			- 작은 아이콘/이미지, 투명배경, 움직이는 이미지
		- jpg/jpeg : Joint Photographic Experts Group
			- 사진용, gif 보다 다양한 색상, 저장을 반복하면 화질이 떨어질 수 있다?
		- png : Potable Network Graphic
			- 네트워크용으로 개발
			- 투명배경, 다양한 색상

```html
	- <img> : images 이미지를 표시
		- src : 이미지 경로, 로컬의 경우 현재 html이 있는 경로를 기준
		- alt : 이미지 설명
			- 시각장애인 낭독기, 이미지 액박일때
		- width / height: 이미지 크기
	- <figure> : 설명 글을 붙일 대상(이미지, 표 등)을 감싼다.
		- <figcaption> : 설명할 내용을 담는다.
```

2. 링크 만들기
```html
	- <a> : a hyperlink, 링크를 걸어준다.
		- https://www.w3schools.com/tags/tag_a.asp
		- href : 링크주소
		- target : 링크된 내용이 표시될 창 지정 - 현재 창/새 창
			- _blank : 새 창/새탭
			- _self : 현재 창
			- _parent : 프레임 안에 있다면 부모 프레임에 표시
			- _top : 프레임 밖 전체화면에 표시
		- download : 링크로 넘어가지 않고 다운로드 하게 함
		- rel : 현재 문서와 링크한 문서와의 관계를 알려줌
		- hreflang : 링크한 문서의 언어를 지정
		- type : 링크한 문서의 파일 유형을 알려줌
	- <map> : 이미지의 영역을 지정하여 링크를 연결한다. 여러 영역들을 묶는 역할
		- name : <img usemap="~~"> 에 지정할 이름
		- <area> : 영역을 지정한다.
		  - alt : 이미지가 없을때 대체 텍스트
			- coords : 링크로 사용할 영역을 지정 - 시작좌표 끝좌표 형식, (a,b)(x,y) => "a,b,x,y"
			- download : 클릭하면 다운로드
			- href : 링크의 경로
			- media : 링크를 어떤 미디어에 최적화할지를 지정
			- rel : 현재 문서과 링크 문서 사이의 관계
				- iternate / bookmark / help / license / next / nofollow / noreferer / prefetch / prev / search / tag
			- shape : 영역의 형태를 지정
				- default / rect / circle / poly
			- target : 링크를 표시할 대상을 지정
			- type : 링크의 미디어 유형을 지정
```

3. SVG 이미지
	- SVG : Scalable Vector Graphics
	- SVG 미지원 : IE 8 이하, Android 2.3 이하 - PNG를 사용해야 함
	- Modernizr 사이트로 특정기능 지원여부 테스트
		- https://modernizr.com/download?setclasses

## 04. 폼 관련 태그들
1. 폼 만들기
```html
	- <form> : <input>을 감싸고 입력에 대한 컨트롤을 지원한다.
		- method : 사용자가 입력한 내용을 서버로 보내는 방식
			- get : 내용 드러남, 256 ~ 4096 byte까지
			- post : 내용 길이제한 없고, 내용 드러나지 않음. 주로 이 방식 사용
		- name : 여러개의 form들 중에서 구분하기 위해 form의 이름을 지정
		- action : form 의 내용을 처리해 줄 실행할 스크립트 파일을 지정
		- target : action에서 지정한 스크립트 파일을 다른위치에 열도록 지정
		- autocomplete : on(default) / off
	- <label> : <input>을 감싸고 레이블을 붙이기 위한 것. 브라우져가 인식함
		- for : input의 id를 지정하여 그 input과 연결. input을 감싸지 않아도 됨
		- 라디오 버튼, 체크박스에 달아두면 text를 터치해도 선택되게 하는 효과
	- <fieldset> : 태그 안의 form들을 묶는 외곽선을 그려줌
		- <legend> : 외곽선의 제목(레이블)을 설정
```

2. 사용자 입력을 위한 input 태그
```html
	- <input> : 사용자 입력란
		1. name : 필드의 이름을 지정
		2. value : 필드의 값
		3. type : 입력하는 형태
			- hidden : 사용자에게는 보이지 않음
			- text : 한줄짜리 텍스트
				- size : 화면에서 text box의 길이를 지정, 글자수 단위
				- maxlength: 최대 문자 개수
			- password : 비밀번호
			- search : html5에서 추가됨, 검색상자, 텍스트 지울 수 있는 x 버튼이 나온다.
			- url : URL 주소, "http://" 로 시작하는 주소를 자동으로 체크
			- email : 메일 주소, 메일주소 형식을 자동으로 체크
			- tel : 전화번호 입력, 바로 전화를 걸 수 있도록
			- number : 숫자 조절 화살표, 브라우저에 따라 스핀박스(증감 버튼) 지원
			- range : 숫자 조절 슬라이드 막대, 일부 브라우저는 텍스트 상자로 표시됨
			- checkbox : 복수선택 체크박스
			- radio : 단일선택 라디오버튼
				- name : 라디오 버튼의 그룹, 같은 이름 중에서 하나만 고를 수 있도록 함
				- value : 선택된 버튼의 값
				- checked : 기본으로 선택된 상태를 설정
			- color : 색상 표에서 색상을 선택할 수 있도록, html5에서만
				- value : #ffffff 형태의 값
			- date : 사용자 지역 기준 날짜(년월일), 일부 브라우저는 달력 미지원(yyyy/mm/dd 타이핑 입력)
			- month : 사용자 지역 기준 월(년월)
			- week : 사용자 지역 기준 주(년주)
			- time : 사용자 지역 기준 시간(시분초,분할초)
			- datetime : UTC 날짜(년월일)와 시간(시분초,분할초)
				- HTML5 미지원 => HTML5.1 지원
				- 타임존 표기
					- UTC : 날짜 뒤 Z
					- 아닌경우 : +dd:dd, -dd:dd
			- datetime-local : 사용자 지역 기준 날짜와 시간
			- submit / reset : 서버 전송 / 리셋 버튼
			  - action : 프로그림의 파일명(php)
				- method : get / post 방식을 지정
			- image : submit 버튼 대신 사용할 이미지
			- button : 버튼
				- value : 버튼 내용
			- file : 파일 첨부 버튼
```

3. input 태그의 다양한 속성
```html
	1. autofocus : 페이지를 불러오자마자 폼의 요소 중 원하는 요소에 마우스 커서를 표시
	2. placeholder : 힌트 내용을 표시
	3. readonly : 읽기전용
		- readonly
		- readonly="readonly"
		- readonly="true"
	4. required : 필수 필드 지정
		- required
		- required="required"
	5. min, max, step : (숫자) 최소, 최대, 간격 값 지정
		- date, datetime, datetime-local, month, week, time, number, range 에서만 사용가능
	6. size, minlength, maxlength : text 길이, 최소길이, 최대길이
	  - minlength : 최신 크롬과 안드로이드에서만 지원
	7. etc
		- formaction : type="image", type="submit"일때 실행할 프로그램을 연결
		- formenctype : type="image", type="submit"일때 서버에서 폼 데이터를 어떤 방식으로 해석할 것인지 지정
		- formmethod : 서버에 전송할 방식(GET, POST 등) 지정. <form> 테그에서 지정해도 무시하고 이 방식으로 함
		- formnovalidate : 서버 전송할때 유효성 여부 표시
		- formtarget : 서버의 응답을 어디에 표시할 것인지 타깃을 지정
		- height, width: type="image" 일 때 크기 지정
		- list : <datalist> 태그 에서 미리 정해놓은 옵션 값을 <input>안에 나열
		- multiple : type="email", type="file" 일때 두개 이상의 값을 입력
```

4. 여러 데이터 나열해 보여 주기
```html
	1. <select> : 드롭다운
		- size : 드롭다운 항목의 개수
		- multiple : 멀티선택 가능(control을 누르고 여러개 선택 가능)
		- <option> : 드롭다운의 항목들
			- value : 선택되었을때 전달될 값
			- selected : 기본 선택
		- <optgroupt> : 옵션들을 그룹으로 묶음
			- label : 그룹 이름
			- value : 선택되었을때 전달될 값?
	2. <input> + <datalist> : 드롭다운 이지만 typing 입력도 가능함
		- <input> + list => <datalist> + id 지정
		- <option> : 드롭다운의 항목들, <select> 의 경우와 동일
	3. <textarea> : 여러줄 입력 텍스트 영역
		- name : 영역의 이름
		- cols : 가로길이, 문자 단위
		- rows : 세로길이, 문자 단위
```

5. 기타 다양한 폼 요소들
```html
	1. <button> : 버튼
		- <input type="button">보다의 장점 :
			- 화면 낭독기가 이 부분이 명확히 버튼이다고 인식이 가능하다.
			- tag + css 만으로 구성하기 때문에 빠르다.
		- type="submit" : 서버로 전송
			- value="전송하기"
		- type="reset" : (자신이 소속된) form 입력내용을 초기화
		- type="button" : 버튼 형태
	2. <output> : 계산 결과
		- 브라우저가 정확히 output인지를 input의 결과를 잘 보여줄 수 있다.
		- 감싸고 있는 <form>의 oninput으로 input => output 될 계산식을 설정
	3. <progress> : progress
		- value : 진행된 값
		- max : 최대 진행될 값. default: 1
	4. <meter> : progress와 유사
		- min/max : 최소/최대값. default: 0/1
		- value : 표시할 값(초록색)
		- low : 이 값 이하로는 low(노란색)
		- high : 이 값 이상으로는 high(노란색)
		- optimum : 이 값이 적정한 값
```

## 05. CSS 기초
1. 스타일과 스타일 시트
	- 웹 표준 : HTML - 내용을 나열, CSS - 디자인 구성
	- 스타일과 스타일 시트
		```
		- 내부 스타일 시트 : <style></style>
		- 외부 스타일 시트 :
			- .CSS
			- <link href="[스타일 파일 경로]" rel="stylesheet" type="text/css">
		- 인라인 스타일 : style="스타일~"
		```
2. 주요 선택자
		```
		- 전체 선택 : * { 스타일~ }
		- 태그 : [태그명] { 스타일~ }
		- 클래스 : .[클래스명] { 스타일~ }
		- id : #[id명] { 스타일~ }
		```
3. 캐스캐이딩 스타일 시트(CSS)
	- CSS : Cascading Style Sheet
	- 스타일간의 충돌을 막기 위한 방법
	- 스타일 우선순위
		- 중요도(important)
			1. 사용자 스타일 시트의 중요 스타일
				- 저시력자, 색약자 설정 등
			2. 제작자 스타일 시트의 중요 스타일
				- 사이트 제작자가 만든 스타일 중 !important 가 붙은 것
			3. 제작자 스타일 시트의 일반 스타일
				- 사이트 제작자가 만든 스타일
			4. 사용자 스타일 시트의 일반 스타일
			5. 브라우저 스타일 시트의 스타일
				- 링크 색상 등 브라우저가 정하는 색상
		- 명시도(Specificity)
			1. 인라인 스타일
			2. id 스타일
			3. 클래스 스타일
			4. 태그 스타일
		- 소스 순서 : 나중에 나온 스타일이 덮어씀
	- 스타일 상속
		- 부모 요소가 자식 요소에 상속된다.
		- 예외 : 배경이미지, 배경색 등

4. CSS3와 CSS 모듈
	- CSS2 : 스타일이 한꺼번에 담겨있어 덩치가 크고 복잡
	- CSS3 : 작은 CSS 모듈들, 보다 정교해지고 애니메이션 지원
	- W3C 표준화 단계
		1. LC : Last Call Working Draft. 초안을 최종 검토
		2. WD : Working Draft. 초안. W3C 멤버, 대중, 다른 기술단체 등의 검토
		3. CR : Candidate Recommendation. 후보 권고안
		4. PR : Proposed Recommendation. 제안 권고안
		5. REC : W3C Recommendation. 권고안
	- 브라우저 접두사
		- -webkit- : 사파리, 크롬 등 웹키트 방식
		- -moz- : 모질라, 파이어폭스 등 게코 방식
		- -o- : 오페라 브라우저
		- -ms- : 인터넷 익스플로러
	- 브라우저 접두사 자동으로 붙이기
		- 라이브러리 : https://leaverou.github.io/prefixfree/#

## 06. 텍스트 관련 스타일
1. 글꼴 관련 스타일
	- font-family : [글꼴 이름1], [글꼴 이름2], [글꼴 이름3]
		- 사용자에 시스템에 없으면 표시할 수 없으므로 web-safe font를 사용
		- web-safe font
			- Window: 영문 - sans-serif, 한글 - 굴림, 궁서, 돋움, 바탕
		- 하위에 항속. 보통 Body에 선언
	- 웹 폰트
		- @import url([폰트 URL]);
		- import한 폰트를 포함하여 font-family를 선언
	- 직접 웹 폰트
		- 글꼴파일 :
			- ttf/otf(True Type font / Open Type font), 파일 사이즈가 크다
			- eot(Embedded Open Type)
			- woff(Web Open Font Format)
			- svg/svgz
			- 글꼴 포멧 변환 가능하지만 사용허가 있어야 함. 사전에 확일 필요
		- @font-face { font-family: [폰트명]; src:url(글꼴파일 경로) format(파일 유형)}
			형태로 선언, 지원가능여부에 따라서 파일 유형
	- font-size : 글자 크기 속성
		- 절대크기: xx-small | x-small | small | medium | large | x-large | xx-large
		- 상대크기: larger | smaller
		- 지정크기: px...
			- 크기 단위
				- em: 부모 폰트크기 대문자 M의 크기 = 1em
				- ex: x-height, 소문자 x의 높이를 기준으로
				- px: 모니터의 상대적 크기, 모바일 환경 고려한다면 em을 권장
				- pt: 포인트, 일반 문서
		- 백분율: 부모의 글자크기를 기준으로
	- font-weight : 글자 굵기 지정
		- 상대값: normal | bold | bolder | lighter
		- 절대값: 100 | 200 | 300 | 400(=normal) | ... | 700(=bold) | 900
	- font-variant : 영어 글꼴에서 대문자를 소문자 크기에 맞추어 작게 표시
		- small-caps: 작은 대문자
	- font-style : 이탤릭체
		- italic: 글꼴이 지원하는 이탤릭체
		- oblique: 단순히 기울어지게 표시
	- font : 글꼴 속성 한번에 정의
		- 순서: font-style, font-variant, font-weight, font-size/line-height, font-family
		- 또는 해당하는 키워드에 어울리는 글꼴 스타일 : caption | icon | menu | message-box | small-caption | status-bar

2. 텍스트 스타일
	- color: 글자색
	- text-decoration: 밑줄, 취소선 등
		- underline: 밑줄, ex) <span style="text-decoration:underline">underline</span>
		- overline: 윗줄, ex) <span style="text-decoration:overline">overline</span>
		- line-through: 취소선, ex) <span style="text-decoration:line-through">line-through</span>
	- text-transform: 대소문자 변환
		- capitalize: 시작하는 첫번째 글자를 대문자로
			ex) <span style="text-transform:capitalize">capitalize capitalize</span>
		- uppercase: 대문자로 변환
			ex) <span style="text-transform:uppercase">uppercase uppercase</span>
		- lowercase: 소문자로 변환
			ex) <span style="text-transform:lowercase">LOWERCASE lowercase</span>
		- full-width: 전각문제로 변환, 지원하는 문자에 한함
			ex) <span style="text-transform:full-width">full-width full-width</span>
	- text-shadow: 텍스트 그림자 효과, 여러번 선언하여 오버레이
		- 가로거리 세로거리 번짐정도 색상
		- 가로거리: 양수-오른쪽, 음수-왼쪽에 그림자
		- 세로거리: 양수-아래쪽, 음수-위쪽에 그림자
		- 번짐정도: 양수-밖으로, 음수-안쪽으로 번짐
	- white-space: 공백
		- normal: 여러개의 공백을 하나로 표시
		- nowrap: normal + 줄바꿈 안함
		- pre: 여러개의 공백을 그대로 표시 + 줄바꿈 안함
		- pre-line: normal + 자동 줄바꿈
		- pre-wrap: 여러개의 공백을 그대로 표시 + 자동 줄바꿈
	- letter-spacing / word-spacing : 낱글자사이 간격 / 단어사이 간격
		- ex) letter-spacing: 0.2em;

3. 문단 스타일
	- direction: 글자 쓰기 방향,
		- ltr: ex) <span style="direction:ltr">가나다라마바사</span>
		- rtl: ex) <span style="direction:rtl">언어가 ltr 이면 미적용</span>
	- text-align: 텍스트 정렬
		- start: ltr언어는 왼쪽, rtl언어는 오른쪽으로 정렬
		- end: start의 반대
		- left/right/center: 왼쪽/오른쪽/가운데 맞춤
		- justify: 양쪽에 맞추어 정렬
		- match-parent: 부모의 요소를 따라 문단을 정렬. 단, 부모가 start/end인 경우는 left/right으로 고정됨
	- text-justify: 텍스트 정렬시의 공백
		- auto: 웹브라우저의 자동
		- none: 정렬 안함
		- inter-word: 단어 사이의 공백읠 조절
		- distribute: 글자단위의 사이 공백을 똑같이 맞추어 정렬
	- text-indent: 텍스트 들여쓰기
		- 크기 지정: px등의 단위로 지정, 백분률: 부모요소의 너비를 기준, 음수도 가능
	- line-height: 줄 간격 조절
		- normal | 크기 지정: px등의 단위로 지정 | 숫자/백분율: 글자크기를 기준 | inherit
	- text-overflow: text가 레이아웃을 넘어갈때의 설정
		- white-space는 줄바꿈에 대한 설정이고, 줄바꿈이 일어나지 않을때 레이아웃에 넘치는 text를 어떻게 처리할 것인지에 대한 설정
		- clip: 넘치는 text 자름
		- elipsis: 말 줄임(...) 으로 표시
			- overflow와 같이 쓰여지면서 hover 하면 나머지 글이 보이도록 하는 동작으로 자주 쓰임

4. 목록 스타일
	- list-style-type: 목록의 bullet 모양
		- ul case
			- disc: default라는데... ex) <ul style="list-style-type: disc"><li>list-style-type: disc</li></ul>
			- circle: ex) <ul style="list-style-type: circle"><li>list-style-type: circle</li></ul>
			- square: ex) <ul style="list-style-type: square"><li>list-style-type: square</li></ul>
			- none: ex) <ul style="list-style-type: none"><li>list-style-type: none</li></ul>
		- ol case
			- decimal: ex) <ol style="list-style-type: decimal"><li>list-style-type: decimal</li></ol>
			- decimal-leading-zero: ex) <ol style="list-style-type: decimal-leading-zero"><li>list-style-type: decimal-leading-zero</li></ol>
			- lower-roman: ex) <ol style="list-style-type: lower-roman"><li>list-style-type: lower-roman</li></ol>
			- upper-roman: ex) <ol style="list-style-type: upper-roman"><li>list-style-type: upper-roman</li></ol>
			- lower-alpha: ex) <ol style="list-style-type: lower-alpha;"><li>list-style-type: lower-alpha</li></ol>
			- upper-alpha: ex) <ol style="list-style-type: upper-alpha"><li>list-style-type: upper-alpha</li></ol>
			- armenian: ex) <ol style="list-style-type: armenian"><li>list-style-type: armenian</li></ol>
			- georgian: ex) <ol style="list-style-type: georgian"><li>list-style-type: georgian</li></ol>
	- list-style-image: ul 목록의 bullet 모양대신 이미지로
		- url(image url 경로): 없으면 list-style-type 설정을 따름
			- ex) <ul style="list-style-image: url(https://img.icons8.com/metro/26/000000/domain.png)"><li>list-style-image: url(https://img.icons8.com/metro/26/000000/domain.png)</li></ul>
	- list-style-position: 목록 들여쓰는 효과를 bullet을 포함할 것인가의 여부
		- inside: ex) <ol style="list-style-position: inside"><li>list-style-position: inside</li></ol>
		- outside: default, ex) <ol style="list-style-position: outside"><li>list-style-position: outside</li></ol>
	- list-style: type, image, position 설정을 한번에
		- type, image, position 순서대로 설정: image 로딩에 실패시 type 속성대로 보여줌


## 07. 색상과 배경을 위한 스타일
1. 웹에서 색상 표현하기
	- 16진수 표기법: #RRGGBB, 00 ~ FF : 없음 ~ 가득
	- rgb/rgba 표기법: 10진수, rgb(red, green, blue)/rgba(red, green, blue, alpha) 로 표현, 0 ~ 255 : 없음 ~ 가득, alpha: 불투명도 - 0 ~ 1: 투명 ~ 불투명
	- hsl/hsla 표기법: hue(색상), saturation(채도), lightness(밝기)
		- 색상환(원형 그라데이션으로 된 색 고르는 판)
		- hue(색상): 0/360도: red, 120도: green, 240도: blue
		- saturation(채도): 0%: 회색 ~ 100%: 아무것도 안 섞은 순수한 그색
		- lightness(밝기): 0%: 어두움 ~ 100%: 가장 밝음
		- ex) 빨간색: hsl(360, 100%, 0%) => 반투명 빨간색: hsl(360, 100%, 0%, 0.5)
	- 색상 이름 표기법: red, yellow, black 등 web-safe color(웹 안전 색상)
		- 기본 16색, 총 216가지 색상
	- 색상 추출 사이트
		- https://www.w3schools.com/colors/colors_picker.asp
		- https://www.webfx.com/web-design/color-picker/

2. 배경 색과 배경 이미지
	- background-color: 배경 색 지정
		- 16진수/rgb/색상이름 으로 지정
		- 상속 X
	- background-clip: 배경 적용 범위 조절
		- border-box: border(테두리) 까지, default
		- padding-box: border(테두리)를 제외한 padding 까지
		- content-box: 내용부분에만
	- background-image: 배경 이미지 지정
		- url(파일경로): 절대/상대경로 등
	- background-repeat: 배경 이미지 반복 방법 지정
		- repeat: 가득 찰때까지 가로, 세로 반복 - default
		- repeat-x/repeat-y: 가로/세로로 반복
		- no-repeat: 한번만 표시
	- background-size: 배경 이미지 크기 조절
		- auto: 이미지 크기만큼 표시 - default
		- contain: 이미지를 요소의 크기에 맞춤, 비율 유지
		- cover: 배경 이미지가 요소를 모두 덮도록
		- 가로 세로 지정: 크기값이 하나만 주어지면 가로로 지정되고 이미지의 비율에 맞추어 나머지 크기 자동
			- ex) 200px 150px, ex) 60% 40%
	- background-position: 배경 이미지 위치 조절
		- ex) background-position: left center;
		- 수평 수직 지정: 하나만 지정하면 수평으로 간주, 수직은 center/50% 자동 지정
			- 수평: left/center/right/백분율/고정값
			- 수직: top/center/bottom/백분율/고정값
		- 백분율/고정값: 지정한 값 만큼 왼쪽/위쪽을 비우고 왼쪽/상단 모서리에 맞춤
	- background-origin: background-position을 사용할때 왼쪽/상단의 시작 기준
		- background-clip 속성과 유사
		- border-box: border(테두리) 까지, default
		- padding-box: border(테두리)를 제외한 padding 까지
		- content-box: 내용부분에만
	- background-attachment: 스크롤시 배경 이미지 고정
		- scroll: 스크롤에 따라 이동
		- fixed: 화면에 고정
	- background: background 관련 속성을 한방에
		- 순서: background-image, background-repeat, background-attachment,
			background-position, background-clip, background-origin, background-size


3. 그러데이션 효과로 배경 꾸미기
	- 지원하지 않는 브라우저 접두사
		- -webkit- : 사파리 5.1 ~ 6.0
		- -moz- : 파이어폭스 3.6 ~ 15
		- -o- : 오페라 11.1 ~ 12.0
	```html
	<style>
		// 방향지정
		.hello {
			background: blue; // 미지원 브라우저용
			// 시작위치, 시작색상, 끝 색상
			background: -webkit-linear-gradient(left top, blue, white);
			// 끝 위치, 시작색상, 끝 색상
			background: -moz-linear-gradient(right bottom, blue, white);
			background: -o-linear-gradient(right bottom, blue, white);
			background: linear-gradient(to right bottom, blue, white);
		}

		// 각도 지정
		.hello2 {
			background: #ff0000; // 미지원 브라우저용
			// 끝 부분 각도, 시작색상, 끝 색상
			background: -webkit-linear-gradient(45deg, #ff0000, #ffffff);
			background: -moz-linear-gradient(45deg, #ff0000, #ffffff);
			background: -o-linear-gradient(45deg, #ff0000, #ffffff);
			background: linear-gradient(45deg, #ff0000, #ffffff);
		}

		// 색상 중지 점(color-stop)
		.hello3 {
			background: #06f; // 미지원 브라우저용
			// 시작부분, 시작색상, 중간색상 시작위치에서의 거리,끝 색상
			background: -webkit-linear-gradient(top, #06f, white 30%, #06f);
			// 끝부분, 시작색상, 중간색상 시작위치에서의 거리,끝 색상
			background: -moz-linear-gradient(bottom, #06f, white 30%, #06f);
			background: -o-linear-gradient(bottom, #06f, white 30%, #06f);
			background: linear-gradient(bottom, #06f, white 30%, #06f);
		}
	</style>
	```
	- 선형 그러데이션: linear-gradient(<각도> to <방향>, color-stop, [color-stop, ...])
		- 수평, 수직, 대각선 방향으로 일정하게 변화
		- 방향: 그러데이션의 방향
			- to top/bottom : 아래에서 시작하여 위로 / 위에서 시작하여 아래로
			- to left/right : 오른쪽에서 시작하여 왼쪽으로 / 왼쪽에서 시작하여 오른쪽으로
		- 각도: 색상이 바뀌는 방향
			- 수직 윗 방향을 기준으로 0deg, 오른쪽 시계방향으로 증가
		- 색상 중지 점(color-stop): 그러데이션 중간 지점 색 변화
			- 시작 위치에서의 거리와 중간지점의 색을 지정

	```html
	<style>
		// 모양: ellipse(default)
		.hello {
			background: red; // 미지원 브라우저용
			background: -webkit-radial-gradient(white, yellow, red);
			background: -moz-radial-gradient(white, yellow, red);
			background: -o-radial-gradient(white, yellow, red);
			background: radial-gradient(white, yellow, red);
		}

		// 모양: circle
		.hello2 {
			background: red; // 미지원 브라우저용
			background: -webkit-radial-gradient(circle, white, yellow, red);
			background: -moz-radial-gradient(circle, white, yellow, red);
			background: -o-radial-gradient(circle, white, yellow, red);
			background: radial-gradient(circle, white, yellow, red);
		}

		// 위치
		.hello2 {
			background: red; // 미지원 브라우저용
			background: -webkit-radial-gradient(10% 10%, circle, white, blue);
			background: -moz-radial-gradient(10% 10%, circle, white, blue);
			background: -o-radial-gradient(10% 10%, circle, white, blue);
			background: radial-gradient(circle at 10% 10%, white, blue);
		}

		// 크기
		.hello2 {
			background: darkgreen; // 미지원 브라우저용
			background: -webkit-radial-gradient(30% 40%, circle closest-side, white, yellow, green);
			background: -moz-radial-gradient(30% 40%, circle closest-side, white, yellow, green);
			background: -o-radial-gradient(30% 40%, circle closest-side, white, yellow, green);
			background: radial-gradient(circle closest-side at 30% 40%, white, yellow, green);
		}
	</style>
	```
	- 원형 그러데이션: radial-gradient(<최종 모양> <크기> at <위치>, color-stop, [color-stop...])
		- 모양: circle(원형), ellipse(타원형, default)
		- 위치: 그러데이션이 시작하는 위치 지정
			- top, left 등으로 지정하거나 왼쪽 상단에서부터의 거리를 지정
		- 크기: 그러데이션 원의 크기를 지정. 어느쪽 벽이나 모서리를 기준으로 멈출 것인지
			- closest-side: 가장 가까운 모서리까지
			- closest-corner: 가장 가까운 코너까지
			- farthest-side: 가장 먼 모서리까지
			- farthest-corner: 가장 먼 코너까지
		- 색상 중지 점(color-stop): 그러데이션 중간 지점 색 변화
			-

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
		- auto: display 속성에서 지정한 값에


## 09. CSS 포지셔닝
