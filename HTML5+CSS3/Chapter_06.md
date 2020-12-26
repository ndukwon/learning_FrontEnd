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
