# Core Javascript
- https://www.coupang.com/vp/products/295759416?itemId=932616303&vendorItemId=5429606972&pickType=COU_PICK&q=%EC%BD%94%EC%96%B4+%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8&itemsCount=14&searchId=3c95bf81231949caa32085f3e617d45d&rank=1&isAddedCart=
- 저자 / 출판: 정재남 / 위키북스

## 목차
01. 데이터 타입
  1. 데이터 타입의 종류
  2. 데이터 타입에 관한 배경지식
  3. 변수 선언과 데이터 할당
  4. 기본형 데이터와 참조형 데이터
  5. 불변 객체
  6. undefined와 null
02. 실행 컨텍스트
  1. 실행 컨텍스트란?
  2. VariableEnvironment
  3. LexicalEnvironment
  4. this
03. this
  1. 상황에 따라 달라지는 this
  2. 명시적으로 this를 바인딩하는 방법
04. 콜백 함수
  1. 콜백 함수란?
  2. 제어권
  3. 콜백 함수는 함수다.
  4. 콜백 함수 내부의 this에 다른 값 바인딩 하기
  5. 콜백 지옥과 비동기 제어
05. 클로저
06. 프로토타입
07. 클래스


## 01. 데이터 타입
1. 데이터 타입의 종류
  - Primitive type
    - Number: 64 bytes
    - String
    - Boolean
    - null
    - undefined
    - Symbol: 화면에 떠있는 동안 절대 같은 값을 가질 수 없는것, Map의 KEY로 쓰이면...
  - Reference type
    - Object
      - Array
      - Function
      - Date
      - RegExp
      - Map

2. 데이터 타입에 관한 배경지식
  - 변수 == 데이터
  - 변수명 == 식별자

3. 변수 선언과 데이터 할당
  - 변수 영역이 데이터 영역을 참조 >> 중복된 데이터에 대한 처리 효율 좋아짐

4. 기본형 데이터와 참조형 데이터
  - 기본형 데이터: 불변값. 기존에 있던것에서 찾아보고 있으면 쓰고, 없으면 새로 만든다.
  - 참조형 데이터: 그 내부의 데이터는 변경가능
  - GC: Mark & sweep

5. 불변 객체
  - 얕은 복사, 깊은 복사, JSON 변환 복사

6. undefined와 null
  - System의 undefined:
    - 값을 대입하지 않았을때
    - 존재하지 않을때
    - return이 없을때
  - 명시적 undefined:
    - 그 값의 자리를 차지하고 있기 때문에 다른의미
    - 차라리 null을 쓸 것
  - null: object이기 때문에 typeof를 쓸 수 없다.


## 02. 실행 컨텍스트
1. 실행 컨텍스트란?
  - 실행할 코드에 제공할 환경 정보들을 모아놓은 객체
  - call stack의 top이 현재의 시점

  - VariableEnvironment
    - environmentRecord
    - outerEnvironmentReference
  - LexicalEnvironment
    - environmentRecord
    - outerEnvironmentReference
  - ThisBinding

2. VariableEnvironment - LexicalEnvironment 최초의 컨텍스트 스냅샷
3. LexicalEnvironment
  - environmentRecord: 호이스팅
    - hoisting: 선언부분이 컨텍스트의 상위로 올라가서 가장 마지막에 선언된 변수 하나로만 동작하게 되는 상황
      - 함수도 미리 선언하고 써야 호이스팅에 영향받지 않는다.
    - typescript, ES6 기준: 이름을 다르게 쓰면 되지 않나? const, let을 쓰면 되고, 툴이 경고를 해주지 않나?
  - outerEnvironmentReference: 스코프체인
    - scope chain: 변수를 찾을때 environmentRecord (>> outerEnvironmentReference) * n 순서로 찾고
      가장 먼저 찾은 변수만 사용할 수 있다.
4. this
  - ThisBinding에는 this가 저장
  - this가 지정되지 않았을땐 전역객체


## 03. this
1. 상황에 따라 달라지는 this
  - this: 특정 객체의 프로퍼티로서 동작
  - 전역 객체
    - Browser: window
    - Node.js: global
    - 전역에 선언은 this.a = '~~' 혹은 var a = '~~' 해도 되지만
    - 전역의 변수를 삭제하는것은 선언한 방식과 완전히 동일해야 삭제가 된다.(의도치 않은 삭제 방지)
      - this.a = '~~' >> delete this.a
      - var a = '~~' >> delete a
  - Method로 호출(. 찍고 호출) : 해당 객체에 바인딩
    - constructor에서의 this도 해당
  - Function으로 호출(그냥 호출) : this === 전역 객체에 바인딩
    - Callback은 일반적으로 함수호출
2. 명시적으로 this를 바인딩하는 방법
  - self 등으로 this를 미리 저장하여 사용
  - 객체.메소드.call(this 로 지정할 인자, 원형의 인자들)
  - 객체.메소드.apply(this 로 지정할 인자, [원형의 인자들 배열])
  - 객체.메소드.bind(this 로 지정할 인자, 원형의 인자들)
    - 메소드 원형의 인자들 중 앞에서부터 몇개만 미리 지정 가능
    - bound [메소드 명] 으로 나오면 bind 된 것임
  - Arrow function: this가 아예 없으며 스코프체인상 가장 가까운 this

## 04. 콜백 함수
1. 콜백 함수란? - 제어권을 넘긴다.
2. 제어권 - 호출시점, 인자
3. 콜백 함수는 함수다. - 특정 객체에 바인딩 되지 않기 때문
4. 콜백 함수 내부의 this에 다른 값 바인딩 하기
  - this를 쓰면 재활용이 가능한데 이를 포기하고 안쓰는 것도 방법
  - bind를 써라.
5. 콜백 지옥과 비동기 제어
  1. 비동기적, 순차적으로 실행해야 할 것들을 모두 함수로 만들어 순차적으로 연결
    - 일회성 함수를 변수로 할당이 낭비
    - 순차적인 것을 모두 따라다녀야 하고 헷갈릴 수 있음
  2. promise 사용
    - promise로 감싸서 resolve/reject 로 진행여부를 결정하고 .then으로 순차적 연결
  3. generator 사용
    - \* function + yield 예약어로 순차적으로 연결 후 generator.next()로 다음 동작을 트리거
  4. promise + async + await 사용
    - (generator 방식과 유사하게) async function + await 예약어로 순차적으로 연결 후 실행

## 05. 클로저
- 유효범위가 사라진 후에도 사용할 수 있는 함수, 변수
1. 클로저의 의미 및 원리 이해
  - 유효범위가 사라진 후에도 사용할 수 있는 함수, 변수
  - V8엔진의 경우 선언한 위치는 GC 대상이지만 참조하는 변수가 하나라도 있어서 남겨두고 GC 된다.
2. 클로저와 메모리 관계
  - 클로저는 쓰고있기 때문에 남겨진 것. 누수로 볼 수 없지만 관리할 수 있어야 한다.
3. 클로저 활용 사례
  - 콜백 구현체에서 외부 데이터를 참조
  - 함수(getter, setter 등)만 주고 내부 변수는 가린다.
  - bind() 등으로 부분적으로 인자를 적용할때
  - 고차함수: 함수를 인자로 받거나 함수를 리턴하는 함수
  - Object.freeze(): 객체를 변경할 수 없게 한다.
4.
