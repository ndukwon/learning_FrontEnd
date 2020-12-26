## 10. HTML5와 Semantic tag
1. HTML4 VS HTML5: 태그만 보고도 페이지에서 어떤 부분인지 알 수 있도록
	- body 안에서?
		- header: 제목, 검색 창 등
		- contents: 본문
		- sidebar: 사이드 바
		- footer: 저작권 정보, 제작자 정보 등
	- 본문과 제목을 쉽게 구별, 검색 할 수 있도록

2. 문서 구조를 위한 HTML5 Semantic tag
	- https://html.spec.whatwg.org/dev/sections.html
	- header: 머리말 지정 (!= head 태그와 다름을 주의)
		- 주로 페이지 맨 위쪽, 왼쪽에 삽입
		- 본문중 해당 내용의 머리말로도 사용
		- header 내부 구성
			- form: 검색창
			- nav: 사이트 메뉴
	- nav: 동일한 사이트 안의 문서나 다른 사이트의 문서로 연결하는 링크 모음
		- 위치의 영향을 받지 않고 독립적 사용
	- section: 주제별 콘텐츠 영역
		- section 내부 구성
			- h1 ~ 6 로 제목을 사용
			- 또다른 section을 둘 수도 있음
	- article: 독립적인 하나의 콘텐츠 구성 단위
		- https://html.spec.whatwg.org/dev/sections.html#the-article-element
		- article 내부 구성
			- 주로 header, section을 넣는다.
	- aside: 본문 이외의 내용 표시
		- 광고나 링크 모음을 넣을때
	- iframe: 외부 문서 삽입 = inline frame
		- src: 삽입할 문서 주소
		- width, height: 너비, 높이 px/백분율
		- name: frame 이름
		- seamless: 프레임의 테투리를 없애서 본문의 일부처럼(크롬, 사파리에서만 지원)
	- footer: 제작 정보와 저작권 정보 표시
	- address: 사이트 제작자, 연락처 정보 등
		- 주로 footer 내부에서 사용

3. IE8 이하 버전에서는 어떻게 하나요?
	- caniuse.com 으로 지원범위 확인
		- https://caniuse.com/?search=semantic
		- IE8, 오페라 미니 미지원

		1. 지원하지 않는 tag를 CSS에서 블록 레벨로 정의
			```
				header, section, nav, article, footer {
					display: block;
				}
			```
		2. tag 직접 정의
			```
				document.createElement('article');
				document.createElement('section');
				document.createElement('aside');
				document.createElement('nav');
				document.createElement('header');
				document.createElement('footer');
			```
		3. html5shiv
			- head 사이에 추가

	- pollyfill: js로 브라우저 진단하여 shim을 자동으로 끼워주는 역할
		- https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills
		- browswer fragmentation: 어떤 브라우저는 되고 안되는 파편화
		- shim / fallback: 파편화를 줄이고 같은 결과를 만들기 위한 방법
