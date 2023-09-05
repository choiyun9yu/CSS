# CSS

[button](https://inpa.tistory.com/entry/CSS-%F0%9F%92%8D-%EB%B2%84%ED%8A%BC-%EB%94%94%EC%9E%90%EC%9D%B8-%EB%AA%A8%EC%9D%8C)

### float와 overflow

#### float

요소를 왼쪽 또는 오른쪽에 배치할 때 유용한 속성  
float 속성을 부여한 요소의 다음 요소는 float 속성을 부여한 요소가 차지하는 위치만 제외하고 나머지 공간을 채운다.  
사이트 레이아웃을 만들 때 사용

#### overflow

내용이 요소의 크기를 벗어났을 때 어떻게 처리할지 정하는 속성  
내용이 주어진 공간에 다 들어가지 않을 때, 보여주게 할 수도 있고, 안보이게 할 수도 있고, 스크롤바를 만들게 할 수도 있다.

## Animation

!!주의!! height든 width든 애니메이션을 줄 때 초기값이 있어야지 초기값 부터 천천히 움직임

### 1. transiton(전환)

트랜지션은 CSS 프로퍼티의 값이 변화할 때, 프로피터 값의 변화가 일정시간에 걸쳐 일어나도록 하는 것  
상태 변화에 동반하여 변경되는 CSS 프로퍼티 값에 의한 표시 변화를 부드럽게 하기 위해 애니메이션 속도를 조절

#### 속성

-   transition : 모든 transition 속성을 이용한 스타일을 한 줄에 설정
-   transition-property : 요소에 추가할 전환 효과 설정
-   transition-duration : 전환 효과가 지속될 시간을 설정
-   trainsition-timing-fuction : 전환 효과의 시간당 속도를 설정
-   transition-delay : 전환 효과가 나타나기 전까지으 지연시간 설정

### 2. transform

#### 2D Transform

-   translate(x,y) : 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 이동시킨다. | px, %, em 등
-   translateX(n) : 요소의 위치를 X축으로 x만큼 이동시킨다. | px, %, em 등
-   translateY(n) : 요소의 위치를 Y축으로 y만큼 이동시킨다. | px, %, em 등
-   scale(x,y) : 요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수
-   scaleX(n) : 요소의 크기를 X축으로 x배 확대 또는 축소 시킨다. | 0과 양수
-   scaleY(n) : 요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수
-   skew(x-angle,y-angle) : 요소를 X축으로 x 각도만큼, Y축으로 y 각도만큼 기울인다. / +/- 각도(deg)
-   skewX(x-angle) : 요소를 X축으로 x 각도만큼 기울인다. | +/- 각도(deg)
-   skewY(y-angle) : 요소를 Y축으로 y 각도만큼 기울인다. | +/- 각도(deg)
-   rotate(angle) : 요소를 angle만큼 회전시킨다. | +/- 각도(deg)

#### 3D Transform

-   translate3d(x,y,z) : 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 Z축으로 z만큼 이동시킨다. | px, %, em 등
-   translateX(n) : 요소의 위치를 X축으로 x만큼 이동시킨다. | px, %, em 등
-   translateY(n) : 요소의 위치를 Y축으로 y만큼 이동시킨다. | px, %, em 등
-   translateZ(n) : 요소의 위치를 Z축으로 z만큼 이동시킨다. | px, %, em 등
-   scale3d(x,y) : 요소의 크기를 X축으로 x배, Y축으로 y배, Z축으로 z배 확대 또는 축소 시킨다. | 0과 양수
-   scaleX(n) : 요소의 크기를 X축으로 x배 확대 또는 축소 시킨다. | 0과 양수
-   scaleY(n) : 요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다. | 0과 양수
-   scaleZ(n) : 요소의 크기를 Z축으로 z배 확대 또는 축소 시킨다. | 0과 양수
-   rotate3d(x,y,z) : 요소를 X축으로 x각도, Y축으로 y각도, Z축으로 z각도 회전시킨다. | +/- 각도(deg)
-   rotateX(x) : 요소를 X축으로 x각도 회전시킨다. | +/- 각도(deg)
-   rotateY(y) : 요소를 Y축으로 y각도 회전시킨다. | +/- 각도(deg)
-   rotateZ(z) : 요소를 Z축으로 z각도 회전시킨다. | +/- 각도(deg)

### 3. animation

animation은 실행할 애니메이션 속성을 지정하는 단계

#### 3-1. animation 속성

    div {
        animation-name: bgmove;
        animation-duration: 2s;
        animation-delay: 1s;
        animation-iteration-count: infinite;
        animation-timing-function: ease-out;
        animation-direction:reverse;
    }

-   animation-name : keyframe에 적용할 애니메이션 이름(자유롭게)
-   animation-duration : 애니메이션이 완료될때까지 걸리는 시간
-   animation-timing-function : 애니메이션 실행 속도
-   animation-delay : 애니메이션이 시작하기 전 지연시간
-   animation-iteration-count : 반복 횟수
-   animation-direction : 애니메이션 방향 (앞으로, 뒤로 또는 번갈아 재생해야하는지 여부)
    -   normal : 기본 값 (forwards)
    -   reverse : 애니메이션이 역방향으로 진행 (backwards)
    -   alternate : 애니메이션이 기본값으로(앞) 진행된 후 역방향으로 번갈아 진행
    -   alternate-reverse : 애니메이션이 역방향으로(뒤) 진행된 후 앞으로 번갈아 진행
-   animation-fill-mode : 애니메이션 시작 전, 끝나기 전(또는 둘다) 스타일을 지정
    -   none : 기본값 (따로 적용되지 않음)
    -   forwards : 마지막 키 프레임에 의해 설정된 스타일 값을 유지 (애니메이션 방향 및 애니메이션 반복 횟수에 따라 다름)
    -   backwards : 첫 번째 키 프레임에 설정된 스타일 값을 가져오고 (애니메이션 방향에 따라 다름) 애니메이션 지연 기간 동안이 값을 유지
    -   both : 애니메이션은 앞뒤 모두에 대한 규칙을 따름
-   animation-play-state : 애니메이션 실행 여부 (실행 or 일시정지)
    -   paused : 애니메이션 일시중지
    -   running : 기본값 (애니메이션 실행)
-   [example](https://www.w3schools.com/cssref/css3_pr_animation.asp)

### 4. @keyframes

@keyframes는 애니메이션의 스타일을 구체적으로 제어하는 단계

    @keyframes animationname {keyframes-selector {css-styles;}}

    // animation에서 지정했던 animationname을 지정(반드시 같은 이름으로)
    // animation의 구체적인 단계를 지정하고 css 스타일을 적용
    @keyframes bgmove {
        from {top: 0px;}    // from은 애니메이션의 시작 부분
        to {to: 200px;}     // to는 애니메이션 끝 부분
    }

    // 0% ~ 100% 까지 나눠서 주기
    @keyframes hideSplashScreenIcon {
    0% {
        transform: none;
    }

    25% {
        transform: scale(2);
    }

    50% {
        transform: scale(1.7);
    }

    75% {
        transform: scale(2.1);
    }

    100% {
        transform: none;
    }
    }

[ref](https://yzink.tistory.com/102)
[ref](https://www.codingfactory.net/12593)
[ref](https://inpa.tistory.com/entry/CSS-%F0%9F%93%9A-%ED%8A%B8%EB%9E%9C%EC%A7%80%EC%85%98-%ED%8A%B8%EB%9E%9C%EC%8A%A4%ED%8F%BC-%EC%95%A0%EB%8B%88%EB%A9%94%EC%9D%B4%EC%85%98)
