## 13. CSS3와 애니메이션
1. 변형: transform
  - 회전, 이동 등의 변형
  - 2차원 변형: (0, 0) >> x, y
  - 3차원 변형: (0, 0, 0) >> x, y, z
  - transform과 변형 함수
    - ``` { transform: translate(50px, 100px); } ```
    - 2차원 변형 함수
      - 일부 지원되지 않는 브라우저가 있어 접두사 필요할 수 있음
      - translate(x, y): (x, y)로 이동. translateX(x), translateY(y) 도 있음
      - scale(x, y): (x, y)축으로 확대/축소. scaleX(x), scaleY(y)도 있음
      - rotate(angle): (angle) 각도만큼 회전
      - skew(angleX, angleY): (angleX, angleY) 각도만큼 외곡. skewX(angleX), skewY(angleY) 도 있음
        <style lang="scss">
          .ex-13-1-2d {
            width: 100px;
          }

          .translate:hover {
            transform: translate(-20px, -5px);
          }

          .scale:hover {
            transform: scale(2, 2);
          }

          .rotate:hover {
            transform: rotate(-5deg);
          }

          .skew:hover {
            transform: skew(10deg, 10deg);
          }

        </style>

        <div class="ex-13-1-2d translate">translate</div>
        <div class="ex-13-1-2d scale">scale</div>
        <div class="ex-13-1-2d rotate">rotate</div>
        <div class="ex-13-1-2d skew">skew</div>

    - 3차원 변형 함수
      - matrix3d(
          <br /> a1, b1, c1, d1, // 선형 변환 1
          <br /> a2, b2, c2, d2, // 선형 변환 2
          <br /> a3, b3, c3, d3, // 선형 변환 3
          <br /> a4, b4, c4, d4  // translation
        ):
        - 4*4 행렬로 이동, 확대/축소, 회전 등
        - https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix3d()
        - https://www.w3.org/TR/css-transforms-1/#interpolation-of-2d-matrices
        - 행렬을 생성: http://ds-overdesign.com/transform/matrix3d.html
      - translate3d(x, y, z): (x, y, z) 만큼 이동. translateZ(z) 도 있음
        - https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate3d()
        - 단위: px 등

      - scale3d(x, y, z): 각 축에 맞추어 확대/축소. scaleZ(z) 도 있음
        - https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale3d()
        - 단위: 숫자만(배율을 지정, 1 == 원래 크기)

      - rotate3d(x, y, z, angle): 지정한 각도 만큼 회전
        - https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate3d()
        - rotateX(angle), rotateY(angle), rotateZ(angle) 도 있음

      - perspective(length): 입체적으로 보이는 깊이
        - https://developer.mozilla.org/en-US/docs/Web/CSS/perspective

        <style lang="scss">
          .ex-13-1-3d {
            width: 100px;
          }

          .matrix3d:hover {
            transform: matrix3d(1.1,0,0.09,0.001,0.00,1,0.05,0.001,-0.09,-0.05,1,0,2,4,6,1);
          }

          .translate3d:hover {
            transform: translate3d(5px, 10px, -15px);
          }

          .scale3d:hover {
            transform: scale3d(1.5, 1.5, 5);
          }

          .rotate3d:hover {
            transform: rotate3d(1, 0, 1, 45deg);
          }

          .perspective:hover {
            transform: perspective(50px);
          }

        </style>
        <div class="ex-13-1-3d matrix3d">matrix3d</div>
        <div class="ex-13-1-3d translate3d">translate3d</div>
        <div class="ex-13-1-3d scale3d">scale3d</div>
        <div class="ex-13-1-3d rotate3d">rotate3d</div>
        <div class="ex-13-1-3d perspective">perspective</div>
