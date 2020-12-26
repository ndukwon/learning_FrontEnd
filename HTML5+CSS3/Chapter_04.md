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
