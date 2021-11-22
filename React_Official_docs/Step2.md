# Step2: 주요 개념

## 1. Hello World
```Javascript
  ReactDOM.render(
    <h1>Hello, world!</h1>,
    document.getElementById('root')
  );
```
- 특정 ID DOM을 Root로 하여 React가 렌더링을 시작


## 2. Introducing JSX
```Javascript
const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);
```
- 마크업 + 로직이 담길 수 있는 파일
- 자동 세미콜론 삽입을 피하기 위해 괄호를 묶는게 좋다.
- 중괄호로 js 표현식을 삽입
- 자식을 포함할 수 있고, 자식이 없다면 />로 바로 닫아준다.
- 렌더되기 전 이스케이프 되어 XSS 공격이 방지된다.
  - https://www.w3.org/International/questions/qa-escapes#use
- Babel이 컴파일 하면 객체 형태가 된다.
  - Before
    ```Javascript
    const element = (
      <h1 className="greeting">
        Hello, world!
      </h1>
    );
    ```
  - After
    ```Javascript
    const element = React.createElement(
      'h1',
      {className: 'greeting'},
      'Hello, world!'
    );
    ```

## 3. Rendering Elements
- ReactDOM.render()를 여러번 부르더라도 변화된 DOM만 업데이트 한다.
  ```Javascript
  function tick() {
    const element = (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {new Date().toLocaleTimeString()}.</h2>
      </div>
    );
    ReactDOM.render(element, document.getElementById('root'));
  }

  setInterval(tick, 1000);
  ```
  - https://codepen.io/pen?&editors=0010

## 4. Components and Props
- function Components
  ```Javascript
  function Welcome(props) {
    return <h1>Hello, {props.name}</h1>;
  }
  ```
- class Components
  ```Javascript
  class Welcome extends React.Component {
    render() {
      return <h1>Hello, {this.props.name}</h1>;
    }
  }
  ```
- 컴포넌트의 이름은 항상 대문자로 시작
- 재사용 가능한 컴포넌트를 만드는것이 큰 규모에서 유리함
- props == readonly
- 순수함수 지향
  - 함수형 프로그래밍의 지향점
  - 외부의 상태를 변경하거나 인자의 상태를 직접 변경하는 부수효과를 없애는 것.
  - 그리하여 모듈화의 수준을 높이려 함.

## 5. State and Lifecycle
- state는 컴포넌트내에서만 제어됨
- componentDidMount / componentWillUnmount: DOM 렌더링 된 후 / DOM 삭제 될때
- state를 직접 수정하지 않기
- this.props와 this.state가 비동기적으로 업데이트될 수 있기 때문에 다음 state를 계산할 때 해당 값에 의존해서는 안 됩니다.
- 일반적으로 이를 “하향식(top-down)” 또는 “단방향식” 데이터 흐름이라고 합니다. 모든 state는 항상 특정한 컴포넌트가 소유하고 있으며 그 state로부터 파생된 UI 또는 데이터는 오직 트리구조에서 자신의 “아래”에 있는 컴포넌트에만 영향을 미칩니다.

## 6. Handling Events
- React의 이벤트는 소문자 대신 캐멀 케이스(camelCase)를 사용합니다.
- JSX를 사용하여 문자열이 아닌 함수로 이벤트 핸들러를 전달합니다.
  ```Javascript
  <button onClick={activateLasers}>
    Activate Lasers
  </button>
  ```
- Arrow function을 사용하면 렌더링 될 때마다 다른 콜백이 생성되어 하위도 추가 렌더링되어 성능저하 유발

```Javascript
<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
```

## 7. Conditional Rendering
1. if else로 엘리먼트를 변경
2. && 연산자 == if
  - true/false로 나오는 값이 아니라면 그 value가 렌더된다.
  ```Javascript
  render() {
    const count = 0;
    return (
      <div>
        { count && <h1>Messages: {count}</h1>}
      </div>
    );
  }

  ```
3. 삼항식 사용
  ```Javascript
  render() {
    const isLoggedIn = this.state.isLoggedIn;
    return (
      <div>
        {isLoggedIn
          ? <LogoutButton onClick={this.handleLogoutClick} />
          : <LoginButton onClick={this.handleLoginClick} />
        }
      </div>
    );
  }
  ```
4. null 리턴
  ```Javascript
  function WarningBanner(props) {
    if (!props.warn) {
      return null;
    }

    return (
      <div className="warning">
        Warning!
      </div>
    );
  }
  ```

## 8. Lists and Keys
- 항목의 순서가 바뀔 수 있는 경우 key에 인덱스를 사용하는 것은 권장하지 않습니다.
- Key는 형제 사이에서만 고유한 값이어야 한다.
- key를 받는 자식 컴포넌트는 자신의 key를 볼 수는 없다.
- (가독성을 위해) map() 함수가 너무 중첩된다면 컴포넌트로 추출 하는 것이 좋습니다.

## 9. Forms
## 10. Lifting State Up
## 11. Composition vs Inheritance
## 12. Thinking In React
