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
