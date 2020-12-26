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