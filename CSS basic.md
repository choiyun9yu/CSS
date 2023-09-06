# Basic

[Doc](https://developer.mozilla.org/ko/docs/Web/CSS)
[button](https://inpa.tistory.com/entry/CSS-%F0%9F%92%8D-%EB%B2%84%ED%8A%BC-%EB%94%94%EC%9E%90%EC%9D%B8-%EB%AA%A8%EC%9D%8C)

### 1. CSS 선택자

#### 태그 선택자

    selector {

    }

#### 클래스 선택자

    .selector {

    }

#### ID 선택자

    #selector {

    }

#### 부모자식 요소 선택

A의 자식요소 중 B 선택

    selectorA > selectorB {

    }

#### 다중 조건 선택자

선택자 A와 선택자 B 적용

    selectorA, selectorB {

    }

#### 범용 선택자

    * {

    }

### 2. 추상(가상)클래스 선택자

선택자 뒤에 (:이벤트)를 붙이면 특정 이벤트 마다 적용 할 스타일 설정 가능

    selector:active;    // 클릭했을 때 스타일
    selector:hober;     // 마우스 올렸을 때 스타일
    selector:focus;     // 포커스가 갔을 때 스타일

    selector:link;      // 방문한적 없는 링크
    selector:visited;   // 이미 방문했던 링크에 적용할 스타일

    selector:first;     // 첫번째 요소
    selector:last;      // 마지막 요소

    selector:fist-child     // 첫번째 자식
    selector:last-child     // 마지막 자식

    selector:nth-child(2n+1)    // 홀수 번째 자식

### 3. CSS 사용자 지정 속성(--\*)

-   사용자 지정 속성은 적용 스코프를 {}로 설정
-   (--변수명: 값;)으로 선언
-   var(--변수명)로 사용

######

    body{값
        --변수명 : 값;
    }

    selector{
        속성 : var(--변수명, 대체값을 두번째 인자로 넣을 수있다.)
    }

### 4. display

block 태그와 inline 태그의 서로 다른 특성을 사용하여 다르게 보여지게 할때 사용

### 5. 케스케이드

우선순위가 높은 속성이 우선순위가 낮은 속성을 덮어쓴다.

우선순위

1. 속성 값 뒤에 !important 를 붙인 속성
2. HTML에서 style을 직접 지정한 속성
3. #id 로 지정한 속성
4. .클래스, :추상클래스 로 지정한 속성
5. 태그이름 으로 지정한 속성
6. 상위 객체에 의해 상속된 속성

### 6. 상속

부모태그의 정렬, 폰트색, 폰트크기 등을 상속 받는 것

## 속성

[materials](https://ofcourse.kr/css-course/%EC%86%8D%EC%84%B1)

### 1. width, height

### 2. margin, padding

### 3. box-sizing

### 4. color

### 5. font

### 6. text-align

### 7. background

### 8. border

### 9. border-radius

### 10. visibility

### 11. display

### 12. float

### 13. clear

### 14. position

### 15. cursor
