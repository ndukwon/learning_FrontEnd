## 09. CSS 포지셔닝
1. CSS 포지셔닝과 주요 속성들
	- CSS 포지셔닝: 화면 콘텐츠의 배치
	- box-sizing: 너비를 정할때 border, padding를 포함할 것인지
		- content-box: default! border, padding를 제외하고 너비로 지정된 크기 그대로
		- border-box: border, padding를 포함하여 너비를 계산함

	- float: 왼쪽/오른쪽에 이미지와 텍스트를 나란히 배치하려 할때
		- left/right: 왼쪽/오른쪽
		- 같은 방향끼리 연달아 있다면 옆으로 쌓인다.

	- clear: float 속성 해제
		- left/right: 왼쪽/오른쪽 float적용된 것 해제
		- float은 그 다음 요소에도 적용이 되기 때문에

	- position: 배치방법 지정
		1. static: default, 나열한 순서대로 배치, top/right/bottom/left 속성 사용불가
		2. relative: static과 동일하게 나열한 순서대로 배치되지만, top/right/bottom/left 속성 사용가능
		3. absolute: 문서의 흐름과 상관없이 top/right/bottom/left 원하는 위치에 배치 가능
			- top/right/bottom/left의 기준: 가장 가까운 부모 OR position: relative 로 설정한 부모
		4. fixed: absolute와 유사, 문서의 흐름과 상관없이 top/right/bottom/left 원하는 위치에 배치 가능
			- top/right/bottom/left의 기준: 브라우저 창 기준

	- visibility: 보이기 속성
		1. visible: default, 보여움
		2. hidden: 자리를 차지하지만 안보이기
		3. collapse: 일반적으로 hidden 처럼 동작, table에선 "display: none"과 같은 효과

	- z-index: 요소를 쌓을 순서
		- 명시하지 않으면 1부터 순차대로 붙여줌

2. 다단으로 편집하기: multi column, 브라우저 접두사 필요
	- column-width: column의 너비 고정, column의 수가 화면의 넓이에 맞추어 늘어나거나 줄어듬
		- 크기지정 / auto(column-count에 따라 자동계산)
			```
			<style>
				.multi-columns {
					-webkit-column-width: 100px;
					-moz-column-width: 100px;
					column-width: 100px;
				}
			</style>
			<div class="multi-columns">
				<p>AAAAA</p>
				<p>BBBBB</p>
				<p>CCCCC</p>
			</div>
			```
	- column-count: column 개수 구성
		- 숫자 / auto(column-width에 따라 자동계산)
	- column-gap: column 간의 여백
		- 크기지정 / normal
	- column-rule: 구분선의 색상, 스타일, 너비
		- 너비 | 스타일 | 색상
		- 혹은 각각(브라우저 접두어 때문에 비추)
			- column-rule-color: 색상
			- column-rule-style: none / hidden / dotted / dashed / solid / double / groove / ridge / inset / outset
			- column-rule-width: 크기지정 / thin / medium / thick
	- break-before/after/inside: column 위치 지정
		- 선언한 요소 앞/뒤/중간에 세로 줄바꿈 개념
		- column / avoid-column으로 설정
	- column-span: 여러 column을 병합하여 하나만 쓰는 속성
		- 1 / all: 유지하거나 / 전부를 합치는 것만 지원
		- firefox 2016년부터 미지원

3. 표 스타일
	- caption-side: 표 제목의 위치
		- top / bottom: 위(기본) / 아래
	- border: 표 테두리
		```
		<table border="1"></table>
		```
		- 처럼 표의 모든 간격에 적용하는 것과는 다름
		- table, td 등 각각 지정해야 함
	- border-collapse: border가 서로 만날때 겹치게 할 것인지
		- collapse: 하나로 합침
		- separate: 따로 표시, default, 바깥쪽이 우선
	- border-spacing: 셀 테두리 사이의 간격
		- 상하좌우 한번에 지정
		- 상하 | 좌우 나누어 지정
	- empty-cells: 내용이 없는 빈 셀의 표시를 지정
		- show: 테두리를 그리고 비어있음을 나타냄
		- hide: 테투리를 그리지 않고 비워둠
	- table-layout: 셀 너비 지정
		- fixed: 너비 고정
			- 고정된 너비에 내용을 채우려면 word-break: break-all 속성 추가
			- 자동 줄바꿈 때문에 height: auto로 두어야 함
		- auto: 셀 내용에 따라, default
	- text-align: 셀 내에서의 수평 정렬
		- left / right / center~%X
	- vertical-align: 셀 내에서의 수직 정렬
		- baseline: 부모의 기준선에 맞춤
		- sub: 아래 첨자 위치에 맞춤
		- super: 위 첨자 위치에 맞춤
		- top / middle / bottom: 위쪽 / 중간 / 아래 맞춤
		- text-top / text-bottom: 부모 글꼴의 윗부분/아랫부분에 맞춤?
		- 길이 / 백분율
