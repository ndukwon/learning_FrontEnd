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
- 

## 5. State and Lifecycle
## 6. Handling Events
## 7. Conditional Rendering
## 8. Lists and Keys
## 9. Forms
## 10. Lifting State Up
## 11. Composition vs Inheritance
## 12. Thinking In React
