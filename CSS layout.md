# Layout

## 0. Position

-   relative : 요소 자기 자신을 기준으로 배치
-   absolute : 부모(조상) 요소를 기준으로 배치
-   fixed : 뷰포트 기준으로 배치
-   stickey : 스크롤 영역 기준으로 배치

#### 기타

현재 뷰포트의 높이에서 70픽셀을 뺀 값으로 설정

    .gcs-height{
        height: calc(100vh - 20px)
    }

## 1. flexbox

flexbox : 일차원으로 요소를 배치하는 방식, 가로 or 세로

### 1-1 flex-direction : 배치할 방향정하기

    flex-direction: row;                // 기본적으로 플렉스박스의 방향은 가로
    flex-direction: row-reverse;        // 가로방향이지만 오른쪽에서 왼쪽으로
    flex-direction: column;             // 세로방향
    flex-direction: column-reverse;     // 세로방향 아래에서 위로

### 1-2. justify-content, align-items : 정렬하기

기본적으로 기본축 방향으로 요소들을 정렬하고, 교차축 방향은 꽉채우게 된다.

-   Main Axis : 요소가 정렬되는 기본 축
-   Cross Axis : 기본 축의 수직인 방향

#### 기본축 정렬

    justify-content: center;        // 가운데 정렬
    justify-content: flex-end;      // 기본축 맨 끝 정렬
    justify-content: flex-start;    // 기본축 맨 앞 정렬
    justify-content: space-around;  // 요소 양쪽에 같은 공간을 주고 띄엄 띄엄
    justify-content: space-btwwen;  // 양끝을 꽉채우게 공간주면서 채움
    justyfy-content: space-evenly;  // 모두 동일한 공간을 주면서 띄엄 띄엄 채움

#### 교차축 정렬: 크기를 꽉채워서 정렬되던게 원래 크기로 변함

    align-items: center;        // 가운데 정렬
    align-items: flex-end;      // 교차축 맨 끝 정렬
    align-items: flex-start;    // 교차축 맨 앞 정렬
    align-items: strech;        // 교차축 꽉채우게 늘려서 배치, 이게 default

### 1-3. flex-wrap : 요소가 넘칠때 어떻게 처리할지

    flex-wrap: wrap;    // 넘치는 요소 교차축 방향으로 넘어가서 정렬된다.

### 1-4. gap : 요소 간격

    마진을 써도 되지만 좋은 코드는 아니다.
    gap: 숫자px;            // wrap으로 넘어가는 방향에도 같은 갭이 적용됨
    gap: 세로갭px 가로갭px  // 기본축/교차축과 상관없이 세로, 가로 순서이다.

### 1-5.flex-grow, flex-shrink, flex-basis : 크기는 어떻게 늘이거나 줄일지

    flex-grow: 1;   // 요소를 늘려서 빈공간을 꽉채우고 싶을 때 사용, 숫자는 값이 클스록 비례해서 더 늘어남
    flex-shrink: 1; // 너비나 높이가 넘쳐도 줄여서 맞춰줌, 숫자는 값이 클수록 비례해서 더 줄어듬, 0을쓰면 줄어들지 않고 고정됨

## 2. Grid

flex-box가 요소를 한방향으로 배치하는 것이라면 grid는 가로세로 두방향으로 배치한다.  
그리드는 요소를 왼쪽에서 오른쪽으로 그리고 위에서 아래로 배치한다.  
각 칸을 나누는 그리드 라인을 긋고 한칸을 그리드셀이라한다. 바둑판 처럼 배치 가능하다.

### 2-1. grid-template-rows(columns) : 격

    grid-template-columns: 100px 300px 100px;   세로 너비 사이즈 정함
    grid-template-rows: 200px 200px 100px;      가로 높이 사이즈 정함
    한번에 쓰기
    grid-template: rows값 먼저 쓰고 / columns 값 써주면 된다

    px로 정한그리드 셀의 크기는 고정이다.
    비율로 크기를 정하려면 1fr 1fr 1fr 이런식으로 입력하면 1:1:1 비율로 나뉜다.
    grid-template: 1fr 1fr 1fr / 1fr 1fr 1fr;

    크기에서 최대 최소 정하는 방법
    grid-template:
                1fr 1fr 1fr / minmax(200px, 300px) minmax(200px, 300px) minmax(200px, 300px);
                !주의 최대값에만 fr을 쓸 수 있음

    6등분하기
    grid-template:
                1fr 1fr 1fr /
                repeat(6, 1fr)

### 2-2. gap : 간격

    gap: 16px 32px; 하나만 쓰면 사방, 두개쓰면 세로, 가로 순서

### 2-3. grid-auto-rows(columns) : 크기 미리 정하기

    grid-auto-rows: 200px; grid-template에서 명시적으로 사이즈 정하지 않았을 때 참조할 디폴트 값 설정
    grid-auto-rows: 50px 100px 200px 값을 여러개 쓰면 값을 번갈아가면서 설정

### 2-4. grid-row(column), span : 원하는 위치에, 원하는 크기로 배치

    그리드 라인 번호로 설정, 여러라인에 걸치려면 시작라인/끝라인, 시작라인/ span 몇칸 으로 설정
    -숫자는 뒤에서부터 카운트임
    grid-row: 3 / span 2; 로우방향 3번 라인부터 2칸
    grid-column: 2/ span3; 컬럼방향 2번 라인부터 3칸

### 2-5. grid-area, grid-template-areas : 이름으로 배치

    각 요소에 이름을 붙이기 이름으로 배치하기
    grid-area: r;

    이름으로 배치하기
    grid-template-areas:
        "r g"
        "r b";
