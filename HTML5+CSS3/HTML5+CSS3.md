# Do it! HTML5 + CSS3 웹표준의 정석
- https://www.coupang.com/vp/products/69096427?itemId=231125641&vendorItemId=3564292720&q=html+css&itemsCount=36&searchId=a73ef92e67d1427dbec130b3d88dab08&rank=1&isAddedCart=
- 저자: 고경희
- 출판: 이지스 퍼블리싱
- 예제들: https://github.com/funnycom/html5-css3

## 목차
01. HTML 기본기 다지기
02. [텍스트 관련 태그들](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_02.md)
03. [이미지와 하이퍼링크](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_03.md)
04. [폼 관련 태그들](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_04.md)
05. [CSS 기초](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_05.md)
06. [텍스트 관련 스타일](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_06.md)
07. [색상과 배경을 위한 스타일](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_07.md)
08. [레이아웃을 위한 스타일](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_08.md)
09. [CSS 포지셔닝](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_09.md)
10. [HTML5와 시맨틱 태그](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_10.md)
11. [HTML5와 멀티미디어](https://github.com/ndukwon/learning_FrontEnd/blob/ec7d1e497f0fbe237b90f7d57c4d4f733a07f0a1/HTML5%2BCSS3/Chapter_11.md)
12. 다재다능한 CSS3 선택자
13. CSS3와 애니매에션
14. 반응형 웹이란?
15. 반응형 웹 사이트 만들기

## 01. HTML 기본기 다지기
1. HTML과의 첫 만남
2. 웹 브라우저와 웹 편집기
3. HTML 기본 분서 구조
4. 웹 문서 만들고 업로드하기


## 12. 다재다능한 CSS3 선택자

1. 연결 선택자: Combination selector
	```
		<aaa>
			<bbb>bbb1</bbb>
			<bbb>bbb2</bbb>
			<ccc>ccc1
				<bbb>bbb3</bbb>
			</ccc>
			<ccc>ccc2
				<bbb>bbb4</bbb>
			</ccc>
		</aaa>
	```
	1. 하위 선택자(Descendant Selector): ``` aaa bbb { color: red; } ```
		- 하위 모두에 적용
		- aaa 내부에 있는 모든 bbb는 적용된다. >> bbb1, bbb2, bbb3, bbb4 모두 적용됨
		<style>.descendant-aaa .descendant-bbb { border: solid 1px red; }</style>
		<div class="descendant-aaa">descendant-aaa
			<div class="descendant-bbb">descendant-bbb1</div>
			<div class="descendant-bbb">descendant-bbb2</div>
			<div class="descendant-ccc">descendant-ccc1
				<div class="descendant-bbb">descendant-bbb3</div>
			</div>
			<div class="descendant-ccc">descendant-ccc2
				<div class="descendant-bbb">descendant-bbb4</div>
			</div>
		</div>

	2. 자식 선택자(Child Selector): ``` aaa > bbb { color: red; } ```
		- 1촌 자식에게만 적용
		- aaa의 직접 자식들인 bbb만 적용된다. >> bbb1, bbb2 해당
		<style>.child-aaa > .child-bbb { border: solid 1px red; }</style>
		<div class="child-aaa">child-aaa
			<div class="child-bbb">child-bbb1</div>
			<div class="child-bbb">child-bbb2</div>
			<div class="child-ccc">child-ccc1
				<div class="child-bbb">child-bbb3</div>
			</div>
			<div class="child-ccc">child-ccc2
				<div class="child-bbb">child-bbb4</div>
			</div>
		</div>

	3. 인접 형제 선택자(Adjacent Selector): ``` bbb + ccc { color: red; } ```
		- 인접된 후자 첫번째에게만 적용
		- bbb와 첫번째로 가까이 있는 ccc에 적용된다. >> ccc1 해당
		<style>.adjacent-bbb + .adjacent-ccc { border: solid 1px red; }</style>
		<div class="adjacent-aaa">adjacent-aaa
			<div class="adjacent-bbb">adjacent-bbb1</div>
			<div class="adjacent-bbb">adjacent-bbb2</div>
			<div class="adjacent-ccc">adjacent-ccc1
				<div class="adjacent-bbb">adjacent-bbb3</div>
			</div>
			<div class="adjacent-ccc">adjacent-ccc2
				<div class="adjacent-bbb">adjacent-bbb4</div>
			</div>
		</div>

	4. 형제 선택자(Sibling Selector): ``` bbb ~ ccc { color: red; } ```
		- 인접된 후자의 형제들에게 적용
		- bbb와 가까이 있는 ccc 모두 적용된다. >> ccc1, ccc2 해당
		<style>.sibling-bbb ~ .sibling-ccc { border: solid 1px red; }</style>
		<div class="sibling-aaa">sibling-aaa
			<div class="sibling-ccc">sibling-ccc0
				<div class="sibling-bbb">sibling-bbb0</div>
			</div>
			<div class="sibling-bbb">sibling-bbb1</div>
			<div class="sibling-bbb">sibling-bbb2</div>
			<div class="sibling-ccc">sibling-ccc1
				<div class="sibling-bbb">sibling-bbb3</div>
			</div>
			<div class="sibling-ccc">sibling-ccc2
				<div class="sibling-bbb">sibling-bbb4</div>
			</div>
		</div>

2. 속성 선택자
	1. ``` a[href] ``` : 해당 속성을 가진
	2. ``` a[target="_blank"] ``` : 해당 속성의 값과 일치
	3. ``` a[class ~="button"] ``` : 해당 속성과 일치한 것이 들어있어야 함(like 검색은 아님)
		- like 검색은 아님: class="flat button"은 해당되고, class="flat-button" 은 해당되지 않음
	4. ``` a[title |="us"] ``` : 해당 속성과 일치하거나 일치한 단어 + '-'(하이픈) 로 된 요소
		- title="us", title="us-english" 둘다 해당됨
	5. ``` a[title ^="en"] ``` : 해당 속성으로 시작(startsWith)
		- title="en", title="english" 둘다 해당됨
	6. ``` a[href $="xls"] ``` : 해당 속성으로 끝남(endsWith)
		- href="intro.xls" 해당 됨
	7. ``` a[href *="xls"] ``` : 해당 속성과 일부 일치하는 요소(like 검색)
