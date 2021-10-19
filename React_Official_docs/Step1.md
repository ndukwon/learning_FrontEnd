# Step1
1. 시작하기
  - https://ko.reactjs.org/docs/getting-started.html
  1. React 시도해보기
    - 온라인 플레이그라운드
        - https://codepen.io/pen?&editors=0010
        - https://codesandbox.io/s/new
        - https://stackblitz.com/edit/react-hqyvzr
    - 로컬용 template
        - https://raw.githubusercontent.com/reactjs/reactjs.org/main/static/html/single-file-example.html
  2. React 배우기
    - 온라인 자습서
        - https://ko.reactjs.org/tutorial/tutorial.html
    - 주요개념
        - https://ko.reactjs.org/docs/hello-world.html
    - 입문자 개요
        - https://www.taniarascia.com/getting-started-with-react/
    - 고급자 생각 넓히기
        - https://ko.reactjs.org/docs/thinking-in-react.html
    - 강좌들
        - https://ko.reactjs.org/community/courses.html
    - 용어사전
        - https://ko.reactjs.org/docs/glossary.html
  3. 최신정보
    - https://ko.reactjs.org/blog/2021/06/08/the-plan-for-react-18.html


2. 웹사이트에 React 추가
  1. 1분 내로 React 추가하기
    - 요약: id가 있는 div tag를 추가하고 그 dom에 React를 초기화 시키며 추가한다.
    - 1단계: HTML 파일에 DOM 컨테이너 설치
      ```html
        <div id="like_button_container"></div>
      ```
    - 2단계: 스크립트 태그 추가하기
      ```html
      <body>
        <!-- React를 실행. -->
        <!-- 주의: 사이트를 배포할 때는 "development.js"를 "production.min.js"로 대체하세요. -->
        <script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
        <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>

        <!-- 만든 React 컴포넌트를 실행. -->
        <script src="like_button.js"></script>
      </body>
      ```
    - 3단계: React 컴포넌트 만들기
        - like_button.js 파일에서
        ```Javascript
        // ... 복사했던 스타터 코드 ...
        const domContainer = document.querySelector('#like_button_container');
        ReactDOM.render(e(LikeButton), domContainer);
        ```
  2. 선택사항: JSX로 React 해보기
    - JSX는 필수가 아닌 선택사항
      ```html
      //  "좋아요" <button>을 표시
      return (
        <button onClick={() => this.setState({ liked: true })}>
          Like
        </button>
      );
      ```
    - JSX를 처리하기 위해 필요한 모듈
        - script로 추가
          ```html
          <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
          ```
        - npm으로 설정
          ```cmd
          // package 설치
          npm install babel-cli@6 babel-preset-react-app@3

          // 실행 >> 순수 JS로 만들어줌
          npx babel --watch src --out-dir . --presets react-app/prodㄴ
          ```
        - babel 공홈: https://babeljs.io/docs/en/babel-cli/

3. 새로운 React 앱 만들기
  1. 추천 툴체인
    - SPA 개발: Create React App
        - https://ko.reactjs.org/docs/create-a-new-react-app.html#create-react-app
        ```
        npx create-react-app my-app
        cd my-app
        npm start
        ```
    - 스태틱 서버 렌더링: Next.js
        - https://ko.reactjs.org/docs/create-a-new-react-app.html#nextjs
    - 정적 웹사이트: Gatsby
        - https://ko.reactjs.org/docs/create-a-new-react-app.html#gatsby
        - ex) https://www.nationalgeographic.co.uk/science
    - 더 많은 추천 툴체인
      - https://ko.reactjs.org/docs/create-a-new-react-app.html#more-flexible-toolchains

4. CDN 링크
  - @다음에 버전정보를 기입
  1. Development
    ```html
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    ```
  2. Production: 용량 및 성능 최척화된 배포용 버전
    ```html
    <script crossorigin src="https://unpkg.com/react@17/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js"></script>
    ```
  3. crossorigin
    - https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin
    - Header 확인 필요
      ```
      Access-Control-Allow-Origin: *
      ```
5. 배포 채널: 버전에 대한 이야기
  - Latest: stable versions
    > npm ~~ @latest
  - Next: Pre-release version 다음 나갈예정 버전
    > npm update react@next react-dom@next
  - Experimental: Next + 개발중인 것들의 버전
    >
