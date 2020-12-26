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
