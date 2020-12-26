#11 HTML5와 멀티미디어
1. 웹과 멀티미디어
	- 과거: 플러그인, ActiveX
		- 미디어 파일마다 플레이어가 다름
	- object: 외부 파일 삽입하기
		- data: 외부파일의 경로(필수)
		- type: 포함시긴 내용의 유형(필수)
		- name: 이름
		- width / height:
	- embed: 외부파일 삽입하기(닫는 태그 없음)
		- object를 지원하지 않는 이전 브라우저

	- 멀티미디어 지원
		- Video
			- mp4: 거의 모든 브라우저. 웹 제외하고 유료 라이선스
			- webm: 크롬, 파이어폭스, 오페라. 무료. (모바일x). 최근 많아짐
			- ogv: 크롬, 파이어폭스, 오페라. 무료. webm 이전에 많이 사용

		- Video Codec
			- H.264/AVC: mp4에서 사용. 고화질 지원 => 업게 표준. 온라인만 무료. 거의 모든 브라우저 지원.
			- v8, v9: webm에서 사용. 하드웨어 지원 부족. 화질 우수. 무료.
			- Ogg Theora: 다른 코덱 비해 화질 약함. 무료.

		- Audio
			- mp3: 거의 모든 브라우저. 유료 라이선스
			- ogg: 크롬, 파이어폭스, 오페라, 안드로이드. 무료

		- Audio Codec
			- MPEG-1 AUDIO Layer3: mp3에서 사용
			- Ogg Vorbis: 무료! '.ogg', '.oga' 확장자 사용.

2. 오디오 & 비디오 재생하기
	1. ```<audio>``` / ```<video>```: 오디오/비디오 파일 삽입
		- src: 파일 경로
		- autoplay: 다운되자 마자 자동재생. 모바일에선 자동 재생되지 않음. 비추
		- width/height: 비디오 크기
		- controls: 웹 화면에 재생/멈춤, 진행 바 볼륨 등 컨트롤 막대 표시
			- 브라우저에서 지원하며 모양은 각각 다름
		- loop: 반복 재생
		- muted: 음소거
		- preload: 재생버튼 전에 미리 다운로드
			- none: 미리 다운로드 X
			- metadata: 메타정보만 다운로드
			- auto: preload만 선언시 default. 미리 다운로드함
		- poster: 재생이 안되는 상황에서의 이미지 지정
		- 마우스 오른쪽 메뉴로 control 표시 혹은 조작 할 수 있음

		<audio controls loop muted>
			<source src="https://bigsoundbank.com/UPLOAD/ogg/0115.ogg" type="audio/ogg">
			<source src="https://bigsoundbank.com/UPLOAD/mp3/0117.mp3" type="audio/mp3">
		</audio><br />

		<video controls loop muted width="300" preload="none">
			<source src="https://docs.google.com/uc?export=download&id=1worT_sLRzbUMGyLSUHRhxiW_frAYIQ3o" type="video/ogg">
			<source src="https://filesamples.com/samples/video/webm/sample_960x540.webm" type="video/webm">

			<source src="https://www.learningcontainer.com/wp-content/uploads/2020/05/sample-mp4-file.mp4" type="video/mp4">
		</video><br />

	3. ```<source>```: 여러 미디어 파일 한번에 지정
		- video 태그 안에서
		- src: 파일 경로
		- type: 미디어 파일 유형
		- codecs: 비디오 코덱 지정
		- 파일 제공 사이트에서 MIME 유형 지정 필요
			- 로컬에선 되지만 재생되지 않는 경우가 있음
			- 파일이 인식될 수 있도록 설정 필요
		- html5 이하에서 보여줘야 한다면 플래시 무비로 변환 후 플러그인으로 삽입
		```
			<video controls>
				<source src="dummy.mp4" type="video/mp4">
				<source src="dummy.webm" type="video/webm">
				<source src="dummy.ogv" type="video/ogg">
				이 영상은 HTML5을 지원하는 브라우저에서 재생 가능합니다.
				OR
				<object data="dummy.swf" type="application/x-shockwave-flash"></object>
			</video>
		```

	4. ```<track>```: 자막 추가
		- kind: 자막의 종류
			- subtitles: default. 소리 나지만 이해할 수 없는 경우, 다른 언어를 위해
			- captions: 청각장애인용 혹은 소리를 켤 수 없는 경우
			- descriptions: 비디오 컨텐츠에 대한 설명. 화면에 표시되지 않음
			- chapters: 비디오 탐색을 위한 창 제목. 화면에 표시되지 않음
			- metadata: 비디오 컨텐츠 정보. 화면에 표시되지 않음
		- src: 자막 텍스트 파일의 경로
		- srclang: 사용하는 언어 지정.
			- ex) ko / en 등
			- kind="subtitles" 이면 반드시
		- label: 자막이 여러개일 경우 식별
		- default: 기본으로 사용할 자막 지정
		```
		<track kind="subtitles" src="dummy.vtt" srclang="ko" label="korean" default>
		```

		- WebVTT 자막 파일
			- smi: 자막 내용만
			- srt: 자막, 시작/종료 시간
			- vtt: WebVTT. 자막, 시작/종료 시간
				```
					시작 시간 --> 종료시간
					자막 내용

				 	HH:MM:SS.ttt --> HH:MM:SS.ttt
					자막 내용
				```
				- 대부분 웹서버는 vtt파일을 인식하지 못함 >> MIME type 추가
			- MS HTML5 Video Caption Maker 에서 자막 파일을 쉽게 만들 수 있음
				- https://testdrive-archive.azurewebsites.net/Graphics/CaptionMaker/Default.html

	- 동영상으로 홈페이지 대문 만들기
		- 내용이 화면 단위 일때
		- 자동재생
			- muted가 설정되어 있어야 자동재생을 시켜줌
			- 스마트폰은 풀스크린 배경을 사용 불가 >> 이미지로 대체
		- 20~30초 정도 5MB 미만 권장
		- 오디오가 제거된 영상 권장

		```
			<style>
				.video-background {
					position: fixed;
					top: 0;
					left: 0;
					height: auto;
					width: auto;
					min-height: 100%;
					min-width: 100%;
					z-index: -100;

					// 미지원
					background: url([동영상 대체 이미지]) left no-repeat;
					background-size: cover;
				}
			</style>
		```
