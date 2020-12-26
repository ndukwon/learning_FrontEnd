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

3. 가상 클래스와 가상 요소
	- 사용자 동작에 반응하는 가상 클래스
		```
		<style>
			:link {~~}     // 방문하지 않은 링크
			:visited {~~}  // 방문한 링크
			:hover {~~}    // 마우스 커서 올려놓을 때
			:active {~~}   // 누르고 있을때, 클릭 했을때(활성화)
			:focus {~~}    // 마우스를 가져다 놓거나, tab 이동했을때

			// 동시에 적용해야 할땐 순서를 지켜야 함
		</style>
		```

	- UI 요소 상태에 따른 가상 클래스
		```
		<style>
			:enabled {~~}     // 사용 가능할때
			:disabled {~~}    // 사용 불가능 할때
			:checked {~~}     // 라디오/체크박스에서 선택했을때
		</style>
		```

	- 구조 가상 클래스
		```
		<style>
			:root {~~}                 // 문서의 root에 적용...?

			:nth-child(n) {~~}         // n번째 자식 요소. 홀수번째: odd/2n+1, 짝수번째: even/2n
			:nth-last-child(n) {~~}    // 끝에서 n번째 자식 요소
			:nth-of-type(n) {~~}       // 자식 중 n번째 동일한 태그(id, class를 사용하지 않으며, 여러 태그가 혼합일때)
			:nth-last-of-type(n) {~~}  // 자식 중 끝에서 n번째 동일한 태그(id, class를 사용하지 않으며, 여러 태그가 혼합일때)

			:first-child {~~}          // 첫번째 자식
			:last-child {~~}           // 마지막 자식
			:firt-of-type {~~}         // 자식 중 첫번째 동일한 태크
			:last-of-type {~~}         // 자식 중 마지막 동일한 태크

			:only-child {~~}           // 자식이 하나일때
			:only-of-type {~~}         // 자식 중 동일한 태그가 하나일때
		</style>
		```

	- 그 외 가상 클래스
		```
		<style>
			:target {~~}       // 같은 페이지의 앵커 목적지 스타일?
			:not() {~~}        // 해당 요소가 아닐때 적용
		</style>
		```

	- 가상 요소: 내용의 일부만 선택해 스타일을 적용하려 할때
		```
		<style>
			::first-line {~~}     // 첫번째 줄에 적용
			::first-letter {~~}   // 첫번째 글자에 적용. br태그 위치에 따라 인식 안될 수 있음

			::before {~~}         // 앞에 내용을 추가
			::after {~~}          // 뒤에 내용을 추가
		</style>
		```
