# bootstrap_study
부트스트랩 공부한 내용을 기록하는 리포지토리 입니다.
</br>

참고한 문서 : https://getbootstrap.kr/docs/5.3/getting-started/introduction/

</br>

## 목차
1. [Getting Start](#1.-Getting-Start)
  - Starter Template
  - RFS (Responsive Font Size)
  - RTL (Right To Left)
2. [Customize](#2.-Customize)
  - Sass
  - Component
  - CSS variable 
3. [Layout](#3.-Layout)
  - Breakpoints
  - Containers
  - Grid System
  - Columns
  - Gutters
4. [Contents](#4.-Contents)
  - Reboot
  - Typography
  - Image
  - Table
5. [Forms](#5.-Forms)
  - overview
  - form-control
  - select
  - checkbox & radio-button
  - range
  - input group
  - floating labels
  - layout
6. [Component](#6.-Component)
  - alerts
  - badges
  - breadcrumb
  - buttons
  - button group
  - card
  - carousel
  - close button
  - collapse
  - dropdown
  - list group
  - modal
  - navbar
  - navs and tabs
  - pagination
  - placeholders
  - popovers
  - progress
  - scrollspy
  - spinners
  - toasts
  - tooltips

</br>
</br>

## 1. Getting Start
<details>
<summary> 1-1. Starter Template</summary>
<div markdown="1">

### Starter Template

```css
<!doctype html>
<html lang="ko">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>

  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>

    <!-- Option 2: Separate Popper and Bootstrap JS -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js" integrity="sha384-IQsoLXl5PILFhosVNubq5LC7Qb9DXgDA9i+tQ8Zj3iwWAwPtgFTxbJ8NT4GN1R8p" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@3.0.2/dist/js/bootstrap.min.js" integrity="sha384-cVKIPhGWiC2Al4u+LWgxfKTRIcfu0JTxR+EQDz/bgldoEyl4H0zUF0QKbrJ0EcQF" crossorigin="anonymous"></script>
    -->
  </body>

</html>
```

### Meta 태그

 meta 태그는 <head></head>요소 내부에 위치하는 특수 태그로, 웹 서버와 웹 브라우저 간에 상호 교환되는 정보를 정의하는데 사용합니다. 사이트의 디자인에는 전혀 영향을 미치지 않고 문서의 내용, 키워드, 누가 만들었는지 등의 `문서 자체의 특성`을 담고 있습니다.

 HTML5에서는 <meta> 요소를 통해 웹 페이지에서 사용자가 볼 수 있는 영역인 viewport를 제어할 수 있도록 name 속성에 viewport 속성값`(name=”viewport”)`을 제공하고 있습니다. 

- meta 태그 요소
    - `http-equiv`
        
        웹 브라우저가 서버에 명령을 내리는 속성. name 속성을 대신해 사용될 수 있으며, html 문서가 응답 헤더와 함께 웹 서버로부터 웹 브라우저에 전송되었을 때만 의미를 갖습니다. 
        
        - <meta `http-equiv="X-UA-Compatible"` content="IE=edge"/>
            - 브라우저 호환성을 지정
            - 항상 IE8 이상의 버전에서 **최신 표준모드**로 렌더링, 모든 IE 브라우저에 호환성 보기를 무시
            - 인터넷 익스플로러의 버전에 따라 렌더링 방식이 다르기 때문에 레이아웃이 깨지거나 작동하지 않을 수 있음
        - <meta `http-equiv="Expires"` content="1"/>
            - 캐시 완료시간을 정의하고, 1분이 지나면 캐시를 지우고 값을 새로 읽어옴
        - <meta `http-equiv="Pragma"` content="no-cache"/>
            - 캐시가 되지 않게 하는 태그(매번 새로운 페이지를 엶)
        - <meta `http-equiv="Content-Type"` content="text/html”; charset=utf-8">
            - 웹문서의 언어를 설정하는 태그
            - 한글을 인식하기 위해선 `charset=utf-8`로 설정해야 함
    - meta 예시 (name)
        - 몇 개의 meta 정보의 이름을 정할 수 있는 속성
        
        ```html
        <!--검색 엔진에 의해 검색되는 단어를 지정합니다-->
        <meta name="keyword" content="Web, html, 웹 표준"/>
        
        <!--검색 결과에 표시되는 문자를 지정합니다-->
        <meta name="description" content="HTML meta tag page"/>
        
        <!--문서의 저자를 정의하는 예제-->
        <meta name="author" content="TCPSchool"/>
        
        <!--모든 장치에서 웹 사이트가 잘 보이도록 뷰포트를 설정하는 예제-->
        <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
        
        <!--날짜(제작일)-->
        <meta name="Date" content="2016-02-15T07:45:37+09:00" />
        ```
        
    - content
        - meta 정보의 내용을 지정
        - name 이나 http-equiv 속성이 명시 되었다면 반드시 포함되어야 하는 속성, 두 속성이 없다면 사용하지 않아도 됨
        
        - meta Robots : name이 robots인 메타 태그의 content에 대한 설명
        
        ```
        <!--content 속성에 지정할 수 있는 값은 다음과 같습니다.-->
        기본 index, follow의 긍정, 부정값의 조합
        1. All(기본값) : 'index, follow'
        2. None : 'noindex, nofollow'
        3. Index : 그 페이지를 수집 대상으로 함
        4. Follow : 그 페이지를 포함해 링크가 걸린 곳을 수집 대상으로 함
        5. Noindex : 그 페이지를 수집대상에서 제외
        6. Nofollow : 그 페이지를 포함해 링크가 걸린 곳을 수집 대상으로 하지 않음
        
        <meta name="Robots" content="noindex, nofollow" />
        ```
        

### Popper

포퍼는 위치 기반으로 `툴팁`과 `팝오버` 같은 UI 요소를 올바르게 배치해주는 `Javascript 라이브러리` 입니다. HTML 요소 사이의 상대적인 위치를 계산해 요소가 화면에 잘 나타나도록 도와줍니다. 용량이 작아 사용감이 좋다는 장점이 있습니다. 

- 부트스트랩에서 popper가 `있는 버전`과 `없는 버전`으로 나눈 이유
    - 부트스트랩은 버전4까지는 Popper를 이용해 툴팁과 팝오버 같은 UI 요소의 위치를 관리
    - 버전5부터는 부트스트랩 자체적으로 개발한 Popper 기능을 사용하고 있어 boostrap5부터는 별도의 Popper.js 라이브러리를 포함할 필요가 없음
    - 부트스트랩 자체 popper를 가지면서 UI 요소의 위치 관리에 대한 성능과 유연성 향상

---

### HTML5 doctype

아래 코드를 추가해 html을 적용합니다. 이 부분이 없다면, funky incomplete styling의 페이지를 만들 수 있습니다. 

```css
<!doctype html>
<html lang="en">
  ...
</html>
```

### Responsive meta tag

```css
<!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
```

`<meta charset=”utf-8”>` : html 파일의 인코딩을 알려주는 코드, 브라우저에게 text 표현 방식을 알려주는 방식. 이 태그가 없으면 한글, 특수문자들이 깨져서 나올 수 있습니다.

`<meta name~> :` 두 번째 meta를 추가해야 반응형 화면을 구현할 수 있습니다. 

### Bootstrp CSS

이거를 추가하면 부트스트랩에서 미리 정의된 components를 불러와 사용할 수 있습니다. 

```css
<!-- Bootstrap CSS --> 
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
```

### JavaScript

js에는 두 가지 버전이 있는데, 이는 popper의 유무 차이입니다. 

- Bundle : popper를 번들로 포함한 소스 코드

```css
<!-- Option 1: Bootstrap Bundle with Popper -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
```

- Separate : popper를 포함하지 않은 소스 코드로, popper가 먼저 선행 되어야 함

```css
<!-- Option 2: Separate Popper and Bootstrap JS -->
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js" integrity="sha384-IQsoLXl5PILFhosVNubq5LC7Qb9DXgDA9i+tQ8Zj3iwWAwPtgFTxbJ8NT4GN1R8p" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.min.js" integrity="sha384-cVKIPhGWiC2Al4u+LWgxfKTRIcfu0JTxR+EQDz/bgldoEyl4H0zUF0QKbrJ0EcQF" crossorigin="anonymous"></script>    
```

</div>
</details>

<details>
<summary> 1-2. RFS </summary>
<div markdown="1">
**RFS**는 글꼴 크기를 조절하기 위해 만들어졌던 유닛 크기 조절 엔진입니다.

`margin`, `padding`, `border-radius`, `box-shadow`의 단위 값으로 대부분의 css 속성의 크기를 조정할 수 있습니다. 

rem 값 및 view port 단위가 혼합된 `calc()함수`를 컴파일하고, 이를 통해 반응형 스케일링 동작을 활성화할 수 있습니다. 

- calc() 함수
    - 괄호 안의 식을 계산한 결과를 속성값으로 사용하게 해주는 함수
    - 반응형이나 모바일 코딩을 할 때, %로 값을 주기 애매한 것들이 있는데, calc()를 사용해 position, absolute, fixed를 사용하면 정확한 px값을 지정해줄 수 있습니다.
    
    ```css
    // calc() 적용 가능한 필드
    width, height, margin, padding
    
    // 예시
    width:calc(100%/7);
    widht:calc(100px + 5px); 
    ```
    
- calc() 사용시 티
    - 모든 계산은 왼쪽 → 오른쪽
    - 우선순위 : 곱하기, 나누기 > 더하기, 빼기
    - 오페라 브라우저, IE9 미만의 브라우저에서는 지원 불가능
    - 호환성을 위해 -moze, -webkit 같은 `vendor-prefix`를 먼저 작성
    - calc(50% - 10px)와 같이 다른 단위 값 사용가능
    - 더하기/빼기에는 앞뒤 공백이 필수이지만, 곱하기/나누기에는 공백이 없어도 됩니다

### RFS 사용하기

믹스인은 Bootstrap에 포함되어 있으며, `Bootstrap의 scss를 포함`하면 사용할 수 있습니다. 필요하면 RFS를 독립형으로 설치할 수도 있습니다. 

rfs() 믹스인의 약어들

- `font-size`
    
    ```css
    .title {
    	@include font-size(4rem);
    }
    
    .title {
    	font-size: calc(1.525rem + 3.3vw)
    }
    
    // 최소 가로가 1200픽셀인 반응형 화면
    @media (min-width: 1200px) {
    	.title {
    		font-size: 4rem; /*4rem == 64px*/ 
    	}
    }
    
    .selector {
    	@include rfs(4rem, border-radius);
    }
    ```
    
- `margin` 관련 : margin, margin-top, margin-right, margin-bottom, margin-left
- `padding` 관련 : padding, padding-top, padding-right, padding-bottom, padding-left
    - `!important` : 나중에 설정한 값이 적용되지 않게 하는 단어
    
    ```css
    .selector {
    	@include padding(2.5rem !important);
    }
    ```
    

포함해서 사용하고 싶지 않으면, rfs-value()나 rfs-fluid-value()를 사용할 수 있습니다. 

- `rfs-value()` : px 값이 전달되면 값을 rem 값으로 변환하고, px 값이 아니라면 동일한 결과를 반환합니다.
- `rfs-fluid-value()` : 속성 크기를 조정해야할 때 값의 유동적 버전을 반환합니다.
    
    ```css
    .selector {
    	// lg 중단점 아래에만 스타일을 적용합니다. 
      @include media-breakpoint-down(lg) {
        padding: rfs-fluid-value(2rem);
        font-size: rfs-fluid-value(1.125rem);
      }
    }
    ```
    
    `→ 여기서 가져가야 할 것 : rem, vw 는 알아야함!!!!`
  
</div>
</details>


<details>
<summary>1-3. RTL </summary>
  <div>
    오른쪽에서 왼쪽으로 쓰는 텍스트를 사용해야 할 때 추가하는 설정입니다.

### RTL 사용하기 위한 조건

1. <html> 안에 `dir=”rtl”`을 설정 해야합니다. 
2. <html> 안에 `lang=”ar”`와 같이 적절한 lang 속성을 추가합니다. 

RTL이 활성화되고, 컴파일 경량화된 CSS의 스타일시트

```css
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.rtl.min.css" integrity="sha384-gXt9imSW0VcJVHezoNQsP+TNrjYXoGcrqBZJpry9zJt8PCQjobwmhMGaDHTASo9N" crossorigin="anonymous">
```

### RTL을 반영한 시작 템플릿

html 태그 안에 lang=”ar”, dir=”rtl”이 반영 되어있고, <head> 태그 안에 위에서 언급한 css 스타일시트가 포함된 것을 확인할 수 있습니다. 

```css
<!doctype html>
<html lang="ar" dir="rtl">

  <head>
...
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.rtl.min.css" integrity="sha384-gXt9imSW0VcJVHezoNQsP+TNrjYXoGcrqBZJpry9zJt8PCQjobwmhMGaDHTASo9N" crossorigin="anonymous">
		
		<title>مرحبا بالعالم!</title>
...
  </head>

  <body>
...
  </body>

</html>
```
  </div>
</details>


</br>
</br>

## 2. Customize

<details>
<summary> 2-1. Sass</summary>
  <div markdown="1">
    CSS의 단점(동일한 코드 재사용을 위한 중복, 변수 선언 불가능)을 보완한 확장 언어입니다.

컴파일 과정을 통해 CSS 파일을 생성해 줘 코드 작성에 드는 시간을 줄여주고, 코드를 관리하는데 도움을 줍니다. sass, scss는 변수 선언이 가능합니다.

Sass의 `장점`

- 하나의 컴파일러로 모두 컴파일 가능
- 오래된 CSS 확장 언어기에 많은 커뮤니티를 가지고 있음

### Sass로 스타일시트 생산하는 방법

- Sass가 제공하는 문법 기반으로 코드 작성
- 컴파일 → CSS 파일 빌드

SCSS는 전처리기로, 표준 CSS보다 훨씬 많은 기능으로 편리하게 코드를 작성할 수 있습니다. 

하지만 웹에서는 CSS만 동작하므로 작성한 전처리기를 웹에서 동작 가능한 `표준의 CSS로 컴파일` 합니다. 

- Sass vs. SCSS
    
    Sass:
    
    중괄호, 세미콜론을 사용하지 않아 코드가 깔끔하고, 더 간결하고 작성하기에 편리합니다. 
    
    ```css
    .list
      width: 100px
      float: left
      li
        color: red
        background: url("./image.jpg")
        &:last-child
          margin-right: -10px
    ```
    
    SCSS:
    
    중괄호, 세미콜론 있지만 인라인 코드를 작성할 수 있고, CSS와 유사한 문법을 가지기 때문에 코드 통합이 훨씬 쉽습니다. 보통의 경우 SCSS를 주로 사용합니다. 
    
    ```css
    .list {
      width: 100px;
      float: left;
      li {
        color: red;
        background: url("./image.jpg");
        &:last-child {
          margin-right: -10px;
        }
      }
    }
    ```
    

### 패키지 매니저를 사용하지 않는 프로젝트의 파일 구조

```css
your-project/
├── scss
│   └── custom.scss
└── bootstrap/
    ├── js
    └── scss
```

custom-element 클래스의 색깔과 배경 색깔을 설정하는 코드

```css
.custom-element {
	color: $gray-100;
	background-color: $dark;
}
```

### 더하기 및 빼기

더하기와 빼기는 calc()함수를 이용할 수도 있고, add(), subtract() 함수를 이용해 구현할 수 있습니다. 

calc()는 식에 0이 들어갔을 때 에러가 발생할 수 있으므로 식에 0이 있는 경우에 `add()`, `subtract()`를 이용할 수 있습니다.

```css
$border-radius: .25rem;
$border-width-nonzero: 1px;
$border-width-zero: 0px;

// valid, Output calc(.25rem - 1px)
.element {
	border-radius: calc($border-radius - $border-width-nonzero);
}

// valid, Output calc(.25rem - 1px)
.element {
	border-radius: subtract($border-radius - $border-width-nonzero);
}

// invalid, calc(.25rem - 0px)
.element {
	border-radius: calc($border-radius - $border-width-zero);
}

// valid, Output : .25rem
.element {
	border-radius: subtract($border-radius - $border-width-zero);
}
	
```

### 색상 스킴(scheme)

- `prefers-color-scheme`은 미디어(media) 쿼리의 간단한 믹스인 입니다
- light, dark, 사용자 정의 색상 배합을 지원합니다

```css
@mixin color-scheme($name) {
	@media (prefers-color-scheme: #($name}) {
		@content;
	}
}
```

```css
.custom-element {
	@include color-scheme(dark) {
		// 다크 모드 스타일 삽입
	}
	
	@include color-scheme(custom-name-scheme) {
		// 사용자 설정 스킴 스타일 삽입
	}
}
```
  </div>
</details>

<details>
<summary> 2-2. Component</summary>
  <div markdown="1">
    Bootstrap의 컴포넌트는 주로 기본-제어자 명명법으로 만들어졌습니다. 

이는 가장 상위 클래스에서 하위로 내려가면서 그룹화하기 용이 합니다. 

예) 기본 클래스 : `.btn`같은 기본 클래스

제어자 클래스 : `.btn-primary`, `.btn-success`

위에서 정의한 제어자 클래스는 $theme-colors 맵에서 구축되어 제어자 클래스 수와 이름을 재정의 합니다. 

```css
$theme-colors: (
  primary: #007bff,
  secondary: #6c757d,
  success: #28a745,
  // ... 다른 색상들 ...
);
// primary, secondary, success 는 색상 이름
```

- 예시 코드 ($theme-colors 맵을 반복해 .alert 컴포넌트 제어자 생성)
    
    ```jsx
    // Generate contextual modifier classes for colorizing the alert
    
    @each $state, $value in $theme-colors {
      $alert-background: shift-color($value, $alert-bg-scale);
      $alert-border: shift-color($value, $alert-border-scale);
      $alert-color: shift-color($value, $alert-color-scale);
    
      @if (contrast-ratio($alert-background, $alert-color) < $min-contrast-ratio) {
        $alert-color: mix($value, color-contrast($alert-background), abs($alert-color-scale));
      }
      .alert-#{$state} {
        @include alert-variant($alert-background, $alert-border, $alert-color);
      }
    }
    ```
    
- 예시 코드 ($theme-colors 맵을 반복해 .list-group 컴포넌트 제어자 생성)
    
    ```jsx
    // List group contextual variants
    // Add modifier classes to change text and background color on individual itmes.
    // Organizationally, this must come after the ':hover' states
    
    @each $state, $value in $theme-colors {
      $list-group-variant-bg: shift-color($value, $list-group-item-bg-scale);
      $list-group-variant-color: shift-color($value, $list-group-item-color-scale);
      @if (contrast-ratio($list-group-variant-bg, $list-group-variant-color) < $min-contrast-ratio) {
        $list-group-variant-color: mix($value, color-contrast($list-group-variant-bg), abs($list-group-item-color-scale));
      }
    
      @include list-group-item-variant($state, $list-group-variant-bg, $list-group-variant-color);
    }
    ```
  </div>
</details>


<details>
<summary> 2-3. CSS variable</summary>
  <div markdown="1">
    이 변수는 브라우저 검사기, 코드 샌드박스, 일반 프로토타입을 작업할 때 `테마 색상, 중단점, 주요 글꼴 스택`과 같이 일반적으로 자주 사용되는 값에 대해 간단한 접근을 제공합니다.

제 3의 css와의 충돌을 피하기 위해 모든 사용자 정의 속성 앞에 `bs-`(bootstrap)가 붙습니다.

이 css 변수들은 _root.scss에 위치해 있고, 컴파일된 dist 파일에 포함되어 있습니다. :root를 명시한 뒤 사용할 수 있습니다. 

```jsx
// 예시 코드

:root {
  --bs-blue: #0d6efd; 
  --bs-indigo: #6610f2;
  --bs-purple: #6f42c1;
	--bs-font-sans-serif: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  --bs-font-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  --bs-gradient: linear-gradient(180deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0));
}
```

### 접두사

사용자가 작성한 코드와 충돌을 피하기 위해 CSS 변수는 앞에  `--` 접두사를 붙입니다. 

기본값은 `bs-` 입니다.

```jsx
// 예시 코드 

.ex {
  --color: red; // 여기에서의 --color는 기존의 color와는 다른 속성입니다.
  color: blue;
}

body {
  font: 1rem/1.5 var(--bs-font-sans-serif);
}
a {
  color: var(--bs-blue);
}
```
    
  </div>
</details>

</br>
</br>

## 3. Layout
<details>
<summary> 3-1. breakpoints</summary>
  <div markdown="1">
  브레이크 포인트는 반응형 레이아웃이 장비에서 어떻게 행동할 지 커스터마이징 할 수 있는 가로입니다. 

### Breakpoints 핵심 개념

- **`Breakpoints` aret he building blocks of responsive design**
    - 부트스트랩을 사용해 특정 뷰포트나 장치 사이즈를 조절할 수 있음
- **Use `media queries` to architect your CSS by breakpoint**
- **Mobile first, responsive design is the goal**

각 breakpoint에는 고유한 컨테이너/클래스 접두어/수정자가 있습니다. 

### 가능한 breakpoints

부트스트랩에는 6개의 기본 breakpoints가 있습니다. 만약 Sass 파일을 사용한다면 breakpoints도 커스터마이즈 할 수 있습니다. 

width는 12의 배수

예시 (Breakpoint : Class infix, Dimensions 순)

- Extra small : NONE, <576px
- small : sm, ≥576px
- Medium :md, ≥768px
- Large : lg, ≥992px
- Extra large : xl, ≥1200px
- Extra extra large : xxl, ≥1400px

### Media queries

- min-width
    
    ```css
    // 'xs' 사이즈는 media query가 없습니다.
    
    @media (min-width: 576px) { ... } // 핸드폰 같이 작은 장비
    @media (min-width: 768px) { ... } // 태블릿
    @media (min-width: 992px) { ... } // 데스크탑
    @media (min-width: 1200px) { ... } // 1200px 이상의 큰 데스크탑
    @media (min-width: 1400px) { ... } // 1400px 이상의 큰 데스크탑
    ```
    
- max-width
    
    max-width에서는 위 코드와 동일하나 px 값을 .02px을 뺀 값으로 설정해야합니다. 
    
    `0.02px 값을 빼는 이유` : 브라우저는 range context queries를 지원하지 않기 때문에 **더 높은 정밀도의 값**을 사용해 분수너비가 있는 min-, max- 접두사 및 뷰포트의 제한 사항을 해결합니다.
    
    ```css
    // 'xs' 사이즈는 media query가 없습니다.
    
    @media (max-width: 575.98px) { ... } // 핸드폰 같이 작은 장비
    @media (max-width: 767.98px) { ... } // 태블릿
    @media (max-width: 991.98px) { ... } // 데스크탑
    @media (max-width: 1199.98px) { ... } // 1200px 이하의 큰 데스크탑
    @media (max-width: 1399.98px) { ... } // 1400px 이하의 큰 데스크탑
    ```
    
- break point `width 여러개` 설정하기
    
    ```css
    @media (min-width: 768px) and (max-width: 1199.98px) { ... }
    ```
	
  </div>
</details>

<details>
<summary> 3-2. Containers</summary>
  <div markdown="1">
  컨테이너는 주어진 장치나 viewport 안에서 내용을 contain, pad, align하는 근본적인 빌딩 블록입니다.

### 작동 방식

컨테이너는 가장 기본적인 레이아웃 요소이고, 부트스트랩의 `기본 grid 시스템`을 이용하기 위해서는 필수입니다. 컨테이너는 contain, pad, center에 사용됩니다. 

- 부트스트랩의 3가지 컨테이너
    - `.container`
        - 각 반응형 breakpoint에 max-width를 설정
    - `.container-(breakpoint)`
        - 특정 breakpoint까지 width : 100% 설정
    - `.container-fluid`
        - 모든 breakpoint에 100% 설정

- container 예시
    - 각 사이즈(sm, md,,)의 breakpoint에 도달하기 전까지는 width=100%
    
    ### Default Container
    
    부트스트랩의 `.container`는 breakpoint 마다 max-width가 변경되는 반응형/fixed width 컨테이너 입니다. 
    
    기본으로 제공되는 크기는 다음과 같으며, Sass map에서 수정할 수도 있습니다. 
    
    ```css
    $container-max-widths: (
      sm: 540px,
      md: 720px,
      lg: 960px,
      xl: 1140px,
      xxl: 1320px
    );
    ```
	
  </div>
</details>

<details>
<summary> 3-3. Grid system </summary>
  <div markdown="1">
  부트스트랩의 grid system은 내용을 할당하고 layout하기 위해 `container, row, column 시리즈`를 사용합니다. 이는 flexbox에 있으며, 전적으로 반응형입니다. 

작동 방법

- 부트스트랩의 그리드는 **6개의 반응형 breakpoint**s를 가집니다
    - 컨테이너, 컬럼 크기/행동을 각 breakpoint로 조절할 수 있음을 의미
- 컨테이너는 콘텐츠를 중앙에 놓고 가로로 채웁니다
- **행은 열의 wrapper** 입니다
    - 행은 열 크기를 균일하게 적용하고, gutter class를 통해 콘텐츠의 간격을 변경하는 수정자 클래스를 지원합니다.
- **열(column)은 매우 유연**합니다
    - 행 당 12개의 템플릿 열을 사용할 수 있어 여러 열에 걸쳐 있는 다양한 요소 조합을 만들 수 있습니다.
- **Gutters는 반응형이고, 사용자 정의가 가능합니다**
    - Gutter 클래스는 모든 breakpoint에서 사용가능하고, margin/padding 간격과 같은 크기
    - 수평 gutter는 `.gx-*`, 수직 gutter는 `.gy-*`, 모든 gutter는 g-*로 변경합니다
    - `.g-0`은 gutter를 제거하는 데에 사용 가능합니다
- Sass 변수, 맵, 믹스인은 그리드를 구동합니다
    - bootstrap에서 미리 정의된 grid class를 사용하지 않으려면 grid의 Sass 소스를 추가해 직접 생성할 수 있습니다

### 열 자동 레이아웃

- **같은 너비** : 별다른 설정을 하지 않으면, 각 중단점에서 생성하는 **모든 열의 너비는 동일**
    - `<div class=”col”>`
    
    
    - html 코드
        
        ```html
        <div class="container">
          <div class="row">
            <div class="col">
              1 of 2
            </div>
            <div class="col">
              2 of 2
            </div>
          </div>
          <div class="row">
            <div class="col">
              1 of 3
            </div>
            <div class="col">
              2 of 3
            </div>
            <div class="col">
              3 of 3
            </div>
          </div>
        </div>
        ```
        
- **하나의 column 너비 설정** : 한 열의 너비를 설정하면 그 주변에 있는 열은 자동 크기 조절됩니다
    - `<div class=”col”>`, `<div class=”col-6”>`
    
    
    - html 코드
        
        ```html
        <div class="container">
          <div class="row">
            <div class="col">
              1 of 3
            </div>
            <div class="col-6">
              2 of 3 (wider)
            </div>
            <div class="col">
              3 of 3
            </div>
          </div>
          <div class="row">
            <div class="col">
              1 of 3
            </div>
            <div class="col-5">
              2 of 3 (wider)
            </div>
            <div class="col">
              3 of 3
            </div>
          </div>
        </div>
        ```
        
- **가변 너비 컨텐츠** : `col-{breakpoint}-auto` 클래스를 사용하면 컨텐츠의 자연스러운 너비에 따라 열 크기를 조정합니다
    

### 행열

`.row-cols-*`(예시 : .row-cols-4) 클래스를 사용해 행렬을 만들 수 있습니다. 

.col-* 클래스는 개별 column에 적용되고, 행열 클래스는 부모 .row에 설정됩니다. 

```html
<div class="container text-center">
  <div class="row row-cols-2"> // 컬럼 2개
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
  </div>
</div>
```

<div class="row `row-cols-auto`"> 도 존재하고, 결과는 다음과 같습니다
	
  </div>
</details>

<details>
<summary> 3-4. Columns </summary>
  <div markdown="1">
  ### 열 작동 원리

- 열은 그리드의 **flexbox 아키텍처 기반**입니다
    - 열이 커지거나 줄어드는 방식을 선택할 수 있습니다
- 그리드 레이아웃을 만들 때 **모든 컨텐츠는 열**에 들어갑니다
    - 그리드 계층 구조는 `container → row → column → contents` 입니다
- Bootstrap에는 빠른 반응형 레이아웃을 만들기 위해 `미리 정의된 클래스`가 포함되어 있습니다
    - 각 그리드 계층의 12개의 열에 원하는 레이아웃을 생성할 수 있습니다

### 열 정렬

- 수직 정렬
    - `align-items-*` 를 통해 열의 위치를 지정할 수 있습니다
    - `<div class=”row align-items-start”>`
        
        
    - html 코드
        
        ```html
        <div class="container">
          <div class="row align-items-start">
            <div class="col-3">
              One of three columns
            </div>
          </div>
        ```
        
    - `<div class=”row align-items-center”>`
        
        
    - `<div class=”row align-items-end”>`
        
        
    - 각 열에 위치를 다르게 설정해 정렬할 수도 있습니다
        
    
- 수평 정렬
    - 수평 정렬은 `justify-content-*` 클래스를 이용해 구현할 수 있습니다
    - * 에 들어갈 수 있는 키워드 : **start(default)**, center, **end** `+ around, between, evenly`

### 열 줄바꿈

단일 행에 12개 이상의 열이 있는 경우, 추가 열의 각 그룹은 하나의 단위씩 새 줄로 줄바꿈 됩니다

```html
<div class="container">
  <div class="row">
    <div class="col-9">.col-9</div>
    <div class="col-offset-4 col-4">.col-4<br>Since 9 + 4 = 13 &gt; 12, this 4-column-wide div gets wrapped onto a new line as one contiguous unit.</div>
    <div class="col-6">.col-6<br>Subsequent columns continue along the new line.</div>
  </div>
</div>
```

열 분할/재정렬/오프셋은 잘 모르겠어서 추후 공부 후 업로드 예정
	
  </div>
</details>

<details>
<summary> 3-5. Gutters </summary>
  <div markdown="1">
  gutter는 열 사이의 패딩으로, bootstrap 그리드 시스템에서 컨텐츠의 간격을 맞추고, 정렬하는 데에 사용 됩니다. 

### 거터 작동원리

- 거터는 가로 padding에 의해 생성되는 열 컨텐츠 사이의 간격입니다.
    - 각 열에 padding-right, padding-left를 설정해 음수 margin을 사용해 각 행의 시작과 끝에서 이를 오프셋하여 콘텐츠를 정렬합니다
- 거터의 너비는 `1.5rem(24px)`에서 시작합니다
- 거터는 반응형으로 조정될 수 있습니다
    - breakpoint 별로 거터 클래스를 사용해 가로/세로를 비롯한 모든 거터를 수정할 수 있습니다

### 수평 거터

- `.gx-* 클래스`를 사용해 수평 거터 너비를 제어할 수 있습니다
- .container 또는 .container-fluid 부모는 일치하는 padding 유틸리티를 사용해 원하지 않는 오버플로를 방지하기 위해 더 큰 gutter를 사용하는 경우 조정해야할 수 있습니다 → 대안은 `overflow-hidden 클래스`로 `.row 주위에 래퍼`를 추가하는 것입니다
    
    
    ```html
    <div class = “overflow-hidden”> 
    	<div class=”row”>~
    ```
    
    
    ```html
    <div class="container px-4 text-center">
      <div class="row gx-5"> // 여기에 gutter 5가 적용 되어있습니다
        <div class="col">
         <div class="p-3">Custom column padding</div>
        </div>
        <div class="col">
          <div class="p-3">Custom column padding</div>
        </div>
      </div>
    </div>
    ```
    

### 수직 거터

- `.gy-* 클래스`를 사용해 열이 줄바꿈 될 때 행 내의 세로 거터 너비를 제어하는 데 사용할 수 있습니다.
    - 수평 거터와 마찬가지로 페이지 끝 .row 아래에 약간의 오버플로를 유발할 수 있습니다. 이 경우 `.overflow-hidden 클래스`로 `.row 주위에 래퍼`를 추가합니다.


```html
<div class="container overflow-hidden text-center">
  <div class="row gy-5">
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
    <div class="col-6">
      <div class="p-3">Custom column padding</div>
    </div>
  </div>
</div>
```

### 수평 & 수직 거터

- .`g-* 클래스`를 사용해 거터 너비를 제어할 수 있습니다.
    
    
    ```html
    <div class="container text-center">
      <div class="row g-2">
        <div class="col-6">
          <div class="p-3">Custom column padding</div>
        </div> -> 3번 더 반복
      </div>
    </div>
    ```
    

### 거터 제거

- 사전 정의된 그리드 클래스 열 사이의 거터는 `.g-0`으로 제거할 수 있습니다. 이렇게 하면 .row에서 음수 margin이 제거되고, 모든 직계 자식 열에서 가로 padding이 제거 됩니다
    
    
    ```html
    <div class="row g-0 text-center">
    
    <!--화면이 sm 사이즈일 때는 열 6개 크기, md 사이즈일 때는 열 8개 크기-->
      <div class="col-sm-6 col-md-8">.col-sm-6 .col-md-8</div>
    
    <!--화면이 sm 사이즈일 때는 열 6개 크기, md 사이즈일 때는 열 4개 크기-->
      <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    
    </div>
    ```
	
  </div>
</details>

</br>
</br>

## 4. Contents 

<details>
<summary> 4-1. Reboot </summary>
  <div>
    Reboot는 `단일 파일에 있는 요소별 css 변경 모음`을 의미하고, Bootstrap을 초기에 빌드하는 우아하고 일관되며 간단한 기준선을 제공합니다. 

> 몇몇 요소들의 margin-top이 제거되거나, 기본 폰트가 변경되는 등 **요소들의 기본 설정 값이 변경된 내용**을 설명하고 있습니다.
> 

### 제목

제목크기는 `<h1>-<h6>` 요소로 설정할 수 있으며, 구체적인 특징은 다음과 같습니다.

margin-top : removed

margin-bottom : .5rem(8px)

line-height : tightened 

### 문단

모든 `<p>` 요소는 모두 `margin-top이 제거`되어있고, `margin-bottom은 1rem` 입니다. 

### 링크

링크는 기본 색상과 underline이 적용됩니다. `:hover`일 때 링크는 변경되며, `:visited`일 때는 변경되지 않습니다.

### 목록

모든 목록(`<ul>, <ol>, <dl>`)에는 `margin-top과 margin-bottom: 1rem`이 제거됩니다. 중첩된 목록에는 margin-bottom이 없습니다. 

`<ul>, <ol> 요소`에서 padding-left를 재설정했습니다.

### 인라인 코드

인라인 코드는 `<code> 태그`로 묶고, html 꺽쇠 괄호는 `‘<’`로 작성하는 것이 아닌, `&lt;` 나 `&rt;` 로 표현해서 꺽쇠를 escape 해야합니다.

```html
For example, <code>&lt;section&gt;</code> should be wrapped as inline.

<!--output : For example, <section> should be wrapped as inline-->
```

### 코드 블록

코드가 여러 줄일 때는 `<pre></pre> 태그`를 사용합니다. 

올바른 렌더링을 위해 `꺽쇠 괄호를 이스케이프`를 잊으면 안됩니다.

`<pre>` 요소는 margin-top을 제거하고 margin-bottom에 rem 단위를 사용하도록 재설정 됩니다.
  </div>
</details>

<details>
<summary> 4-2. Typography </summary>
  <div>
   ### 전역 설정

- 각 os 및 기기에 가장 적합한 기본 글꼴 스택을 사용합니다
- 일반적으로 `16px`의 기본 글꼴 크기를 제공하고, 브라우저 기본값은 사용자가 지정 가능합니다
- `<body>`에 적용된 타이포그래피는 `$font-family-base`, `$font-size-base`, `$line-height-base` 속성을 사용합니다
- `$link-color`를 통해 글로벌 링크 색상을 설정합니다
- `$body-bg`를 사용해 `<body>`에 background-color를 설정합니다

### 제목

- `<h1>~<h6>`
    
    `<h1>~<h6>`을 사용해 제목 크기를 지정할 수 있습니다. 
    
    만약 제목의 글꼴 스타일과 일치시키고 싶지만 관련 html 요소를 사용할 수 없는 경우 .h1부터 .h6 클래스도 사용할 수 있습니다. 
    
    ```html
    <p class="h1">h1. Bootstrap heading</p>
    <p class="h2">h2. Bootstrap heading</p>
    <p class="h3">h3. Bootstrap heading</p>
    <p class="h4">h4. Bootstrap heading</p>
    <p class="h5">h5. Bootstrap heading</p>
    <p class="h6">h6. Bootstrap heading</p>
    ```
    

### 사용자 정의 제목

.text-body-secondary를 사용해 작은 보조 제목 텍스트를 만들 수 있습니다

With faded secondary text에 적용

```html
<h3>
  Fancy display heading
  <small class="text-body-secondary">With faded secondary text</small>
</h3>
```

### Display

눈에 띄는 제목이 필요한 경우 `표시 제목`을 사용하는 것이 좋습니다. 이 제목은 좀 더 크고, 약간 더 독선적인 제목 스타일입니다.

```html
<h1 class="display-1">Display 1</h1>
<h1 class="display-2">Display 2</h1>
<h1 class="display-3">Display 3</h1>
<h1 class="display-4">Display 4</h1>
<h1 class="display-5">Display 5</h1>
<h1 class="display-6">Display 6</h1>

<!--display-* 형태로, * 값이 1에서 6으로 갈수록 글자 크기가 줄어듭니다-->
```

### 서두

.lead 클래스를 활용해 단락을 눈에 띄게 만들 수 있습니다

- .lead 적용 (크기가 좀 더 커진 것을 확인할 수 있습니다)

- .lead 미적용
     

### 인라인 텍스트 요소

하이라이트, 글 지우기, 밑줄, 볼드 등 다양하게 텍스트를 스타일링 할 수 있습니다

```html
<p>You can use the mark tag to <mark>highlight</mark> text.</p>

<p><del>This line of text is meant to be treated as deleted text.</del></p>
<p><s>This line of text is meant to be treated as no longer accurate.</s></p>

<p><ins>This line of text is meant to be treated as an addition to the document.</ins></p>
<p><u>This line of text will render as underlined.</u></p>

<p><small>This line of text is meant to be treated as fine print.</small></p>
<p><strong>This line rendered as bold text.</strong></p>
<p><em>This line rendered as italicized text.</em></p>
```

- `<mark>`, .mark : 참조 또는 표기 목적으로 표시, 강조된 텍스트
- `<small>`, .small : 부가적인 댓글과 작은 텍스트
- `<s>`, .text-decoration-line-through : 더이상 관련이 없거나 더이상 정확하지 않은 요소
- `<u>`, .text-decoration-underline : 텍스트가 아닌 주석이 있음을 나타내는 방식, 렌더링 되어야 하는 인라인 텍스트 범위를 나타냄

### 인용문

`<blockquote class=”blockquote”>`를 사용해 문서 내의 다른 소스에서 콘텐츠 블록을 `인용`합니다. 

- 인용 출처
    
    인용에 대한 출처는 `<blockquote>`를 `<figure>`로 감싸고, <figure> 내에 `<figcaption>` 또는 `.blockquote-footer 클래스`를 통해 표현할 수 있습니다.
    
    ```html
    <figure>
    <!--인용문-->
      <blockquote class="blockquote">
        <p>A well-known quote, contained in a blockquote element.</p>
      </blockquote>
    
    <!--인용 출처-->
      <figcaption class="blockquote-footer">
        Someone famous in <cite title="Source Title">Source Title</cite>
      </figcaption>
    
    </figure>
    ```
    
- 인용구 정렬
    
    인용구를 정렬하려면 `<figure>` 태그에 `.text-*` 를 적용합니다. `center`, `end` 등을 설정할 수 있습니다. 
    

### 목록

- 말 줄임표
- `.text-truncate 클래스`를 추가해 말 줄임표를 사용할 수 있습니다.
    
    ```html
    <dl class="row">
    	<dt class="col-sm-3 text-truncate">Truncated term is truncated</dt>
      <dd class="col-sm-9">This can be useful when space is tight. Adds an ellipsis at the end.</dd>
    </dl>
    ```
  </div>
</details>

<details>
<summary> 4-3. Image </summary>
  <div markdown="1">
###이미지

- 반응형 이미지

Bootstrap의 이미지는 `.img-fluid`를 통해 반응형으로 만들어집니다. 그러면 이미지에 `max-width: 100%;`, `height: auto;`가 적용되어 부모 너비와 함께 크기가 조정됩니다.

```html
<!-- .img-fluid 클래스가 적용됨-->
<img src="..." class="img-fluid" alt="..."/>
```

- 이미지 썸네일

`.img-thumbmail`을 사용해 이미지에 `둥근 1px 테두리 모양`을 제공할 수 있습니다

```html
<img src="..." class="img-thumbnail" alt="..."/>
```

- 이미지 정렬
    
    ```html
    <img src="..." class="rounded float-start" alt="...">
    <img src="..." class="rounded float-end" alt="...">
    ```
    

### 사진

<picture> 요소를 사용하여 특정 <img>에 대해 여러 <source> 요소를 지정하는 경우, `.img-* 클래스`를 <picture> 태그가 아닌 `<img> 태그`에 추가해야 합니다.

```html
<picture>
  <source srcset="..." type="image/svg+xml">
  <img src="..." class="img-fluid img-thumbnail" alt="...">
</picture>
```
  </div>
</details>

</br>
</br>

<h3>5. Forms</h3>

<details>
  <summary> 5-0. overview </summary>
  <div>
      `TODO`

form-`control`, `label`이 무엇인지 공부하기

- form-control
    - input, select, textarea 등의 태그에서 스타일을 줄 수 있는 클래스
- form-label
    - label은 form 내부에서 해당 form의 조작을 담당하는 `태그의 이름표 역할`
     - 

```html
<!--<label>의 for에 <input> id를 추가하면 됨-->
<form>
<label for="타겟id">타겟에대한 정보</label>
<input id="타겟id" type="text">
</form>
```

- label 태그를 사용하는 `이유`
    - self-closing 태그의 용도를 분명하게 보여줌 (input은 셀프 클로징 태그로 내부 텍스트가 없어서 용도를 표현하는 데 한계가 있음)
    - label을 누르는 것만으로도 브라우저를 해당 form 조작에 집중시킬 수 있음
    - id-for 연결

- form email 만들기

```html
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>
  <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

- form 비활성화 하기
```html
<form>
    <fieldset disabled>
      <legend>DIsabled fieldset example</legend>
      <div class="mb-3">
        <label for="disableTextInput" class="form-label">Disabled input</label>
        <input class="form-control" id="disabledInput" type="text" placeholder="Disabled input" disabled>
      </div>
      <div class="mb-3">
        <label for="disabledSelect" class="form-label">Disabled select menu</label>
        <select id="disabledSelect" class="form-select">
          <option>this is disabled select</option>
        </select>
      </div>
      <div class="mb-3 form-check">
        <input class="form-check-input" id="disabledFieldsetCheck" type="checkbox" disabled>
        <label class="form-check-label" for="disabledFieldsetCheck">Can't check this</label>
      </div>
      <button type="submit" class="btn btn-success">Submit</button>
    </fieldset>
</form>
```
  </div>
</details>

<details>
  <summary> 5-1. form-control</summary>
  <div>
  폼 컨트롤은 `텍스트 형식`의 `폼 컨트롤러(<input>, <textarea>)`에 사용자 정의 스타일, 크기 조정, 포커스 상태 등의 업그레이드를 실시할 수 있습니다.

type=”check”, “radio”, “number”,
`TODO`

- input → number 일 때 숫자만 입력할 수 있게 하는 태그 있음
    
    input 박스에 숫자만 입력할 수 있게 설정하는 3가지 방법이 있습니다. 
    
    아래 내용은 해당 링크를 참고했습니다.
    
    1. `type=”number”` → 특정 브라우저 버전에서만 적용가능
        
        ```html
        <input type="number"> 
        ```
        
    2. `oninput` 이벤트, 정규식, replace() 함수 활용하기
        
        ‘`oninput’ 이벤트`는 input form의 값이 바뀌면 발생합니다. `oninput` 이벤트가 발생했을 때, `숫자만 입력할 수 있는 정규식`을 적용해 숫자가 아닌 다른 값이 입력되면 `replace()` 함수를 이용해 값을 대체하도록 했습니다. 
        
        ```html
        <input type="text" 
            oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" />
        ```
        
    3. `pattern = pattern="[0-9]+"` 활용하기 → 모든 브라우저 버전에 적용가능 (효율적)
        
        input에 `pattern 속성`을 지정하고, 입력한 값을 검증할 정규식을 입력했습니다. 위 pattern 속성에 지정된 정규식은 숫자만 입력받도록 하고 있습니다. 만약, 숫자가 아닌 다른 문자가 입력된다면, `‘submit’ 버튼 클릭 시 메시지`를 표시합니다.
        
        ```html
        <form>
          <input type="text" pattern="[0-9]+">
          <input type='submit'>
        </form>
        ```
        
- value, placeholder 의 차이 찾아보기
    
    
    ### 공통점
    
    input 태그에 value와 placeholder를 적용하면 input 박스 안에 `미리 원하는 문구`를 적어 놓을 수 있습니다. 
    
    ### 차이점
    
    - value : 실질적인 값
        
        input 태그의 초기값을 사용되고, 이를 바꾸고 싶다면 사용자가 직접 지우고 입력해야 합니다. 
        
        또한 form 태그를 활용해 `서버에 정보를 전송`할 수 있습니다. 만약 input 태그의 내용을 변경하지 않고, form 태그를 활성화 시키면, 초기의 value 값이 그대로 서버로 전송됩니다. 
        
    - placeholder : 눈에 보이지만 실질적이지 않은 값
        
        사용자가 글자를 입력할 때, 자동으로 미리 입력된 문구가 사라지고, placeholder 값은 서버로 전송되지 않습니다. 
        
    
    code
    
    ```html
    <body>
        <form action="서버의 주소~~"> 
            <input type="text" value="글자를 입력하세요">  // value를 적용했습니다. <br>  // 서버에 전송 되는 정보
            <input type="text" placeholder="글자를 입력하세요."> // placeholder를 적용했습니다. 여기 값은 서버로 못 감
        </form>
    </body>
    ```
    

### Sizing

`.form-control-*{lg, sm} 클래스`를 이용해 input의 크기를 조절할 수 있습니다.
```html
<input class="form-control form-control-lg" type="text" placeholder=".form-control-lg" aria-label=".form-control-lg example">
<input class="form-control" type="text" placeholder="Default input" aria-label="default input example">
<input class="form-control form-control-sm" type="text" placeholder=".form-control-sm" aria-label=".form-control-sm example">
```

### Form text

form text는 input 칸 아래에 넣을 수 있는 텍스트로, `.form-text 클래스`를 이용해 설정할 수 있습니다.
사진에서 Password 칸 아래 “Your password~”가 `form text` 입니다.

```html
<label for="inputPassword5" class="form-label">Password</label>
<input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
<div id="passwordHelpBlock" class="form-text">
  Your password must be 8-20 characters long, contain letters and numbers, and must not contain spaces, special characters, or emoji.
</div>
```

### Disabled

disabled는 포커스가 안되게하고, readonly는 수정만 안되게 함

`<inpupt> 요소`에 `disabled 불리언 속성`을 추가하면 비활성화할 수 있습니다. 

`disabled`만 하면 글씨까지 회색으로 변하지만, `disabled readonly`로 설정하면 글씨는 또렷하게 검정색으로 보입니다.

```html
<input class="form-control" type="text" placeholder="Disabled input" aria-label="Disabled input example" disabled>
<input class="form-control" type="text" value="Disabled readonly input" aria-label="Disabled input example" disabled readonly>
```

### Readonly

`readonly 불리언 속성`을 이용하면 input value의 수정을 예방할 수 있습니다. 

readonly input은 disabled와는 다르게 `focus`나 `selected`가 될 수 있습니다.
- readonly plain text
    
    `.form-control-plaintext 클래스`를 적용하면 테두리 없는 readonly를 구현할 수 있습니다. (사진에서 `Email`의 `email@expale.com`에 plaintext가 적용됨을 확인할 수 있습니다)

```html
<div class="mb-3 row">
    <label for="staticEmail" class="col-sm-2 col-form-label">Email</label>
    <div class="col-sm-10">
      <input type="text" readonly class="form-control-plaintext" id="staticEmail" value="email@example.com">
    </div>
  </div>

  <div class="mb-3 row">
    <label for="inputPassword" class="col-sm-2 col-form-label">Password</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword">
    </div>
  </div>
```


### File input

`.form-control 클래스`의 `type=”file”`을 설정해 파일을 불러오는 것도 구현할 수 있습니다.

```html
<div class="mb-3">
  <label for="formFile" class="form-label">Default file input example</label>
  <input class="form-control" type="file" id="formFile">
</div>

<div class="mb-3">
  <label for="formFileMultiple" class="form-label">Multiple files input example</label>
  <input class="form-control" type="file" id="formFileMultiple" multiple>
</div>

<div class="mb-3">
  <label for="formFileDisabled" class="form-label">Disabled file input example</label>
  <input class="form-control" type="file" id="formFileDisabled" disabled>
</div>

<div class="mb-3">
  <label for="formFileSm" class="form-label">Small file input example</label>
  <input class="form-control form-control-sm" id="formFileSm" type="file">
</div>

<div>
  <label for="formFileLg" class="form-label">Large file input example</label>
  <input class="form-control form-control-lg" id="formFileLg" type="file">
</div>
```

### Datalists

Datalist는 `<options>` 그룹을 생성해 `<input>`에 있는 옵션으로 접근할 수 있게 해줍니다. 

이는 `<select>` 요소와 비슷하지만, 스타일링의 제약과 차이가 존재합니다.

```html
<label for="exampleDataList" class="form-label">Datalist example</label>
<input class="form-control" list="datalistOptions" id="exampleDataList" placeholder="Type to search...">
<datalist id="datalistOptions">
  <option value="San Francisco">
  <option value="New York">
  <option value="Seattle">
  <option value="Los Angeles">
  <option value="Chicago">
</datalist>
```
  </div>
</details>


<details>
  <summary> 5-2. select </summary>
  <div>
  사용자 정의 `css`로 `셀렉트` 요소를 변경할 수 있습니다. 

### 기본값 & 크기 조절

`.form-select 클래스`를 사용해 사용자 정의의 `<select>`를 사용할 수 있습니다. 

이 스타일은 브라우저 제한으로 `<select>`의 처음 외형만 변경할 수 있고, 그 안에 있는 `<option> 들의 스타일 변경은 불가능`합니다.
크기 조절은 `.form-select-*(sm, lg) 클래스`를 사용하면 됩니다.

```html
<h3>1. Default</h3>
    <select class="form-select form-select-lg mb-3" aria-label="Default select example">
        <option selected>Open this select menu</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
    </select>

    <select class="form-select form-select-sm" aria-label="Default select example">
        <option selected>Open this select menu</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
    </select>
```

### multiple

보이는 option 수 (행) 지정할 수 있음
```html
<select class="form-select" multiple aria-label="Multiple select example">
	<option selected>Open this select menu</option>
	<option value="1">One</option>
	<option value="2">Two</option>
	<option value="3">Three</option>
</select>
```

### Disable 하기

```html
<select class="form-select form-select-sm" aria-label="Default select example" disabled>
	<option selected>Open this select menu</option>
	<option value="1">One</option>
	<option value="2">Two</option>
	<option value="3">Three</option>
</select>
```
  </div>
</details>


<details>
  <summary> 5-3. checkbox & radio-box</summary>
  <div>
`TODO`

- 체크박스 인라인 여러개 해보기
    

### 접근

브라우저의 기본 체크 박스/라디오 버튼은 .form-check의 도움을 받아 대체할 수 있습니다. 

기본적으로 체크 박스나 라디오 버튼은 `.form-check`를 이용해 수직으로 적절한 간격으로 쌓을 수 있습니다. 


```html
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
  <label class="form-check-label" for="flexCheckDefault">
    Default checkbox
  </label>
</div>

<!--처음부터 체크된 상태로 설정하기(checked)-->
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="flexCheckChecked" checked>
  <label class="form-check-label" for="flexCheckChecked">
    Checked checkbox
  </label>
</div>
```

### 비활성화 - 체크박스

`disabled 속성`을 추가하면 `<label>과 함께 관련된 입력 폼`이 흐릿한 비활성화 상태로 표시됩니다. 


```html
<!--unchecked disabled-->
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="flexCheckDisabled" disabled>
  <label class="form-check-label" for="flexCheckDisabled">
    Disabled checkbox
  </label>
</div>

<!--checked diabled-->
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="flexCheckCheckedDisabled" checked disabled>
  <label class="form-check-label" for="flexCheckCheckedDisabled">
    Disabled checked checkbox
  </label>
</div>
```

### 라디오 버튼

기본적으로 체크 박스나 라디오 버튼은 `.form-check`를 이용해 수직으로 적절한 간격으로 쌓을 수 있습니다. 

```html
<div class="form-check">
  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1">
  <label class="form-check-label" for="flexRadioDefault1">
    Default radio
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault2" checked>
  <label class="form-check-label" for="flexRadioDefault2">
    Default checked radio
  </label>
</div>
```

### 비활성화 - 라디오 버튼

```html
<div class="form-check">
  <input class="form-check-input" type="radio" name="flexRadioDisabled" id="flexRadioDisabled" disabled>
  <label class="form-check-label" for="flexRadioDisabled">
    Disabled radio
  </label>
</div>

<div class="form-check">
  <input class="form-check-input" type="radio" name="flexRadioDisabled" id="flexRadioCheckedDisabled" checked disabled>
  <label class="form-check-label" for="flexRadioCheckedDisabled">
    Disabled checked radio
  </label>
</div>
```

### 인라인

`.form-check`에 `.form-check-inline 클래스`를 추가해 체크 박스나 라디오 버튼을 같은 수평 방향에 놓아 그룹화할 수 있습니다. 

`<div class=”form-check form-check-inline”>`


```html
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox1" value="option1">
  <label class="form-check-label" for="inlineCheckbox1">1</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox2" value="option2">
  <label class="form-check-label" for="inlineCheckbox2">2</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox3" value="option3" disabled>
  <label class="form-check-label" for="inlineCheckbox3">3 (disabled)</label>
</div>
```

- 라디오 버튼 인라인
    
    ```html
    <div class="form-check form-check-inline">
      <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="option1">
      <label class="form-check-label" for="inlineRadio1">1</label>
    </div>
    <div class="form-check form-check-inline">
      <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="option2">
      <label class="form-check-label" for="inlineRadio2">2</label>
    </div>
    <div class="form-check form-check-inline">
      <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio3" value="option3" disabled>
      <label class="form-check-label" for="inlineRadio3">3 (disabled)</label>
    </div>
    ```
    

### 버튼 토글

체크 박스나 라디오 버튼을 버튼처럼 만들고 싶다면 <label> 요소에 .form-check-label이 아닌 .btn 스타일을 사용하면 됩니다. 이러한 토글 버튼은 다시 button group으로 그룹화할 수 있습니다. 

→ 라벨을 체크박스 형식으로 만듦


```html
<input type="checkbox" class="btn-check" id="btn-check" autocomplete="off">
<label class="btn btn-primary" for="btn-check">Single toggle</label>

<input type="checkbox" class="btn-check" id="btn-check-2" checked autocomplete="off">
<label class="btn btn-primary" for="btn-check-2">Checked</label>

<input type="checkbox" class="btn-check" id="btn-check-3" autocomplete="off" disabled>
<label class="btn btn-primary" for="btn-check-3">Disabled</label>
```

### .btn 테두리 스타일

다양한 종류의 .btn이 지원되고 있습니다. 

type은 checkbox 나 radio 이더라도 `.btn-check`로 설정하면 `버튼처럼` 표현할 수 있습니다. 


```html
<input type="checkbox" class="btn-check" id="btn-check-outlined" autocomplete="off">
<label class="btn btn-outline-primary" for="btn-check-outlined">Single toggle</label><br>

<input type="checkbox" class="btn-check" id="btn-check-2-outlined" checked autocomplete="off">
<label class="btn btn-outline-secondary" for="btn-check-2-outlined">Checked</label><br>

<input type="radio" class="btn-check" name="options-outlined" id="success-outlined" autocomplete="off" checked>
<label class="btn btn-outline-success" for="success-outlined">Checked success radio</label>

<input type="radio" class="btn-check" name="options-outlined" id="danger-outlined" autocomplete="off">
<label class="btn btn-outline-danger" for="danger-outlined">Danger radio</label>
```
  </div>
</details>

<details>
  <summary> 5-4. range </summary>
  <div>
    사용자 범위 컨트롤을 사용해 `크로스 브라우저`에서 `일관되게 표시 및 맞춤 제작`이 가능합니다.

가격 범위 지정할 때 주로 사용합니다. `(ex. airbnb)` 잘 쓰이지는 않습니다. 

### 개요

<input `type=”range”`>에 `.form-range`를 사용해 범위 입력을 사용할 수 있습니다. track(배경)과 thumb(값)은 어느 브라우저에서도 동일하게 표시되도록 스타일링 되어있습니다. 

```html
<label for="customRange1" class="form-label">Example range</label>
<input type="range" class="form-range" id="customRange1">
```

### 비활성화

disabled 블리언 속성을 추가하면 범위 입력이 `비활성화` 되어 표시되고, `포인터 이벤트가 삭제`되며, `포커싱` 되지 않습니다.

### 최소와 최대

범위 입력에는 `min`, `max`를 사용해 범위를 지정할 수 있습니다. 기본값은 각각 `0`, `100` 입니다.

```html
<label for="customRange2" class="form-label">Example range</label>
<input type="range" class="form-range" min="0" max="5" id="customRange2">
```

### 단계

기본적인 범위 입력은 정수값으로 눌러집니다. 이를 변경하려면 step 값을 지정해야합니다. 

```html
<label for="customRange3" class="form-label">Example range</label>
<input type="range" class="form-range" min="0" max="5" step="0.5" id="customRange3">
```
  </div>
</details>


<details>
  <summary> 5-5. input groups </summary>
  <div>
    텍스트 입력, 사용자 정의 select, 사용자 파일 선택 등의 `폼의 좌우`에 `텍스트`, `버튼`, `버튼 그룹`을 추가해 폼 컨트롤을 간단하게 확장할 수 있습니다. 

### 기본 예시

추가 기능(add-on)이나 버튼을 input의 한쪽 또는 양쪽에 배치할 수 있습니다. 

<label>은 입력 그룹 밖에 작성해야 합니다. 

`<span class=”input-group-text” id =”basic-addon1”>~</span>`

- 왼쪽에 `@` 붙이고 오른쪽에 username 작성하기
    
    ```html
    <div class="input-group mb-3">
      <span class="input-group-text" id="basic-addon1">@</span>
      <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1">
    </div>
    ```
    

- 오른쪽에 email 도메인(@example.com) 붙이기
    
    ```html
    <div class="input-group mb-3">
      <input type="text" class="form-control" placeholder="Recipient's username" aria-label="Recipient's username" aria-describedby="basic-addon2">
      <span class="input-group-text" id="basic-addon2">@example.com</span>
    </div>
    ```
    

- 왼쪽에 기본 url(https://example.com/users/) 자동으로 붙이기
    
    ```html
    <div class="mb-3">
      <label for="basic-url" class="form-label">Your vanity URL</label>
      <div class="input-group">
        <span class="input-group-text" id="basic-addon3">https://example.com/users/</span>
        <input type="text" class="form-control" id="basic-url" aria-describedby="basic-addon3 basic-addon4">
      </div>
      <div class="form-text" id="basic-addon4">Example help text goes outside the input group.</div>
    </div>
    ```
    

- 왼쪽에 $ 붙이기
    
    ```html
    <div class="input-group mb-3">
      <span class="input-group-text">$</span>
      <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">
      <span class="input-group-text">.00</span>
    </div>
    ```
    

### 크기 조절

상대적으로 크기를 조절해 주는 클래스(`input-group-*`)를 .input-group이 있는 곳에 추가하면 그 안의 콘텐츠가 자동으로 재조정됩니다. 각 요소에 폼 컨트롤 크기 조정 클래스를 추가할 필요가 없습니다.

주의 : 각각의 입력 그룹 요소의 크기 변경은 지원하지 않습니다. 

```html
<div class="input-group input-group-lg, sm mb-3">
  <span class="input-group-text" id="inputGroup-sizing-*">Small</span>
  <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-*">
</div>
```

### 체크박스와 라디오버튼

input-group의 추가 기능 자리에 텍스트 대신 체크 박스나 라디오 버튼 같은 옵션을 배치할 수 있습니다. 

```html
<!--왼쪽에 체크박스 추가-->
<div class="input-group mb-3">
  <div class="input-group-text">
    <input class="form-check-input mt-0" type="checkbox" value="" aria-label="Checkbox for following text input">
  </div>
  <input type="text" class="form-control" aria-label="Text input with checkbox">
</div>

<!--왼쪽에 라디오버튼 추가-->
<div class="input-group">
  <div class="input-group-text">
    <input class="form-check-input mt-0" type="radio" value="" aria-label="Radio button for following text input">
  </div>
  <input type="text" class="form-control" aria-label="Text input with radio button">
</div>
```

### 버튼 애드온

텍스트 왼쪽 또는 오른쪽에 button을 한 개 이상 추가할 수 있습니다. 

```html
<div class="input-group mb-3">
  <button class="btn btn-outline-secondary" type="button" id="button-addon1">Button</button>
  <input type="text" class="form-control" placeholder="" aria-label="Example text with button addon" aria-describedby="button-addon1">
</div>
```

### 드롭다운이 있는 버튼

```html
<div class="input-group mb-3">
  <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
  <input type="text" class="form-control" aria-label="Text input with dropdown button">
</div>
```

### 사용자 지정 폼

input-group에는 사용자 정의 select 및 사용자 정의 파일 선택 지원이 포함되어잇습니다. 브라우저의 기본 버전에서는 이러한 기능은 지원되지 않습니다. 

```html
<div class="input-group mb-3">
  <label class="input-group-text" for="inputGroupSelect01">Options</label>
  <select class="form-select" id="inputGroupSelect01">
    <option selected>Choose...</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
</div>
```

### 사용자 지정 파일 선택

```html
<div class="input-group mb-3">
  <label class="input-group-text" for="inputGroupFile01">Upload</label>
  <input type="file" class="form-control" id="inputGroupFile01">
</div>
```
  </div>
</details>

<details>
  <summary> 5-6. floating labels</summary>
  <div>
입력 필드 위로 떠오르는 예쁘고 간단한 폼 라벨을 작성할 수 있습니다. 이는 input 안에서 떠오르는 문자 (아래에서 Email address)를 의미합니다. 

`<input class=”form-control”>과 <label> 요소`를 함께 `.form-floating`으로 감싸면, Bootstrap의 텍스트 형식의 form field에서 floating label 사용이 가능합니다.


```html
<div class="form-floating mb-3">
  <input type="email" class="form-control" id="floatingInput" placeholder="name@example.com">
  <label for="floatingInput">Email address</label>
</div>

<div class="form-floating">
  <input type="password" class="form-control" id="floatingPassword" placeholder="Password">
  <label for="floatingPassword">Password</label>
</div>
```

### Select

`.form-control` 이외에서의 floating label은 `.form-select` 에서만 사용가능합니다. 이들은 똑같이 동작하지만, <input>과 다르게 <label>이 항상 플로팅 된 상태로 표시됩니다. 

.form-floating → label이 input 안에 포함되기 해주는 클래스

```html
<div class="form-floating">
  <select class="form-select" id="floatingSelect" aria-label="Floating label select example">
    <option selected>Open this select menu</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
  <label for="floatingSelect">Works with selects</label>
</div>
```

### Disabled

`disabled 불리언 속성`을 input에 추가하면 form-floating을 비활성화 할 수 있습니다. 

```html
<div class="form-floating mb-3">
  <input type="email" class="form-control" id="floatingInputDisabled" placeholder="name@example.com" disabled>
  <label for="floatingInputDisabled">Email address</label>
</div>
```

### Input groups

floating label은 또한 .input-group에서도 적용가능합니다. 

```html
<div class="input-group mb-3">
  <span class="input-group-text">@</span>
  <div class="form-floating">
    <input type="text" class="form-control" id="floatingInputGroup1" placeholder="Username">
    <label for="floatingInputGroup1">Username</label>
  </div>
</div>
```

**feedback - 구조**

.input-group과 .form-floating을 유효성 검사를 위해 사용한다면, -feedback은 `.form-floating 외부`에 있고, `.input-group 내부` 에 있어야 합니다. 이는 feedback이 Javascript를 이용해 보여지는 것을 의미합니다. 

```html
<div class="input-group has-validation">
  <span class="input-group-text">@</span>
  <div class="form-floating is-invalid">
    <input type="text" class="form-control is-invalid" id="floatingInputGroup2" placeholder="Username" required>
    <label for="floatingInputGroup2">Username</label>
  </div>
  <div class="invalid-feedback">
    Please choose a username.
  </div>
</div>
```

### 레이아웃

Bootstrap 그리드 시스템을 사용할 경우, 폼 요소는 반드시 `컬럼 클래스 내`에 배치되어야 합니다.

```html
<div class="row g-2">

  <div class="col-md">
    <div class="form-floating">
      <input type="email" class="form-control" id="floatingInputGrid" placeholder="name@example.com" value="mdo@example.com">
      <label for="floatingInputGrid">Email address</label>
    </div>
  </div>

  <div class="col-md">
    <div class="form-floating">
      <select class="form-select" id="floatingSelectGrid">
        <option selected>Open this select menu</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
      </select>
      <label for="floatingSelectGrid">Works with selects</label>
    </div>
  </div>

</div>
```
  </div>
</details>

<details>
  <summary> 5-7. layout</summary>
  <div>
  form에 구조를 갖게 하는 폼 레이아웃 옵션을 준비하고 있습니다. 

### Form

form field의 모든 그룹은 <form> 요소 안에 존재해야 합니다. 

bootstsrap은 거의 모든 폼 컨트롤에 `display: block`과 `width: 100%`를 적용해 기본적으로 수직으로 쌓고 있습니다. 추가 클래스를 사용해 폼 별로 이 레이아웃을 바꿀 수 있습니다.

### Form grid

grid 클래스를 사용해 여러 개의 컬럼, 다양한 너비, 추가 배치 옵션이 필요한 form layout 표현이 가능합니다. 이를 위해선 Sass 변수 `$enable-grid-classes`가 활성화되어 있어야합니다. (기본이 활성화된 상태)


```html
<div class="row">
  <div class="col">
    <input type="text" class="form-control" placeholder="First name" aria-label="First name">
  </div>
  <div class="col">
    <input type="text" class="form-control" placeholder="Last name" aria-label="Last name">
  </div>
</div>
```

### 거터

거터 제어자 클래스를 추가하는 것으로, 인라인이나 블록 방향으로 거터의 너비를 조정할 수 있습니다. 

이또한 Sass 변수 `$enable-grid-classes`가 활성화 되어 있어야 합니다. (기본값이 활성화된 상태)

```html
<div class="row g-3"> <!--거터 클래스가 추가되었음-->
  <div class="col">
    <input type="text" class="form-control" placeholder="First name" aria-label="First name">
  </div>
  <div class="col">
    <input type="text" class="form-control" placeholder="Last name" aria-label="Last name">
  </div>
</div>
```

그리드 시스템을 사용해 보다 복잡한 레이아웃을 만들 수 있습니다.

- 위 페이지를 구현한 code
    
    ```html
    <form class="row g-3">
      <div class="col-md-6">
        <label for="inputEmail4" class="form-label">Email</label>
        <input type="email" class="form-control" id="inputEmail4">
      </div>
      <div class="col-md-6">
        <label for="inputPassword4" class="form-label">Password</label>
        <input type="password" class="form-control" id="inputPassword4">
      </div>
      <div class="col-12">
        <label for="inputAddress" class="form-label">Address</label>
        <input type="text" class="form-control" id="inputAddress" placeholder="1234 Main St">
      </div>
      <div class="col-12">
        <label for="inputAddress2" class="form-label">Address 2</label>
        <input type="text" class="form-control" id="inputAddress2" placeholder="Apartment, studio, or floor">
      </div>
      <div class="col-md-6">
        <label for="inputCity" class="form-label">City</label>
        <input type="text" class="form-control" id="inputCity">
      </div>
      <div class="col-md-4">
        <label for="inputState" class="form-label">State</label>
        <select id="inputState" class="form-select">
          <option selected>Choose...</option>
          <option>...</option>
        </select>
      </div>
      <div class="col-md-2">
        <label for="inputZip" class="form-label">Zip</label>
        <input type="text" class="form-control" id="inputZip">
      </div>
      <div class="col-12">
        <div class="form-check">
          <input class="form-check-input" type="checkbox" id="gridCheck">
          <label class="form-check-label" for="gridCheck">
            Check me out
          </label>
        </div>
      </div>
      <div class="col-12">
        <button type="submit" class="btn btn-primary">Sign in</button>
      </div>
    </form>
    ```
    

### 수평 폼

form group에 `.row 클래스`를 추가하고, `.col-*-* 클래스`를 사용해 label이나 control의 폭을 지정할 수 있습니다. 이때 `<label>`에는 반드시 `.col-form-label`을 추가해 form control과 함께 수직 방향의 중앙에 배치하도록 합니다.

```html
<form>
  <div class="row mb-3">
    <label for="inputEmail3" class="col-sm-2 col-form-label">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control" id="inputEmail3">
    </div>
  </div>
  <div class="row mb-3">
    <label for="inputPassword3" class="col-sm-2 col-form-label">Password</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword3">
    </div>
  </div>
</form>
```

### 열 크기 조절

그리드 시스템에는 `.row` 안에 `여러 개의 .col`을 몇 개라도 배치할 수 있습니다. 이 열들은 이용 가능한 너비를 균등하게 분할합니다. 

아래 코드의 `.col-sm-7` 와 같은 특정 컬럼 클래스를 사용해 컬럼 서브셋을 선택해 공간을 늘리거나 줄일 수 있습니다. 또한 나머지 .col들을 균등 분할 할 수도 있습니다. 

```html
<div class="row g-3"> <!--row에서 위 아래 거터 3을 설정-->
  <div class="col-sm-7">
    <input type="text" class="form-control" placeholder="City" aria-label="City">
  </div>
  <div class="col-sm">
    <input type="text" class="form-control" placeholder="State" aria-label="State">
  </div>
  <div class="col-sm">
    <input type="text" class="form-control" placeholder="Zip" aria-label="Zip">
  </div>
</div>
```

자동 크기 조절, 인라인 폼은 나중에,,
	  
  </div>
</details>

<br>
<br>


<h3> 6. Component </h3>
<details>
  <summary> 6-1. Accordion </summary>
  <div>
    Collapse JavaScript 플러그인과 조합해 수직으로 접는 아코디언을 만들 수 있습니다.

`TODO`(항상 열기와 기본 비교)

1. 두 accordion 에서 accordion-header의 `data-bs-target`, `aria-controls`의 값이 다름
2. accordion-body를 감싸는 div가 기본 열기는 `collapseOne`, 항상 열기는 `panelStayOpen-collapseOne`
3. 항상 열기에서는 `data-bs-parrent=”~”`가 생략되어 있습니다. 

→ 직접 테스트해 본 결과 `3번`의 문장이 있으면 한번에 하나씩 열리고, 없으면 아코디언을 항상 열어놓을 수 있습니다. 

### 작동 원리

`.accordion 클래스`에 `.accordion-item 클래스`로 아코디언을 구현할 수 있습니다. 

```html
<div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
        Accordion Item #1
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse show" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        <strong>This is the first item's accordion body.</strong> It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.
      </div>
    </div>
  </div>
```

아래 코드처럼 작성해야지 텍스트가 펴졌다가 접혔다가 할 수 있게 할 수 있습니다. 

```html
<button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
```

### 채우기

`.accordion-flush`를 추가해 몇 개의 둥근 모서리를 삭제할 수 있고, 아코디언을 부모 컨테이너와 함께 edge-to-edge로 렌더링 합니다. 

```html
<div class="accordion accordion-flush" id="accordionFlushExample">
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseOne" aria-expanded="false" aria-controls="flush-collapseOne">
        Accordion Item #1
      </button>
    </h2>
    <div id="flush-collapseOne" class="accordion-collapse collapse" data-bs-parent="#accordionFlushExample">
      <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate the <code>.accordion-flush</code> class. This is the first item's accordion body.</div>
    </div>
  </div>
</div>
```

### 항상 열기

다른 항목이 열렸을 때도 이전 아코디언 항목이 열린 상태로 유지되게 하고 싶으면 .accordion-collapse의 `data-bs-parent 속성을 생략`하면 됩니다. 

```html
<div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
        Accordion Item #1
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse show" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        <strong>This is the first item's accordion body.</strong> It is shown by default, 
      </div>
    </div>
  </div>

<div class="accordion" id="accordionPanelsStayOpenExample">
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#panelsStayOpen-collapseOne" aria-expanded="true" aria-controls="panelsStayOpen-collapseOne">
        Accordion Item #1
      </button>
    </h2>
    <div id="panelsStayOpen-collapseOne" class="accordion-collapse collapse show"> // data--bs-parent="#accordionExample" 생략
      <div class="accordion-body">
        <strong>This is the first item's accordion body.</strong> It is shown by default, 
      </div>
    </div>
  </div>
</div>
```
  </div>
</details>

<details>
  <summary> 6-2. Alerts </summary>
  <div>
  일반적인 사용자 액션에 대해 상황에 맞는 피드백 메시지를 제공합니다. 

### 예시

`텍스트 길이에 상관없이` 메시지를 표시할 수 있으며, 옵션으로 닫기 버튼을 제공합니다. 

8가지의 테마 컬러를 사용 가능하고, 인라인으로 경고창을 닫기 위해서는 alerts JavaScript plugin을 사용합니다. 


```html
<div class="alert alert-primary" role="alert">
  A simple primary alert—check it out!
</div>
<div class="alert alert-secondary" role="alert">
  A simple secondary alert—check it out!
</div>
<div class="alert alert-success" role="alert">
  A simple success alert—check it out!
</div>
<div class="alert alert-danger" role="alert">
  A simple danger alert—check it out!
</div>
<div class="alert alert-warning" role="alert">
  A simple warning alert—check it out!
</div>
<div class="alert alert-info" role="alert">
  A simple info alert—check it out!
</div>
<div class="alert alert-light" role="alert">
  A simple light alert—check it out!
</div>
<div class="alert alert-dark" role="alert">
  A simple dark alert—check it out!
</div>
```

### 실시간

버튼을 클릭해 경고를 표시한 다음 내장된 닫기 버튼으로 경고를 해제 할 수 있습니다.

아래 Show live alert 버튼을 누르면 위에 초록색 박스가 생성됩니다. 

```html
<!--여기에 JavaScript를 적용해 라이브 알림 데모를 트리거-->
<div id="liveAlertPlaceholder"></div>
<button type="button" class="btn btn-primary" id="liveAlertBtn">Show live alert</button>
```

### 링크 색상

.alert-link 클래스를 사용하면, 경고창에 어울리는 색의 링크를 사용할 수 있습니다. 

```html
<div class="alert alert-info" role="alert">
  A simple info alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.
</div>
<div class="alert alert-light" role="alert">
  A simple light alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.
</div>
<div class="alert alert-dark" role="alert">
  A simple dark alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.
</div>
```

### 추가 콘텐츠

경고창에는 `제목`, `단락` 및 `구분선` 등과 같은 html 요소를 포함할 수 있습니다.


```html
<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">Well done!</h4>
  <p>Aww yeah, you successfully read this important alert message. This example text is going to run a bit longer so that you can see how spacing within an alert works with this kind of content.</p>
  <hr> <!--구분선-->
  <p class="mb-0">Whenever you need to, be sure to use margin utilities to keep things nice and tidy.</p>
</div>
```

### 아이콘

경고창에 icon을 추가해 만들 수도 있습니다. 

```html
<div class="alert alert-primary d-flex align-items-center" role="alert">

	<!--경고 아이콘-->
  <svg xmlns="http://www.w3.org/2000/svg" class="bi bi-exclamation-triangle-fill flex-shrink-0 me-2" viewBox="0 0 16 16" role="img" aria-label="Warning:">
    <path d="M8.982 1.566a1.13 1.13 0 0 0-1.96 0L.165 13.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767L8.982 1.566zM8 5c.535 0 .954.462.9.995l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 5.995A.905.905 0 0 1 8 5zm.002 6a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/>
  </svg>

  <div>
    An example alert with an icon
  </div>
</div>
```

### 무시

경고창의 JavaScript 플러그인을 사용하면, 경고창을 인라인으로 닫을 수 있습니다. 

close button에 .alert-dismissible의 클래스를 추가하면 경고창의 오른쪽 여백이 추가되고, `닫기 버튼`의 위치가 결정됩니다.

닫기 버튼에 `data-bs-dismiss=”alert”` 속성을 추가합니다. 그러면 JavaScript 기능이 트리거 됩니다. 모든 기기에서 올바르게 동작시키려면 반드시 `<button>` 요소를 사용해야 합니다. 

경고창을 닫을 때 애니메이션을 적용하려면, 반드시 .fade와 .show의 클래스를 추가해야 합니다. (경고창이 해제되면 해당 요소는 페이지 구조에서 완전히 제거됩니다)


```html
<div class="alert alert-warning alert-dismissible fade show" role="alert">
  <strong>Holy guacamole!</strong> You should check in on some of those fields below.
  <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
</div>
```
    
  </div>
</details>


<details>
  <summary> 6-3. Badges </summary>
  <div>
    부모 요소의 크기에 일치하도록 상대적인 글꼴 크기 `em`을 사용하고 있습니다. `version 5` 이후로 배지에는 더 이상 링크에 대한 `포커스나 호버 스타일은 없습니다.`

```html
<h1>Example heading <span class="badge bg-secondary">New</span></h1>
<h2>Example heading <span class="badge bg-secondary">New</span></h2>
<h3>Example heading <span class="badge bg-secondary">New</span></h3>
<h4>Example heading <span class="badge bg-secondary">New</span></h4>
<h5>Example heading <span class="badge bg-secondary">New</span></h5>
<h6>Example heading <span class="badge bg-secondary">New</span></h6>
```

### 버튼

배지는 카운터(숫자)를 제공하기 위해 링크나 버튼의 일부로 사용될 수 있습니다. 

Notifications 오른쪽에 <span>으로 badge를 적용하면 됩니다. 

```html
<button type="button" class="btn btn-primary">
  Notifications <span class="badge text-bg-secondary">4</span>
</button>
```

### 위치

카톡, 인스타그램 알림이 왔을 때 처럼 버튼 오른쪽 상단에 배지를 추가할 수 있습니다. 

```html
 <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
    99+
		<span class="visually-hidden">unread messages</span>
</span>
```

```html
<button type="button" class="btn btn-primary position-relative">
  Inbox
  <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
    99+
    <span class="visually-hidden">unread messages</span>
  </span>
</button>
```

아래 코드를 추가해 숫자가 없는 알림을 설정할 수 있습니다. 

```html
<span class="position-absolute top-0 start-100 translate-middle p-2 bg-danger border border-light rounded-circle">
```

```html
<button type="button" class="btn btn-primary position-relative">
  Profile
  <span class="position-absolute top-0 start-100 translate-middle p-2 bg-danger border border-light rounded-circle">
    <span class="visually-hidden">New alerts</span>
  </span>
</button>
```

### 색상

`.text-bg-*`를 이용해 배지의 색상을 지정할 수 있습니다. 

```html
<span class="badge text-bg-primary">Primary</span>
<span class="badge text-bg-secondary">Secondary</span>
<span class="badge text-bg-success">Success</span>
<span class="badge text-bg-danger">Danger</span>
<span class="badge text-bg-warning">Warning</span>
<span class="badge text-bg-info">Info</span>
<span class="badge text-bg-light">Light</span>
<span class="badge text-bg-dark">Dark</span>
```

### 필 배지

`.rounded-pill`을 사용하면 border-radius보다 더 동그란 배지를 만들 수 있습니다. 

```html
<span class="badge rounded-pill text-bg-primary">Primary</span>
<span class="badge rounded-pill text-bg-secondary">Secondary</span>
<span class="badge rounded-pill text-bg-success">Success</span>
<span class="badge rounded-pill text-bg-danger">Danger</span>
<span class="badge rounded-pill text-bg-warning">Warning</span>
<span class="badge rounded-pill text-bg-info">Info</span>
<span class="badge rounded-pill text-bg-light">Light</span>
<span class="badge rounded-pill text-bg-dark">Dark</span>
```   
    
  </div>
</details>

<details>
  <summary> 6-4. Breadcrumb </summary>
  <div>
  CSS로 구분자를 자동으로 추가해 내비게이션 계층 내에서 `현재 페이지의 위치`를 표시합니다. 사이트나 웹 앱에서 유저의 위치를 보여주는 부차적인 내비게이션 시스템을 의미합니다. `페이지 인덱스`

### 예시

`<nav>` 요소 안에 `.breadcrumb 클래스`를 이용해 브레드크럼을 표현할 수 있습니다. 

```html
<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item active" aria-current="page">Home</li>
  </ol>
</nav>

<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item active" aria-current="page">Library</li>
  </ol>
</nav>

<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item"><a href="#">Library</a></li>
    <li class="breadcrumb-item active" aria-current="page">Data</li>
  </ol>
</nav>
```
  </div>
</details>

<details>
  <summary> 6-5. Buttons </summary>
  <div>
    다양한 크기/상태의 버튼 스타일을 사용할 수 있습니다. 

### Base class

버튼은 .btn 클래스를 이용해 구현할 수 있습니다. 색깔을 지정해도 되고, 하지 않아도 됩니다 

`class=”btn”`만 사용하면 테두리가 없는 버튼을 만들 수 있고, `class=”btn-*”`와 같은 형식이면 버튼에 색을 입힐 수 있습니다.

- 색상이 없는 버튼


```html
<button type="button" class="btn">Base class</button>
```

- 색상 버튼

```html
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-light">Light</button>
<button type="button" class="btn btn-dark">Dark</button>

<!--link로도 버튼을 표현할 수 있습니다-->
<button type="button" class="btn btn-link">Link</button>
```

- 버튼 테두리
    
    가벼운 배경색의 버튼도 설정할 수 있습니다. 
    
    
    ```html
    <button type="button" class="btn btn-outline-primary">Primary</button>
    <button type="button" class="btn btn-outline-secondary">Secondary</button>
    <button type="button" class="btn btn-outline-success">Success</button>
    <button type="button" class="btn btn-outline-danger">Danger</button>
    <button type="button" class="btn btn-outline-warning">Warning</button>
    <button type="button" class="btn btn-outline-info">Info</button>
    <button type="button" class="btn btn-outline-light">Light</button>
    <button type="button" class="btn btn-outline-dark">Dark</button>
    ```
    

### 크기

`.btn-*{lg, sm}`을 이용해 버튼 크기를 설정할 수 있습니다. 

```html
<!--lg 크기-->
<button type="button" class="btn btn-primary btn-lg">Large button</button>

<!--sm 크기-->
<button type="button" class="btn btn-primary btn-sm">Small button</button>
```

버튼 크기를 사용자로 설정할 수 있습니다. 

```html
<button type="button" class="btn btn-primary"
        style="--bs-btn-padding-y: .25rem; --bs-btn-padding-x: .5rem; --bs-btn-font-size: .75rem;">
  Custom button
</button>
```

### 비활성화 상태

<button> 요소에 disabled 속성을 추가해 버튼을 비활성화 할 수 있습니다. 버튼이 비활성화 되면 아무것도 적용되지 않고, hover나 활성화된 상태로 눌리는 것을 막습니다. 

```html
<button type="button" class="btn btn-primary" disabled>Primary button</button>
<button type="button" class="btn btn-secondary" disabled>Button</button>
<button type="button" class="btn btn-outline-primary" disabled>Primary button</button>
<button type="button" class="btn btn-outline-secondary" disabled>Button</button>
```

- 참고
    
    `<a> 요소`에서 버튼을 비활성화하는 경우는 `.disabled 클래스`를 추가해야 합니다. 따로 disabled 속성을 지원하지 않기 때문입니다. <a>를 사용하는 비활성화 버튼은 href 속성을 포함하면 안됩니다.  → 코드 추가해 놓기
    

### 버튼 블록

Display와 gap 유틸리티를 조합해, 전체 너비에 걸친 반응형 “블록 버튼”을 만들 수 있습니다. 

```html
<div class="d-grid gap-2">
  <button class="btn btn-primary" type="button">Button</button>
  <button class="btn btn-primary" type="button">Button</button>
</div>
```

여기에 `.gap-2`, `.d-md-block`, `.col-6`, `.max-auto`을 추가해 버튼의 너비나 위치를 조절할 수 있습니다. 

- `.gap-2`, `.d-md-block`
    
    ```html
    <div class="d-grid gap-2 d-md-block">
      <button class="btn btn-primary" type="button">Button</button>
      <button class="btn btn-primary" type="button">Button</button>
    </div>
    ```
    
- `.gap-2`, `.col-6`, `.mx-auto`
    
    ```html
    <div class="d-grid gap-2 col-6 mx-auto">
      <button class="btn btn-primary" type="button">Button</button>
      <button class="btn btn-primary" type="button">Button</button>
    </div>
    ```
    
  </div>
</details>

<details>
  <summary> 6-6. Button group </summary>
  <div>
    여러 개의 버튼을 묶어 `그룹화` 하거나, `세로`로 겹쳐 놓을 수 있습니다. 

### 기본 예시

.btn-group으로 .btn 요소를 포장할 수 있습니다. 

```html
<div class="btn-group" role="group" aria-label="Basic example">
  <button type="button" class="btn btn-primary">Left</button>
  <button type="button" class="btn btn-primary">Middle</button>
  <button type="button" class="btn btn-primary">Right</button>
</div>
toolbar도 적용하기
```

- 현재 위치한 버튼 표시
 
    ```html
    <!-- .active 와 aria-current="page를 추가 -->
    <div class="btn-group">
      <a href="#" class="btn btn-primary active" aria-current="page">Active link</a>
      <a href="#" class="btn btn-primary">Link</a>
      <a href="#" class="btn btn-primary">Link</a>
    </div>
    ```
    

- 테두리 스타일
    
    각 버튼 요소에 `.btn-outline-*`를 적용하면 됩니다.
        
    ```html
    <div class="btn-group" role="group" aria-label="Basic outlined example">
      <button type="button" class="btn btn-outline-primary">Left</button>
      <button type="button" class="btn btn-outline-primary">Middle</button>
      <button type="button" class="btn btn-outline-primary">Right</button>
    </div>
    ```
    

### 체크박스와 라디오버튼 그룹

버튼에 체크박스/라디오 토글 버튼을 조합해 매끄러운 외형의 버튼 그룹을 만들 수 있습니다. 

- 체크박스 + 버튼
    
    여러개의 버튼을 선택할 수 있습니다 
    
    ```html
    <div class="btn-group" role="group" aria-label="Basic checkbox toggle button group">
      <input type="checkbox" class="btn-check" id="btncheck1" autocomplete="off">
      <label class="btn btn-outline-primary" for="btncheck1">Checkbox 1</label>
    
      <input type="checkbox" class="btn-check" id="btncheck2" autocomplete="off">
      <label class="btn btn-outline-primary" for="btncheck2">Checkbox 2</label>
    
      <input type="checkbox" class="btn-check" id="btncheck3" autocomplete="off">
      <label class="btn btn-outline-primary" for="btncheck3">Checkbox 3</label>
    </div>
    ```
    

- 라디오버튼 + 버튼
    
    버튼이 라디오버튼처럼 기본 하나가 선택되어있고, 다른 버튼을 하나씩 선택할 수 있습니다. 
    
    ```html
    
    ```
    

이외에 `버튼 툴바`, `버튼 중첩`, `버튼 수직`으로 버튼을 표현할 수도 있습니다.
    
  </div>
</details>

<details>
  <summary> 6-7. Card </summary>
  <div>

  `TODO`

1. .card-img-`top` 과 .card-img-`bottom`의 차이 알아보기(위치변경은 태그 위치를 변경하면 되는데, 왜 클래스까지 바뀌었는지?)
    - 실습
        
        아래부분이 둥글고, 윗부분은 뾰족한 것을 확인할 수 있습니다. 이로써 .card-img-*에서 *에 들어가는 부분이 둥글게 표현되는 것을 의미하는 것을 알 수 있습니다. 
         
2. 아래 코드에서 rounded-`start` 를 rounded-`end`로 바꿔보기
    - 코드
        
        ```html
        <div class="card mb-3" style="max-width: 540px;">
          <div class="row g-0">
        
            <div class="col-md-4">
              <img src="..." class="img-fluid rounded-end" alt="...">
            </div>
        
            <div class="col-md-8">
              <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
                <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
              </div>
            </div>
        
          </div>
        </div>
        ```
        
    - 실습
     
3. bg-transparent에서 `transparent` 말고 `다른색` 적용해보기
    - 코드
        
        ```html
        <div class="card border-success mb-3 bg-primary" style="max-width: 18rem;">
          <div class="card-header bg-transparent border-success">Header</div>
          <div class="card-body text-success">
            <h5 class="card-title">Success card title</h5>
            <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          </div>
          <div class="card-footer bg-transparent border-success">Footer</div>
        </div>
        ```
        
    - 실습
        
        bg-success를 header와 footer에 적용했습니다. 
        
        transparent도 primary, secondary, success 처럼 색을 의미합니다.         

---

### 기본

카드는 폭이 고정되어 있지 않기 때문에 부모 요소의 폭에 맞춰집니다. 

```html
<div class="card" style="width: 18rem;">

  <img src="..." class="card-img-top" alt="...">

  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>

</div>
```

### 콘텐츠 유형

카드에서는 이미지나 텍스트, 목록, 링크 등의 다양한 콘텐츠를 지원하고 있습니다. 

1. Body
    
    .card-body 클래스로 카드를 빌드할 수 있습니다. 카드 내에 여백이 필요할 때 상요합니다. 
    
   ```html
    <div class="card">
      <div class="card-body">
        This is some text within a card body.
      </div>
    </div>
    ```
    

1. Title, Text, Link
    
    `카드 타이틀`은 <h*> 태그에 `.card-title`을 적용해 표현할 수 있습니다.
    
    `링크`는 <a> 태그에 `.card-link`를 적용하면 욉니다. 
    
    `서브 타이틀`은 <h*> 태그에 `.card-subtitle`을 적용하면 됩니다. 
    
    `Tip` : .card-title과 .card-subtitle을 .card-body 안에 배치하면 카드 제목과 서브 타이틀이 깔끔하게 적용됩니다. 
        
    ```html
    <div class="card" style="width: 18rem;">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <h6 class="card-subtitle mb-2 text-body-secondary">Card subtitle</h6>
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        <a href="#" class="card-link">Card link</a>
        <a href="#" class="card-link">Another link</a>
      </div>
    </div>
    ```
    
2. Image
    
    카드에 이미지를 추가하기 위해선 `.card-img-top 클래스`를 추가해줘야 합니다. `.card-body` 내부에 `.card-text`를 설정하면 카드에 텍스트를 추가할 수 있습니다. 
       
    ```html
    <div class="card" style="width: 18rem;">
    
      <img src="..." class="card-img-top" alt="...">
    
      <div class="card-body">
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      </div>
    
    </div>
    ```
    
3. 목록 그룹
    
    `.list-group-flush`를 이용해 카드 안에 목록을 만들 수 있습니다. 
       
    ```html
    <div class="card" style="width: 18rem;">
      <ul class="list-group list-group-flush">
        <li class="list-group-item">An item</li>
        <li class="list-group-item">A second item</li>
        <li class="list-group-item">A third item</li>
      </ul>
    </div>
    ```
    
4. **키친 싱크**
    
    복수의 콘텐츠 타입을 조합하고, 필요한 카드를 작성하거나 모든 것을 이 안에 넣을 수 있습니다. 
    
    - 이미지, 블록, 텍스트 스타일, 목록 그룹 포함
        
    ```html
    <div class="card" style="width: 18rem;">
    
      <img src="..." class="card-img-top" alt="...">
    
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      </div>
    
      <ul class="list-group list-group-flush">
        <li class="list-group-item">An item</li>
        <li class="list-group-item">A second item</li>
        <li class="list-group-item">A third item</li>
      </ul>
    
      <div class="card-body">
        <a href="#" class="card-link">Card link</a>
        <a href="#" class="card-link">Another link</a>
      </div>
    
    </div>
    ```
    
5. 헤더
    
    `.card-header`
        
    ```html
    <div class="card">
      <div class="card-header">
        Featured
      </div>
      <div class="card-body">
        <h5 class="card-title">Special title treatment</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
    ```
    

### 크기 조절

카드는 별도의 설정을 하지 않은 한 100%의 width를 가로 폭으로 가집니다. 필요하다면 별도의 설정으로 크기를 변경할 수 있습니다. 

- 그리드 마크업 사용하기
    
    Grid를 사용해, 필요에 따라 카드를 행과 열 안에 넣어서 사용합니다. 
     
    ```html
    <div class="row">
      <div class="col-sm-6 mb-3 mb-sm-0">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Special title treatment</h5>
            <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
      </div>
      <div class="col-sm-6">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">Special title treatment</h5>
            <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
          </div>
        </div>
      </div>
    </div>
    ```
    
- 유틸리티 사용하기
    
    크기 조절 유틸리티를 사용해 카드의 가로 폭을 빠르게 설정할 수 있습니다. 
       
    ```html
    <div class="card w-75 mb-3">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Button</a>
      </div>
    </div>
    
    <div class="card w-50">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Button</a>
      </div>
    </div>
    ```
    
- 사용자 지정 css 사용하기
    
    스타일 시트나 인라인 스타일로 가로 폭을 적용할 수 있습니다. 
    
    ```html
    <div class="card" style="width: 18rem;">
    
      <div class="card-body">
        <h5 class="card-title">Special title treatment</h5>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    
    </div>
    ```
    

### 텍스트 정렬

`.text-center`, `.text-end` 클래스 사용으로 카드 안의 텍스트 정렬할 수 있습니다. 

```html
<div class="card mb-3" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card text-center mb-3" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card text-end" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

### 내비게이션

`.nav,` `.nav-tabs`를 이용해 카드의 header 혹은 block에 내비게이션을 적용할 수 있습니다. 

```html
<div class="card text-center">
  <div class="card-header">

    <ul class="nav nav-tabs card-header-tabs">
      <li class="nav-item">
        <a class="nav-link active" aria-current="true" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" aria-disabled="true">Disabled</a>
      </li>
    </ul>

  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

### 이미지

카드에 이미지를 다양한 방식으로 추가할 수 있습니다. 

```html
<div class="card mb-3">

  <img src="..." class="card-img-top" alt="...">

  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
  </div>

</div>
```

```html
<div class="card">

  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
  </div>

  <img src="..." class="card-img-bottom" alt="...">

</div>
```

### 이미지 오버레이

이미지를 카드의 배경으로 한 뒤 카드의 텍스트를 이미지에 덮어씌울 수 있습니다. 

이미지에 따라 추가 스타일/유틸리티가 필요할 수도 아닐 수도 있습니다. 

> `주의` : 콘텐츠가 이미지 높이보다 커지면 일부 콘텐츠는 이미지 외부에 표시될 수 있습니다.

```html
<div class="card text-bg-dark">
  <img src="..." class="card-img" alt="...">
  <div class="card-img-overlay">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small>Last updated 3 mins ago</small></p>
  </div>
</div>
```

### 수평

그리드와 유틸리티 클래스를 조합해 모바일에 친화적이고, 반응형적인 방법으로 카드를 수평 배치할 수 있습니다 `(이미지 - 카드)`

- 거터 삭제(.g-0), 카드 breakpoint md로 배치한 예시

```html
<div class="card mb-3" style="max-width: 540px;">
  <div class="row g-0">

    <div class="col-md-4">
      <img src="..." class="img-fluid rounded-start" alt="...">
    </div>

    <div class="col-md-8">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
        <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
      </div>
    </div>

  </div>
</div>
```

### 카드 스타일

카드에는 다양한 배경/모서리/색 을 지정할 수 있습니다. 

색깔 지정은 `.text-bg-{color}`, `.text-{color}`, `.bg-{color}` 클래스로 할 수 있습니다. 

```html
<!--카드에 회색 입힌 예제-->
<div class="card text-bg-secondary mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h5 class="card-title">Secondary card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
</div>

<!--라인만 있는 회색 카드-->
<div class="card border-secondary mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body text-secondary">
    <h5 class="card-title">Secondary card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
</div>
```

### 믹스인 유틸리티

필요에 따라서 카드의 header나 footer의 라인을 변경하거나 `.bg-transparent`를 사용해 background-color를 삭제 할 수 있습니다. 

```html
<div class="card border-success mb-3" style="max-width: 18rem;">
  <div class="card-header bg-transparent border-success">Header</div>
  <div class="card-body text-success">
    <h5 class="card-title">Success card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
  <div class="card-footer bg-transparent border-success">Footer</div>
</div>
```

### 카드 레이아웃

카드 레이아웃으로 일련의 카드를 배치할 수 있습니다. 다만 현재는 **카드 레이아웃 옵션은 반응형을 지원하고 있지 않습니다.** 

- 카드 그룹
    
    카드 그룹을 사용해 폭과 높이의 열이 같은 하나의 요소로 카드를 렌더링합니다. 
    
    `display: flex;` 를 사용해 `sm` 중단점부터 같은 크기의 상태로 설정됩니다. 
    
    footer가 있는 카드 그룹을 사용하면, 그 내용도 그룹에 맞춰서 자동으로 정렬됩니다.
        
    ```html
    <div class="card-group">
    
      <div class="card">
        <img src="..." class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
        </div>
      </div>
    
      <div class="card">
        <img src="..." class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
          <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
        </div>
      </div>
    
      <div class="card">
        <img src="..." class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
          <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>
        </div>
      </div>
    </div>
    ```
    
- 그리드 카드
    
    bootstrap 그리드 시스템과 `.row-cols` 클래스를 사용해, `행마다 표시하는 그리드 열개수`를 제어할 수 있습니다. 
    
    예를들어 `.row-cols-1`은 한줄로 카드를 배치하고, `.row-cols-md-2`는 하나의 행에  두 개의 열에 맞춰 카드가 정렬됩니다. 
        
    ```html
    <div class="row row-cols-1 row-cols-md-2 g-4">
      <div class="col">
        <div class="card">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          </div>
        </div>
      </div>
    </div>
    ```
    
    같은 높이가 필요한 경우에는 카드에 .h-100 클래스를 추가합니다. 
     
    ```html
    <div class="row row-cols-1 row-cols-md-3 g-4">
      <div class="col">
        <div class="card h-100">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card h-100">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a short card.</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card h-100">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card h-100">
          <img src="..." class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          </div>
        </div>
      </div>
    </div>
    ```
    
  </div>
</details>


<details>
  <summary> 6-8. Carousel</summary>
  <div>
  `TODO`

캐러샐 자동 넘기기 디폴트 지연시간이 몇인지 알아보기, 개발에는 디폴트가 중요함!!!

→ 기본값은 5000으로서, 5초입니다. 링크 참고

---

캐러샐은 css 3d 트랜스폼과 약간의 javascript로 만들어진 `일련의 콘텐츠를 순환시키기 위한 슬라이드쇼`입니다. 

### Basic examples


```html
<div id="carouselExample" class="carousel slide">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>

<!--이전 사진으로 이동하게 해주는 버튼-->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>

<!--다음 사진으로 이동하게 해주는 버튼-->
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
```

- 꼭 지켜야할 것들
    - `.active` 를 슬라이드 중 하나에 무조건 추가해야합니다. 그렇지 않으면 캐러샐이 보이지 않습니다.
    - `.carousel` 클래스에 유일한 `id` 추가하기 (하나의 페이지에 여러개의 캐러셀을 사용하는 경우)
    - 캐러셀 요소의 id에 매치되는 값을 `data-bs-target 속성`에 꼭 추가를 해야합니다.

### 인디케이터

- 코드
    
    ```html
    <div id="carouselExampleIndicators" class="carousel slide">
    
      <div class="carousel-indicators">
        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1" aria-label="Slide 2"></button>
        <button type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2" aria-label="Slide 3"></button>
      </div>
    
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
      </div>
    
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
    ```
    

### 설명문

`.carousel-item` 안의 `.carousel-caption 요소`를 사용해 슬라이드에 설명문(caption)을 쉽게 추가할 수 있습니다. 

또한 `.d-none`, `.d-md-block`을 사용해 작은 뷰포트에서 간단하게 설명문(captioin)을 감추는 것도 가능합니다. .d-md-block만 있으면 안쓰는 거랑 똑같음 → 같이 쓰는게 맞음 반대케이스(다 보이게 해놓고, 특정 크기에서 안 보이게 할 수 있음)

- 코드
    
    ```html
    <div id="carouselExampleCaptions" class="carousel slide">
      <div class="carousel-indicators">
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
        <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
      </div>
    
      <div class="carousel-inner">
    
        <div class="carousel-item active">
          <img src="..." class="d-block w-100" alt="...">
          <div class="carousel-caption d-none d-md-block">
            <h5>First slide label</h5>
            <p>Some representative placeholder content for the first slide.</p>
          </div>
        </div>
    
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
          <div class="carousel-caption d-none d-md-block">
            <h5>Second slide label</h5>
            <p>Some representative placeholder content for the second slide.</p>
          </div>
        </div>
    
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
          <div class="carousel-caption d-none d-md-block">
            <h5>Third slide label</h5>
            <p>Some representative placeholder content for the third slide.</p>
          </div>
        </div>
      </div>
    
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    
    </div>
    ```
    

### 덮어씌우기

캐러셀에 `.carousel-fade`를 추가하면 슬라이드 대신에 fade 트랜지션으로 슬라이드를 애니메이션화 시킬 수 있습니다. (움직이는 장면은 이 링크의 ‘덮어씌우기’를 참고해주시면 됩니다)

- 코드
    
    ```html
    <div id="carouselExampleFade" class="carousel slide carousel-fade">
    
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
      </div>
    
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    
    </div>
    ```
    

### Autoplaying carousels

`.data-bs-ride`를 상위 carousel 클래스에 추가하면 캐러셀이 자동으로 재생될수 있게 할 수 있습니다. 자동 슬라이드를 멈추려면 pause 옵션을 설정한 뒤 마우스로 호버하면 자동으로 멈출 수 있습니다. 

- 코드
    
    ```html
    <div id="carouselExampleAutoplaying" class="carousel slide" data-bs-ride="carousel">
    
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
      </div>
    
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleAutoplaying" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleAutoplaying" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    
    </div>
    ```
    

### .carousel-item 지연시간

자동으로 슬라이드 될 때의 지연시간을 변경하려면 `.carousel-item` 에 `data-bs-interval=””`을 추가하면 됩니다. 

- 코드
    
    ```html
    <div id="carouselExampleInterval" class="carousel slide" data-bs-ride="carousel">
    
      <div class="carousel-inner">
        <div class="carousel-item active" data-bs-interval="10000">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item" data-bs-interval="2000">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
      </div>
    
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleInterval" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleInterval" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    
    </div>
    ```
    

### Autoplaying carousels without controls

위의 캐러셀과 다르게 이전, 다음으로 넘어가는 버튼 없이 자동으로 넘어가기만 하는 캐러셀을 구현할 수 있습니다. 

.`carousel-item` 안에 있는 이미지에 `.d-block` 과 `.w-100` 을 추가하면 됩니다. 

- 코드
    
    ```html
    <div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
    
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
        </div>
      </div>
    
    </div>
    ```
    

### 화살표/캡션/인디케이터 검정색으로 변경

.carousel 클래스에 .carousel-dark를 추가하면 됩니다. 

- 코드
    
    ```html
    <div id="carouselExampleDark" class="carousel carousel-dark slide">
    
      <div class="carousel-indicators">
        <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
        <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="1" aria-label="Slide 2"></button>
        <button type="button" data-bs-target="#carouselExampleDark" data-bs-slide-to="2" aria-label="Slide 3"></button>
      </div>
    
      <div class="carousel-inner">
        <div class="carousel-item active" data-bs-interval="10000">
          <img src="..." class="d-block w-100" alt="...">
          <div class="carousel-caption d-none d-md-block">
            <h5>First slide label</h5>
            <p>Some representative placeholder content for the first slide.</p>
          </div>
        </div>
        <div class="carousel-item" data-bs-interval="2000">
          <img src="..." class="d-block w-100" alt="...">
          <div class="carousel-caption d-none d-md-block">
            <h5>Second slide label</h5>
            <p>Some representative placeholder content for the second slide.</p>
          </div>
        </div>
        <div class="carousel-item">
          <img src="..." class="d-block w-100" alt="...">
          <div class="carousel-caption d-none d-md-block">
            <h5>Third slide label</h5>
            <p>Some representative placeholder content for the third slide.</p>
          </div>
        </div>
      </div>
    
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleDark" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleDark" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    
    </div>
    ```
    
  </div>
</details>

<details>
  <summary> 6-9. Close Button </summary>
  <div>
모달이나 경고창 등의 콘텐츠를 닫을 때 사용합니다. `.btn-close`를 사용해 컴포넌트를 닫는 옵션을 제공합니다.

```html
<!--기본-->
<button type="button" class="btn-close" aria-label="Close"></button>

<!--비활성화-->
<button type="button" class="btn-close" disabled aria-label="Close"></button>
```
  </div>
</details>

<details>
  <summary> 6-10. Collapse</summary>
  <div>
  Collapse는 콘텐츠의 표시와 숨김에 사용됩니다. 요소를 접으면 height가 `기존 값에서 0으로` 애니메이션화 됩니다. 다만 `.collapse 요소`에 `padding`은 사용할 수 없습니다. 

### 기본

왼쪽은 링크로 카드 열기, 오른쪽은 버튼으로 카드를 엽니다. 

둘 다 모두 공통으로 `data-bs-toggle=”collapse” 속성`을 가집니다. 

다른 점은 링크는 `href=”#collapseExample”`로 id가 collapseExample인 collapse를 가리키고, 버튼은 `data-bs-target=”#collapseExample”`로 collapse를 가리킵니다.

```html
<p class="d-inline-flex gap-1">

  <a class="btn btn-primary" data-bs-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample">
    Link with href
  </a>

  <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
    Button with data-bs-target
  </button>

</p>

<!--버튼을 누르면 나오는 카드-->
<div class="collapse" id="collapseExample">
  <div class="card card-body">
    Some placeholder content for the collapse component. This panel is hidden by default but revealed when the user activates the relevant trigger.
  </div>
</div>
```

### 수평 콜랩스

수평 콜랩스는 수직으로 카드가 내려오는 것이 아닌 가로로 카드가 나올 수 있게 해줍니다. 

`.collapse-horizontal 클래스`를 card의 부모로 설정하면 구현할 수 있습니다. 

```html
<p>
  <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseWidthExample" aria-expanded="false" aria-controls="collapseWidthExample">
    Toggle width collapse
  </button>
</p>

<div style="min-height: 120px;">
  <div class="collapse collapse-horizontal" id="collapseWidthExample">
    <div class="card card-body" style="width: 300px;">
      This is some placeholder content for a horizontal collapse. It's hidden by default and shown when triggered.
    </div>
  </div>
</div>
```

### 다중 항목 및 목표

<button>이나 <a>는 data-bs-target 혹은 href을 이용해 카드를 지정할 수 있고, 동시에 여러 개의 카드를 지정할 수도 있습니다. 이는 `data-bs-target = “.multi-collapse”` 와 `aria-controls="collapseId1 collapseId2"` 설정으로 만들 수 있습니다. (아래 코드에서 Toggle both elements 버튼을 참고해주세요)

```html
<p class="d-inline-flex gap-1">
  <a class="btn btn-primary" data-bs-toggle="collapse" href="#multiCollapseExample1" role="button" aria-expanded="false" aria-controls="multiCollapseExample1">Toggle first element</a>
  <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#multiCollapseExample2" aria-expanded="false" aria-controls="multiCollapseExample2">Toggle second element</button>
  <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target=".multi-collapse" aria-expanded="false" aria-controls="multiCollapseExample1 multiCollapseExample2">Toggle both elements</button>
</p>

<!--첫번째 카드-->
<div class="row">
  <div class="col">
    <div class="collapse multi-collapse" id="multiCollapseExample1">
      <div class="card card-body">
        Some placeholder content for the first collapse component of this multi-collapse example. This panel is hidden by default but revealed when the user activates the relevant trigger.
      </div>
    </div>
  </div>

<!--두번째 카드-->
  <div class="col">
    <div class="collapse multi-collapse" id="multiCollapseExample2">
      <div class="card card-body">
        Some placeholder content for the second collapse component of this multi-collapse example. This panel is hidden by default but revealed when the user activates the relevant trigger.
      </div>
    </div>
  </div>
</div>
```

### ⚠️주의⚠️

<aside>
1️⃣ collapse를 사용하기 위해서는 `aria-expanded`를 반드시 추가해줘야 합니다. 이 속성은 컨트롤레 연결된 접을 수 있는 요소의 현재 상태를 리더나 동일한 지원 기술에 명시적으로 전달합니다. 요소가 기본으로 닫혀있으려면 `aria-expanded=”false”`로 명시합니다.
</aside>
</br>

<aside>
2️⃣ `data-bs-target` 속성이 `id` 셀렉터를 바라보는 경우, 접을 수 있는 요소의 `id`를 한 `aria-controls` 속성을 컨트롤 요소에 추가하지 않으면 안 됩니다.

</aside>
  </div>
</details>

<details>
  <summary> 6-11. dropdown </summary>
  <div>

  `TODO`

1. data-bs-toggle이 무엇인지 찾아보기 
    
    `data-bs-toggle`과 `data-bs-target`을 사용하면 대상을 지정해 요소의 동작을 자동으로 할당할 수 있습니다. 예시로 `data-bs-toggle = “collapse/dropdown”` 등을 사용하고, 그게 적용될 타겟을 `data-bs-target`의 값에 적는 것입니다. 
    
    `data-bs-toggle=dropdown`을 제거하면 버튼을 눌러도 리스트가 보이지 않습니다. 
    
    - 코드
        
        ```html
        <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
        	Button with data-bs-target
        </button>
        
        <!--버튼을 누르면 나오는 카드-->
        <div class="collapse" id="collapseExample">
          <div class="card card-body">
            Some placeholder content for the collapse component. This panel is hidden by default but revealed when the user activates the relevant trigger.
          </div>
        </div>
        ```
        
2. dropdown-toggle 테스트 해보기
    - 실습
        
        dropdown-toggle 제거시 버튼에서 화살표가 없어짐
             
        → 이를 통해 .dropdown-toggle은 버튼에서 화살표를 표시해주는 클래스임을 추측할 수 있습니다. 
        
    - 코드
        
        ```html
        <div class="dropdown">
        
          <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown button
          </button>
        
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        
        </div>
        ```
        

---

드롭다운은 동적인 포지셔닝과 뷰포트 검출을 제공하는 서드 파티의 라이브러리인 `Popper`로 빌드되어 있습니다. 그래서 Bootstrap의 Javascript 전에 `popper.min.js`를 넣거나 Popper를 포함한 `bootstrap.bundle.min.js/bootstrap.bundle.js`를 사용해야 합니다. 

### 기본 예시

버튼을 누르면 `.dropdown-menu`에 있는 리스트를 확인할 수 있습니다. secondary 색 외에도 모든 색에 대한 드롭다운을 만들 수 있습니다. 

```html
<div class="dropdown">

  <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
    Dropdown button
  </button>

  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
  </ul>

</div>
```

### 분할버튼

`.dropdown-toggle-split`을 `<button> 요소`에 클래스로 추가해 드롭다운 화살표 주위의 적절한 간격을 확보할 수 있습니다.

→ 화살표의 좌우 padding을 25% 줄이고, margin-left를 삭제 

```html
<!-- Example split danger button -->
<div class="btn-group">
  <button type="button" class="btn btn-danger">Action</button>
  <button type="button" class="btn btn-danger dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
    <span class="visually-hidden">Toggle Dropdown</span>
  </button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider"></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
</div>
```

### 크기 조절

드롭다운의 크기는<button> 택에 `.btn-{breakpoint}`를 추가해서 적용할 수 있습니다. 

```html
<div class="btn-group">
  <button class="btn btn-secondary btn-sm dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
    Small button
  </button>
  <ul class="dropdown-menu">
    ...
  </ul>
</div>
<div class="btn-group">
  <button class="btn btn-secondary btn-sm" type="button">
    Small split button
  </button>
  <button type="button" class="btn btn-sm btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
    <span class="visually-hidden">Toggle Dropdown</span>
  </button>
  <ul class="dropdown-menu">
    ...
  </ul>
</div>
```

### Dropup

드롭다운이 아닌, `.dropup`을 이용해 드롭업을 할 수도 있습니다. 

- 코드
    
    ```html
    <!-- Default dropup button -->
    <div class="btn-group dropup">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
        Dropup
      </button>
      <ul class="dropdown-menu">
        <!-- Dropdown menu links -->
      </ul>
    </div>
    
    <!-- Split dropup button -->
    <div class="btn-group dropup">
      <button type="button" class="btn btn-secondary">
        Split dropup
      </button>
      <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
        <span class="visually-hidden">Toggle Dropdown</span>
      </button>
      <ul class="dropdown-menu">
        <!-- Dropdown menu links -->
      </ul>
    </div>
    ```
    

- Dropend

부모 요소에 .dropend를 추가해 요소의 오른쪽에도 표시할 수 있습니다. 

- 코드
    
    ```html
    <!-- Default dropend button -->
    <div class="btn-group dropend">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
        Dropend
      </button>
      <ul class="dropdown-menu">
        <!-- Dropdown menu links -->
      </ul>
    </div>
    
    <!-- Split dropend button -->
    <div class="btn-group dropend">
      <button type="button" class="btn btn-secondary">
        Split dropend
      </button>
      <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
        <span class="visually-hidden">Toggle Dropend</span>
      </button>
      <ul class="dropdown-menu">
        <!-- Dropdown menu links -->
      </ul>
    </div>
    ```
    

- Dropstart

부모요소에 .dropstart를 추가해 요소의 왼쪽에도 추가할 수 있습니다.

- 코드
    
    ```html
    <!-- Default dropstart button -->
    <div class="btn-group dropstart">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
        Dropstart
      </button>
      <ul class="dropdown-menu">
        <!-- Dropdown menu links -->
      </ul>
    </div>
    
    <!-- Split dropstart button -->
    <div class="btn-group dropstart">
      <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">
        <span class="visually-hidden">Toggle Dropstart</span>
      </button>
      <ul class="dropdown-menu">
        <!-- Dropdown menu links -->
      </ul>
      <button type="button" class="btn btn-secondary">
        Split dropstart
      </button>
    </div>
    ```
    

### 메뉴 정렬

기본적으로, 드롭다운 메뉴는 자동으로 위에서 100%위치와, 부모의 왼쪽에 따라 배치됩니다. 이는 `.drop* 클래스`로 방향을 조절할 수 있습니다. 

드롭다운을 오른쪽으로 배치하려면 `.dropdown-menu`에 `.dropdown-menu-end`를 추가하면 됩니다. 

dropdown-menu-center (기본값이랑 비슷) → 테스트

dropdown-menu-end

```html
<div class="btn-group">
  <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
    Right-aligned menu example
  </button>
  <ul class="dropdown-menu dropdown-menu-end">
    <li><button class="dropdown-item" type="button">Action</button></li>
    <li><button class="dropdown-item" type="button">Another action</button></li>
    <li><button class="dropdown-item" type="button">Something else here</button></li>
  </ul>
</div>
```

### 정렬 옵션

여러개의 다양한 드롭다운을 한 곳에 위치시킬 수도 있습니다. 

- 코드
    
    ```html
    <div class="btn-group">
      <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
        Dropdown
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
      </ul>
    </div>
    
    <div class="btn-group">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
        Right-aligned menu
      </button>
      <ul class="dropdown-menu dropdown-menu-end">
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
      </ul>
    </div>
    
    <div class="btn-group">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" data-bs-display="static" aria-expanded="false">
        Left-aligned, right-aligned lg
      </button>
      <ul class="dropdown-menu dropdown-menu-lg-end">
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
      </ul>
    </div>
    
    <div class="btn-group">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" data-bs-display="static" aria-expanded="false">
        Right-aligned, left-aligned lg
      </button>
      <ul class="dropdown-menu dropdown-menu-end dropdown-menu-lg-start">
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
      </ul>
    </div>
    
    <div class="btn-group dropstart">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
        Dropstart
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
      </ul>
    </div>
    
    <div class="btn-group dropend">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
        Dropend
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
      </ul>
    </div>
    
    <div class="btn-group dropup">
      <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
        Dropup
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
        <li><a class="dropdown-item" href="#">Menu item</a></li>
      </ul>
    </div>
    ```
    

### 메뉴 콘텐츠

- 헤더
    
    임의의 드롭다운 메뉴에서 .dropdown-header를 이용해 헤더를 추가할 수 있습니다.
      
    - 코드
        
        ```html
        <ul class="dropdown-menu">
          <li><h6 class="dropdown-header">Dropdown header</h6></li>
          <li><a class="dropdown-item" href="#">Action</a></li>
          <li><a class="dropdown-item" href="#">Another action</a></li>
        </ul>
        ```
        
- 구분선
    
    구분선으로 드롭메뉴에서 관련 아이템끼리 나눌 수 있습니다.
      
    - 코드
        
        ```html
        <ul class="dropdown-menu">
          <li><a class="dropdown-item" href="#">Action</a></li>
          <li><a class="dropdown-item" href="#">Another action</a></li>
          <li><a class="dropdown-item" href="#">Something else here</a></li>
        
        	<!--구분선-->
          <li><hr class="dropdown-divider"></li>
        
          <li><a class="dropdown-item" href="#">Separated link</a></li>
        </ul>
        ```
        

### 폼

드롭다운 메뉴 안에 폼을 넣을 수도 있습니다. 

- 코드
    
    ```html
    <div class="dropdown-menu">
    
      <form class="px-4 py-3">
        <div class="mb-3">
          <label for="exampleDropdownFormEmail1" class="form-label">Email address</label>
          <input type="email" class="form-control" id="exampleDropdownFormEmail1" placeholder="email@example.com">
        </div>
        <div class="mb-3">
          <label for="exampleDropdownFormPassword1" class="form-label">Password</label>
          <input type="password" class="form-control" id="exampleDropdownFormPassword1" placeholder="Password">
        </div>
        <div class="mb-3">
          <div class="form-check">
            <input type="checkbox" class="form-check-input" id="dropdownCheck">
            <label class="form-check-label" for="dropdownCheck">
              Remember me
            </label>
          </div>
        </div>
        <button type="submit" class="btn btn-primary">Sign in</button>
      </form>
    
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">New around here? Sign up</a>
      <a class="dropdown-item" href="#">Forgot password?</a>
    </div>
    ```
    
  </div>
</details>

<details>	
  <summary> 6-12. list group</summary>
  <div>
    목록 그룹은 일련의 콘텐츠를 보여주기 위한 유연하고, 강력한 컴포넌트 입니다. 그룹을 변경하거나 확장해 모든 콘텐츠를 지원할 수 있습니다. 

### 기본 예시

리스트는 `.list-group`로, 각 리스트 항목은 `.list-group-item`으로 설정해 표현할 수 있습니다. 

```html
<ul class="list-group">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
  <li class="list-group-item">A fourth item</li>
  <li class="list-group-item">And a fifth one</li>
</ul>
```

- 활성화된 항목
    
    `.list-group-item`에 `.active`를 추가해 현재 활성화 된 선택 범위를 알 수 있습니다. 
     
    ```html
    <ul class="list-group">
      <li class="list-group-item active" aria-current="true">An active item</li>
      <li class="list-group-item">A second item</li>
      <li class="list-group-item">A third item</li>
      <li class="list-group-item">A fourth item</li>
      <li class="list-group-item">And a fifth one</li>
    </ul>
    ```
    

- 비활성화된 항목
    
    `.list-group-item`에 `.disabled`를 추가하면 비활성화 할 수 있습니다. 
    
    ```html
    <ul class="list-group">
    	<li class="list-group-item disabled" aria-disabled="true">A disabled item</li>
    </ul>
    ```
    

### 링크와 버튼

`<a>`나 `<button>`에 `.list-group-item-action`을 사용해 actionable한 목록 그룹 아이템을 만들 수 있습니다. 

> 여기에서는 `표준 .btn 클래스`를 사용하지 않도록 주의해야 합니다
> 

```html
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action active" aria-current="true">
    The current link item
  </a>
  <a href="#" class="list-group-item list-group-item-action">A second link item</a>
  <a href="#" class="list-group-item list-group-item-action">A third link item</a>
  <a href="#" class="list-group-item list-group-item-action">A fourth link item</a>

<!--리스트 비활성화-->
  <a class="list-group-item list-group-item-action disabled" aria-disabled="true">A disabled link item</a>
</div>
```

`<button>` 에는 disabled 불리언 속성을 사용할 수 있습니다. `<a>`에는 disabled 속성이 지원되지 않습니다. 

```html
<div class="list-group">
  <button type="button" class="list-group-item list-group-item-action active" aria-current="true">
    The current button
  </button>
  <button type="button" class="list-group-item list-group-item-action">A second button item</button>
  <button type="button" class="list-group-item list-group-item-action">A third button item</button>
  <button type="button" class="list-group-item list-group-item-action">A fourth button item</button>
  <button type="button" class="list-group-item list-group-item-action" disabled>A disabled button item</button>
</div>
```

### 숫자

`.list-group-numbered`라는 제어자 클래스를 추가해 `숫자 목록 리스트 그룹`을 만들 수 있습니다. 숫자는 css에 의해 추가되므로 목록 그룹 아이템 내에서 배치가 간단하고 재정의하기도 쉽습니다. 

```html
<!--리스트를 추가하면 자동으로 4번이 생성됨-->
<ol class="list-group list-group-numbered">
  <li class="list-group-item">A list item</li>
  <li class="list-group-item">A list item</li>
  <li class="list-group-item">A list item</li>
</ol>
```

- 배지를 추가한 리스트 그룹
    
    - 코드
        
        ```html
        <ol class="list-group list-group-numbered">
        
          <li class="list-group-item d-flex justify-content-between align-items-start">
            <div class="ms-2 me-auto">
              <div class="fw-bold">Subheading</div>
              Content for list item
            </div>
        
            <span class="badge bg-primary rounded-pill">14</span>
          </li>
        
          <li class="list-group-item d-flex justify-content-between align-items-start">
            <div class="ms-2 me-auto">
              <div class="fw-bold">Subheading</div>
              Content for list item
            </div>
            <span class="badge bg-primary rounded-pill">14</span>
          </li>
        
          <li class="list-group-item d-flex justify-content-between align-items-start">
            <div class="ms-2 me-auto">
              <div class="fw-bold">Subheading</div>
              Content for list item
            </div>
            <span class="badge bg-primary rounded-pill">14</span>
          </li>
        
        </ol>
        ```
        

### 수평

`list group`의 아이템 레이아웃을 수평으로 놓고싶으면 `.list-group-horizonta`l을 추가하면 됩니다. 중단점에 따라 수평여부를 설정하고 싶으면 `.list-group-horizontal-{sm|md|lg|xl|xxl}`를 설정해 특정 중단점의 min-width로 시작하는 목록그룹으로 수평화할 수 있습니다. 

> ⚠️주의 : 수평 목록그룹을 flush 목록 그룹과 조합할 수는 없습니다.
> 

```html
<ul class="list-group list-group-horizontal">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>

<ul class="list-group list-group-horizontal-{sm|md|lg|xl|xxl">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
```

- 목록 그룹의 아이템을 수평 방향의 동일한 너비로 설정하고 싶다면 목록 그룹의 각 아이템에 `.flex-fill`을 추가
- 위 예시에서 `한 행에 많은 <li>를 추가`했을 때 계속해서 양옆으로만 목록들이 추가되었습니다. 아래로 밀려나는 것은 없었음

### 색상

리스트 아이템에 색을 적용하고 싶으면 `.list-group-item`에 `.list-group-item-{color}`를 설정하면 됩니다.

```html
<ul class="list-group">
	<li class="list-group-item list-group-item-primary">A simple primary list group item</li>
</ul>
```

- 색상 적용된 리스트 그룹에 링크 걸기
    
    ```html
    <div class="list-group">
    	<a href="#" class="list-group-item list-group-item-action list-group-item-primary">A simple primary list group item</a>
    </div>
    ```
    

### 배지 포함

```html
<ul class="list-group">
  <li class="list-group-item d-flex justify-content-between align-items-center">
    A list item
    <span class="badge bg-primary rounded-pill">14</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    A second list item
    <span class="badge bg-primary rounded-pill">2</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    A third list item
    <span class="badge bg-primary rounded-pill">1</span>
  </li>
</ul>
```

- `d-flex` : 1번 사진에서 2번 사진으로 만들어 주는 속성
    - 내부 아이템을 수직으로 정렬해주는 것?
    - 사진
        
        [참고 링크](https://espania.tistory.com/142)
        
        ![1번](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/08ae18db-d51b-4578-b21e-59e27e5a61d7/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7(36).png)
        
        1번
        
        ![2번](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/baefe792-8200-4c2c-8885-732832edd867/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7(37).png)
        
        2번
        
    

### 체크박스와 라디오버튼

리스트 아이템에 체크박스와 라디오버튼을 적용할 수 있습니다. 

```html
<ul class="list-group">
	<li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" id="firstCheckbox">
    <label class="form-check-label" for="firstCheckbox">First checkbox</label>
  </li>
	<li class="list-group-item">
    <input class="form-check-input me-1" type="radio" name="listGroupRadio" value="" id="firstRadio" checked>
    <label class="form-check-label" for="firstRadio">First radio</label>
	</li>
</li>
```
  </div>
</details>


<details>
  <summary> 6-13. Modal </summary>
  <div>
  모달은 일반적으로 기존 화면 위에 `플로팅` 되는 화면을 의미합니다. 

### 작동 원리

- 모달은 문서 내의 `다른 모든것 위`에 배치되어 <body>의 스크롤을 제거하고 모달의 콘텐츠가 스크롤 되도록 함
- 모달의 `“배경”을 클릭`하면 자동으로 모달이 닫힘
- `한번에 하나`의 모달만 지원(중첩된 모달은 지원 안됨)
- `position: fixed` 사용
- 가능한 다른 요소와의 간섭을 피하기 위해 모달 html을 `최상단`에 위치(다른 고정 요소 안에 `.modal`을 중첩해 넣으면 문제 가능성 높음)

### 예시

- static 모달 예시
    
    - position과 display가 오버라이드 됨
    - 모달 header, 모달 body, 모달 footer가 포함됨
    - 코드
        
        ```html
        <div class="modal" tabindex="-1">
          <div class="modal-dialog">
            <div class="modal-content">
        
              <div class="modal-header">
                <h5 class="modal-title">Modal title</h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
              </div>
        
              <div class="modal-body">
                <p>Modal body text goes here.</p>
              </div>
        
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary">Save changes</button>
              </div>
        
            </div>
          </div>
        </div>
        ```
        
        - `tabindex=”-1”`
            
            tabindex는 키보드로 포커스를 줄 수 있는 속성입니다.
            tabindex=-1로 설정하면 키보드 탭으로 포커스가 잡히지 않게 됩니다.
            이렇게 하는 이유는 다음 주제 영역으로 갈 때 그 사이에 있는 a태그를 거치지 않기 위함입니다.
            
        - `modal-dialog`
        - `modal-content`

### 라이브 데모

버튼을 누르면 모달 화면이 위에서 아래로 나타납니다. 

위에서 언급한 것처럼 모달창이 띄어져있을 때 배경을 클릭하면 모달창이 닫힙니다. 

- 코드
    
    ```html
    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
      Launch demo modal
    </button>
    
    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
    
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
    
          <div class="modal-body">
            ...
          </div>
    
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
    
        </div>
      </div>
    </div>
    ```
    

### 정적 백드롭

백드롭을 static으로 설정하면 배경을 클릭해도 모달은 닫히지 않습니다. 

- 코드
    
    ```html
    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#staticBackdrop">
      Launch static backdrop modal
    </button>
    
    <!-- Modal -->
    <div class="modal fade" id="staticBackdrop" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1" aria-labelledby="staticBackdropLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
    
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="staticBackdropLabel">Modal title</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
    
          <div class="modal-body">
            ...
          </div>
    
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Understood</button>
          </div>
    
        </div>
      </div>
    </div>
    ```
    

### 콘텐츠 스크롤

`.modal-dialog`에 `.modal-dialog-scrollable`을 추가하면 긴 모달 본체를 스크롤 할 수 있습니다. 

```html
<!-- Scrollable modal -->
<div class="modal-dialog modal-dialog-scrollable">
  ...
</div>
```

### 모달 간 토글

`data-bs-target` 과 `data-bs-toggle` 속성을 교묘하게 배치함으로써 여러 모달을 토글할 수 있습니다. 예시로 이미 열려있는 로그인 모달에서 비밀번호 재설정의 모달을 열 수 있습니다. `주의할 점`은 여러 개의 모달을 동시에 열 수 없습니다. 

- 첫번째 모달 코드
    
    ```html
    <div class="modal fade" id="exampleModalToggle" aria-hidden="true" aria-labelledby="exampleModalToggleLabel" tabindex="-1">
      <div class="modal-dialog modal-dialog-centered">
        <div class="modal-content">
    
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalToggleLabel">Modal 1</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            Show a second modal and hide this one with the button below.
          </div>
          <div class="modal-footer">
            <button class="btn btn-primary" data-bs-target="#exampleModalToggle2" data-bs-toggle="modal">Open second modal</button>
          </div>
    
        </div>
      </div>
    </div>
    ```
    

- 두번째 모달 코드
    
    ```html
    
    <div class="modal fade" id="exampleModalToggle2" aria-hidden="true" aria-labelledby="exampleModalToggleLabel2" tabindex="-1">
      <div class="modal-dialog modal-dialog-centered">
        <div class="modal-content">
    
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalToggleLabel2">Modal 2</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
    
          <div class="modal-body">
            Hide this modal and show the first with the button below.
          </div>
    
          <div class="modal-footer">
            <button class="btn btn-primary" data-bs-target="#exampleModalToggle" data-bs-toggle="modal">Back to first</button>
          </div>
    
        </div>
      </div>
    </div>
    
    <button class="btn btn-primary" data-bs-target="#exampleModalToggle" data-bs-toggle="modal">Open first modal</button>
    ```
    
  </div>
</details>

<details>
  <summary> 6-14. Navbar </summary>
  <div>
    ### 작동 원리

- 내비게이션 바는 `.navbar`를 `.navbar-expand-{sm|md|lg|xl|xxl}`로 감싸야하고, color scheme 클래스 필요
- 내비게이션과 그 콘텐츠는 기본적으로 유동적임. container를 변경해 다양한 방법으로 가로폭 제한 가능
- 접근성 확보를 위해 `<nav> 요소`를 사용하거나, `<div>에 role=”navigation”`을 추가해 스크린 리더 사용자를 위해 랜드마크가 되는 곳임을 명시적으로 알려줘야 함
- 현재 페이지에는 `aria-current=”page”`, 세트 안에서의 현재 아이템은 `aria-current=”true’`를 사용해 표현할 수 있음

### 지원 콘텐츠

내비게이션에서 지원하는 `서브 컴포넌트`는 다음과 같습니다. 

- `.navbar-brand` : 회사/제품/프로젝트 이름
- `.navbar-nav` : full-height 보다 가벼운 네비게이션
- `.navbar-toggler`
- `.navbar-text` : 수직 방향으로 센터링된 문자열 추가
- `.collapse.navbar-collapse` : 부모 중단점에 따라 내비게이션 바의 콘텐츠 그룹화 또는 감출 수 있음
- `.navbar-scroll` : max-height와 scroll expanded navbar content 가능

### 기본 예시

- 코드
    
    ```html
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
    
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
    
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
    
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
    
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
    
            <li class="nav-item">
              <a class="nav-link" href="#">Link</a>
            </li>
    
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                Dropdown
              </a>
              <ul class="dropdown-menu">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><hr class="dropdown-divider"></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
              </ul>
            </li>
    
            <li class="nav-item">
              <a class="nav-link disabled" aria-disabled="true">Disabled</a>
            </li>
          </ul>
    
          <form class="d-flex" role="search">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-outline-success" type="submit">Search</button>
          </form>
        </div>
    
      </div>
    </nav>
    ```
    

### 브랜드

`.navbar-brand`를 이용해 대부분의 요소에 적용 가능합니다. 

- 텍스트
    
    `.navbar-brand` 클래스(클래스에 따른 css를 먹음)를 요소 내의 텍스트에 추가
    
    - 코드
        
        ```html
        <!-- As a link -->
        <nav class="navbar bg-body-tertiary">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">Navbar</a>
          </div>
        </nav>
        
        <!-- As a heading -->
        <nav class="navbar bg-body-tertiary">
          <div class="container-fluid">
            <span class="navbar-brand mb-0 h1">Navbar</span>
          </div>
        </nav>
        ```
        
    
- 이미지
      
    `.navbar-brand` 안에 텍스트 대신 `<img>`를 사용할 수 있습니다. 
    
    - 코드
        
        ```html
        <nav class="navbar bg-body-tertiary">
          <div class="container">
            <a class="navbar-brand" href="#">
              <img src="/docs/5.3/assets/brand/bootstrap-logo.svg" alt="Bootstrap" width="30" height="24">
            </a>
          </div>
        </nav>
        ```
        
    
- 이미지 & 텍스트
       
    추가 유틸리티를 사용해 이미지와 텍스트를 동시에 추가할 수 있습니다. `<img>`에 `.d-inline-block`과 `.align-text-top`을 사용하고 있다는 것에 주목해야 합니다. 
    
    ```html
    <nav class="navbar bg-body-tertiary">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="/docs/5.3/assets/brand/bootstrap-logo.svg" alt="Logo" width="30" height="24" class="d-inline-block align-text-top">
          Bootstrap
        </a>
      </div>
    </nav>
    ```
    

### 네비게이션 바

내비게이션 바 안에서 내비게이션 링크는 **수평 방향으로 펼쳐져 깔끔하게 정렬**됩니다. 

- 현재 페이지 나타내기
    - `.nav-link`에 `.active`를 추가
    - `.nav-link`에는 `aria-current 속성` 추가

- 기본 예시
      
    - 코드
        
        ```html
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
          <div class="container-fluid">
        
            <a class="navbar-brand" href="#">Navbar</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
        
            <div class="collapse navbar-collapse" id="navbarNav">
        
              <ul class="navbar-nav">
                <li class="nav-item">
                  <a class="nav-link active" aria-current="page" href="#">Home</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">Features</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">Pricing</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link disabled" aria-disabled="true">Disabled</a>
                </li>
              </ul>
        
            </div>
        
          </div>
        </nav>
        ```
        

- 기본 예시와 동일한 화면이지만 <li> 없애기
    - `.nav-link`를 사용하고 있기에 목록 기반 접근법을 완전히 피할 수 있음
    - 코드
        
        ```html
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
          <div class="container-fluid">
        
            <a class="navbar-brand" href="#">Navbar</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
        
            <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
              <div class="navbar-nav">
                <a class="nav-link active" aria-current="page" href="#">Home</a>
                <a class="nav-link" href="#">Features</a>
                <a class="nav-link" href="#">Pricing</a>
                <a class="nav-link disabled" aria-disabled="true">Disabled</a>
              </div>
            </div>
        
          </div>
        </nav>
        ```
        

- 내비게이션 바에 드롭다운 사용하기
    
    드롭다운 메뉴는 `배치를 위한 줄바꿈 요소`가 필요하기 때문에 `.nav-item`과 `.nav-link`는 다른 중첩된 요소로 분리해 사용해야 합니다.
    
    - 코드
        
        ```html
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
          <div class="container-fluid">
        
            <a class="navbar-brand" href="#">Navbar</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
        
            <div class="collapse navbar-collapse" id="navbarNavDropdown">
              <ul class="navbar-nav">
        
                <li class="nav-item">
                  <a class="nav-link active" aria-current="page" href="#">Home</a>
                </li>
        
                <li class="nav-item">
                  <a class="nav-link" href="#">Features</a>
                </li>
        
                <li class="nav-item">
                  <a class="nav-link" href="#">Pricing</a>
                </li>
        
                <li class="nav-item dropdown">
                  <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                    Dropdown link
                  </a>
                  <ul class="dropdown-menu">
                    <li><a class="dropdown-item" href="#">Action</a></li>
                    <li><a class="dropdown-item" href="#">Another action</a></li>
                    <li><a class="dropdown-item" href="#">Something else here</a></li>
                  </ul>
                </li>
              </ul>
            </div>
        
          </div>
        </nav>
        ```
        

### 폼

내비게이션 바 내에 다양한 폼 컨트롤 및 컴포넌트를 배치할 수 있습니다. 이 외에 `input group`, `button`을 내비게이션 바에 추가할 수 있습니다. 

```html
<nav class="navbar bg-body-tertiary">

  <div class="container-fluid">
    <form class="d-flex" role="search">
      <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success" type="submit">Search</button>
    </form>
  </div>

</nav>
```

### 텍스트

문자열의 수직 방향과 수평 간격을 `.navbar-text`로 조절할 수 있습니다. 

```html
<nav class="navbar bg-body-tertiary">
  <div class="container-fluid">
    <span class="navbar-text">
      Navbar text with an inline element
    </span>
  </div>
</nav>
```

### 색상 스키마

어두운 버전의 내비게이션은 `data-bs-theme=”dark”`를 추가하거나 `style=”background-color: {color};”`를 `.nav`에 추가하면 됩니다. 

```html
<nav class="navbar bg-dark border-bottom border-body" data-bs-theme="dark">
  <!-- Navbar content -->
</nav>

<nav class="navbar bg-primary" data-bs-theme="dark">
  <!-- Navbar content -->
</nav>

<nav class="navbar" style="background-color: #e3f2fd;">
  <!-- Navbar content -->
</nav>
```

### 배치

위치 유틸리티를 사용해 내비게이션 바를 정적이지 않은 위치에 배치할 수 있습니다. 

- 상단/하단 고정 : `fixed-{top|bottom}`

    - 코드
        
        ```html
        <!--Fixed top-->
        <nav class="navbar fixed-top bg-body-tertiary">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">Fixed top</a>
          </div>
        </nav>
        
        <!--Fixed bottom-->
        <nav class="navbar fixed-bottom bg-body-tertiary">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">Fixed bottom</a>
          </div>
        </nav>
        ```
        
- `sticky-{top|bottom}`
    
    - 코드
        
        ```html
        <!--Sticky top -->
        <nav class="navbar sticky-top bg-body-tertiary">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">Sticky top</a>
          </div>
        </nav>
        
        <!--Sticky bottom -->
        <nav class="navbar sticky-bottom bg-body-tertiary">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">Sticky bottom</a>
          </div>
        </nav>
        ```
        

### 반응형 행동

`.navbar-toggler`, `.navbar-collapse`, `.navbar-expand-{sm| md | lg| xl | xxl}` 클래스를 사용해 **콘텐츠가 버튼 뒤쪽에서 접히는 시점을 결정**할 수 있습니다. 

항상 접히는 내비게이션 바의 경우에는 `.navbar-expand` 클래스를 추가하지 않아도 됩니다. 

- 토글
    
    내비게이션 바의 토글은 기본적으로 왼쪽 정렬이지만, .navbar-brand와 같은 형제 요소와 연결되는 경우는 자동으로 오른쪽 정렬이 됨
     
    - 코드
        
        ```html
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
          <div class="container-fluid">
        
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarTogglerDemo01" aria-controls="navbarTogglerDemo01" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
        
            <div class="collapse navbar-collapse" id="navbarTogglerDemo01">
              <a class="navbar-brand" href="#">Hidden brand</a>
              <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                  <a class="nav-link active" aria-current="page" href="#">Home</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">Link</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link disabled" aria-disabled="true">Disabled</a>
                </li>
              </ul>
        
              <form class="d-flex" role="search">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success" type="submit">Search</button>
              </form>
        
            </div>
          </div>
        
        </nav>
        ```
        
    
- 외부 콘텐츠
    
    구조적으로 .navbar 바깥쪽에 있는 콘텐츠를 위해 collapse plugin을 사용해 컨테이너 요소를 트리거할 때 사용할 수 있습니다. 
    
    ```html
    <div class="collapse" id="navbarToggleExternalContent" data-bs-theme="dark">
      <div class="bg-dark p-4">
        <h5 class="text-body-emphasis h4">Collapsed content</h5>
        <span class="text-body-secondary">Toggleable via the navbar brand.</span>
      </div>
    </div>
    
    <!--메뉴 버튼--> 
    <!--data-bs-target이 위의 id를 가리키고 있음을 알 수 있음-->
    <nav class="navbar navbar-dark bg-dark">
      <div class="container-fluid">
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarToggleExternalContent" aria-controls="navbarToggleExternalContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
      </div>
    </nav>
    ```
    
- 오프캔버스
    
    버튼을 누르면 가장 바깥 웹 페이지에서 내비게이션이 열릴 수 있습니다. 
    
    `.navbar-expand-*` 를 이용하면 됩니다. 
     
    - 코드
        
        ```html
        <nav class="navbar bg-body-tertiary fixed-top">
          <div class="container-fluid">
        
            <a class="navbar-brand" href="#">Offcanvas navbar</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar" aria-controls="offcanvasNavbar" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
        
            <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasNavbar" aria-labelledby="offcanvasNavbarLabel">
        
              <div class="offcanvas-header">
                <h5 class="offcanvas-title" id="offcanvasNavbarLabel">Offcanvas</h5>
                <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
              </div>
        
              <div class="offcanvas-body">
                <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
                  <li class="nav-item">
                    <a class="nav-link active" aria-current="page" href="#">Home</a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link" href="#">Link</a>
                  </li>
                  <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                      Dropdown
                    </a>
                    <ul class="dropdown-menu">
                      <li><a class="dropdown-item" href="#">Action</a></li>
                      <li><a class="dropdown-item" href="#">Another action</a></li>
                      <li>
                        <hr class="dropdown-divider">
                      </li>
                      <li><a class="dropdown-item" href="#">Something else here</a></li>
                    </ul>
                  </li>
                </ul>
        
                <form class="d-flex mt-3" role="search">
                  <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                  <button class="btn btn-outline-success" type="submit">Search</button>
                </form>
              </div>
            </div>
        
          </div>
        </nav>
        ```
  </div>
</details>

<details>
  <summary> 6-15. Navs and tabs </summary>
  <div>

  Boostrap에 포함된 내비게이션 컴포넌트를 어떻게 사용하는지에 대한 설명입니다. 

### 기본 내비게이션

`.nav` 클래스에 `.nav-item`으로 구현하고, 현재 있는 페이지 활성화는 `.active`로 표현하면 됩니다. 비활성화는 `.disabled`를 추가하면 됩니다. (disabled 불리언 속성으로는 적용이 되지 않습니다)

```html
<ul class="nav">

  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>

  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>

  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>

  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>

</ul>
```

### 정렬

내비게이션의 기본은 왼쪽 정렬이지만 `.justify-content-{center|end}`를 이용해 내비게이션 정렬을 변경할 수 있습니다. 

- 가운데 정렬
     
    - 코드
        
        ```html
        <ul class="nav justify-content-center">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Active</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" aria-disabled="true">Disabled</a>
          </li>
        </ul>
        ```
        
    
- 오른쪽 정렬
       
    - 코드
        
        ```html
        <ul class="nav justify-content-end">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Active</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" aria-disabled="true">Disabled</a>
          </li>
        </ul>
        ```
        
    

### 수직 정렬

`.flex-column` 을 이용해 내비게이션을 세로로 만들 수 있습니다. 특정 뷰포트에서 이를 적용하고 싶지 않다면 `.flex-{sm|md|lg|xl|xxl}-column`을 사용해주세요. 아래 코드 1번, 2번 모두 아래 화면을 만듭니다. 

```html
<!--1번-->
<ul class="nav flex-column">
  <li class="nav-item">
    <a class="nav-link active" aria-current="page" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" aria-disabled="true">Disabled</a>
  </li>
</ul>

<!--2번-->
<nav class="nav flex-column">
  <a class="nav-link active" aria-current="page" href="#">Active</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" aria-disabled="true">Disabled</a>
</nav>

```

### 탭

`.nav-tabs 클래스`로 탭이 있는 내비게이션을 구현할 수 있습니다. 

- 코드
    
    ```html
    <ul class="nav nav-tabs">
      <li class="nav-item">
        <a class="nav-link active" aria-current="page" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" aria-disabled="true">Disabled</a>
      </li>
    </ul>
    ```
    

### Pills

`.nav-pills`를 사용해 아래와 같이 만들 수 있습니다. 

- 코드
    
    ```html
    <ul class="nav nav-pills">
      <li class="nav-item">
        <a class="nav-link active" aria-current="page" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" aria-disabled="true">Disabled</a>
      </li>
    </ul>
    ```
    

### Underline

`.nav-underline`을 이용해 내비게이션 현재 페이지에 밑줄을 그을 수 있습니다. 

- 코드
    
    ```html
    <ul class="nav nav-underline">
      <li class="nav-item">
        <a class="nav-link active" aria-current="page" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" aria-disabled="true">Disabled</a>
      </li>
    </ul>
    ```
    

### 접근성에 대하여

내비게이션 바를 제공하기 위해 내비게이션을 사용하고 있는 경우, `<ul>`의 부모 컨테이너에 `role="navigation"`을 추가하거나, `<nav>` 요소를 내비게이션 전체에 감싸주세요. role을 `<ul>` 자체에 추가하지 마세요.

내비게이션 바는, `.nav-tabs`에서 시각적으로는 탭으로 보여지게 되있지만, `role="tablist"`, `role="tab"`, `role="tabpanel"` 속성을 부여하지 **말아** 주십시오. 이들은 [ARIA Authoring Practices Guide tabs pattern](https://www.w3.org/WAI/ARIA/apg/patterns/tabpanel/)에서 설명된 것처럼, 동적인 탭 인터페이스에만 적절합니다. [JavaScript behavior](https://getbootstrap.kr/docs/5.3/components/navs-tabs/#javascript-behavior)를 참조해 주십시오. JavaScript는 활성화된 탭에 `aria-selected="true"`를 추가하여 선택된 상태를 처리하기 때문에 인터페이스에서는 `aria-current` 속성이 필요하지 않습니다.

### 드롭다운 사용

`.dropdown 클래스`를 이용해 내비게이션에 드롭다운을 추가할 수 있습니다. 

- 드롭다운이 있는 탭
    
    - 코드
        
        ```html
        <ul class="nav nav-tabs">
        
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Active</a>
          </li>
        
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Dropdown</a>
            <ul class="dropdown-menu">
              <li><a class="dropdown-item" href="#">Action</a></li>
              <li><a class="dropdown-item" href="#">Another action</a></li>
              <li><a class="dropdown-item" href="#">Something else here</a></li>
              <li><hr class="dropdown-divider"></li>
              <li><a class="dropdown-item" href="#">Separated link</a></li>
            </ul>
          </li>
        
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" aria-disabled="true">Disabled</a>
          </li>
        
        </ul>
        ```
        
- 드롭다운이 있는 pills
    
    - 코드
        
        ```html
        <ul class="nav nav-pills">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Active</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Dropdown</a>
            <ul class="dropdown-menu">
              <li><a class="dropdown-item" href="#">Action</a></li>
              <li><a class="dropdown-item" href="#">Another action</a></li>
              <li><a class="dropdown-item" href="#">Something else here</a></li>
              <li><hr class="dropdown-divider"></li>
              <li><a class="dropdown-item" href="#">Separated link</a></li>
            </ul>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" aria-disabled="true">Disabled</a>
          </li>
        </ul>
        ```
  </div>
</details>


<details>
  <summary> 6-16. Pagination </summary>
  <div>
  페이지네이션은 여러 페이지에 일련의 내용이 관련이 있음을 나타냅니다. 

### 개요

페이지네이션은 `<nav> 요소`를 사용해 그것을 스크린 리더나 기타 지원 기술에서 내비게이션 영역으로 식별합니다. 

페이지에는 여러 개의 내비게이션 영역이 있을 가능성이 높기 때문에 그 목적을 반영하기 위해 `<nav>요소`에 `aria-label`을 붙이는 것을 권장합니다. 예시로 페이지네이션 컴포넌트를 사용해 `일련의 검색 결과 사이를 이동`하는 경우 적절한 라벨은 `aria-label=”Search results pages”`가 됩니다. 

### 예시

```html
<nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
</nav>
```

### 아이콘 사용하기

```html
<nav aria-label="Page navigation example">
  <ul class="pagination">
		<!--아이콘 적용 영역-->
    <li class="page-item">
      <a class="page-link" href="#" aria-label="Previous">
        <span aria-hidden="true">&laquo;</span>
      </a>
    </li>

    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
		<!--아이콘 적용 영역-->
    <li class="page-item">
      <a class="page-link" href="#" aria-label="Next">
        <span aria-hidden="true">&raquo;</span>
      </a>
    </li>

  </ul>
</nav>
```

### 비활성화 및 활성화 상태

페이지네이션에서도 클릭할 수 없는 링크에는 `.disabled`를, 현재 페이지는 `.active`를 사용합니다. 

<aside>
⚠️ `<a>요소`의 링크를 비활성화한다면 항상 `tabindex=”-1”`을 추가하고 그 기능을 완전히 비활성화 하기 위해 사용자 정의 JS를 사용해야 합니다.

</aside>

```html
<nav aria-label="...">
  <ul class="pagination">
    <li class="page-item disabled">
      <a class="page-link">Previous</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item active" aria-current="page">
      <a class="page-link" href="#">2</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```

### 크기 조절

페이지네이션의 크기 변경은 `.pagination-{sm|lg}`를 사용하면 됩니다. 

```html
<nav aria-label="...">
  <ul class="pagination pagination-lg">
    <li class="page-item active" aria-current="page">
      <span class="page-link">1</span>
    </li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
  </ul>
</nav>
```

### 정렬

페이지네이션의 정렬은 `.justify-content-{center|end}`를 사용하면 됩니다.

- 가운데 정렬

```html
<nav aria-label="Page navigation example">
  <ul class="pagination justify-content-center">
    <li class="page-item disabled">
      <a class="page-link">Previous</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```

- 오른쪽 정렬

```html
<nav aria-label="Page navigation example">
  <ul class="pagination justify-content-end">
    <li class="page-item disabled">
      <a class="page-link">Previous</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```
    
  </div>
</details>

<details>
  <summary> 6-17. Placeholders</summary>
  <div>
  로딩 플레이스홀더는 컴포넌트나 페이지에 아직 로딩 중임을 나타냅니다. 

플레이스홀더는 `애플리케이션 경험을 향상`시키는 데 사용할 수 있습니다. 플레이스홀더는 html과 css로만 만들어졌기 때문에 만드는데 Javascript가 필요하지 않지만, 가시성을 전환하려면 일부 사용자 정의 Javascript가 필요합니다. 

### 예제

일반적인 카드 컴포넌트를 가져와 `“로딩 카드”`를 만들기 위해 적용된 자리 표시자를 사용해 다시 만듭니다. 크기와 비율은 둘 사이에 동일합니다. 

```html
<div class="card">
  <img src="..." class="card-img-top" alt="...">

  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card" aria-hidden="true">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">

    <h5 class="card-title placeholder-glow">
      <span class="placeholder col-6"></span>
    </h5>

    <p class="card-text placeholder-glow">
      <span class="placeholder col-7"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-6"></span>
      <span class="placeholder col-8"></span>
    </p>

    <a class="btn btn-primary disabled placeholder col-6" aria-disabled="true"></a>
  </div>
</div>
```

### 작동 방법

`.placeholder 클래스`와 그리드 열 클래스(예 : .col-6)로 자리 표시자를 만들어 width를 설정합니다. 요소 내부의 텍스트를 바꾸거나 기존 컴포넌트에 수정자 클래스로 추가할 수 있습니다. 

```html
<p aria-hidden="true">
  <span class="placeholder col-6"></span>
</p>

<a class="btn btn-primary disabled placeholder col-4" aria-disabled="true"></a>
```

### 너비

여기에 `.bg-*`를 추가해 플레이스 홀더에 색상을 적용할 수도 있고, `.placeholder-{xs|sm|lg}`크기를 설정할 수도 있습니다.

```html
<span class="placeholder col-6"></span>
<span class="placeholder w-75"></span>
<span class="placeholder" style="width: 25%;"></span>
```

### 애니메이션

`.placeholder-glow` 또는 `.placeholder-wave`를 사용해 플레이스홀더에 애니메이션을 적용해 무언가가 활성적으로 로드되고 있다는 인식을 더 잘 전달할 수 있습니다. 

```html
<p class="placeholder-glow">
  <span class="placeholder col-12"></span>
</p>

<p class="placeholder-wave">
  <span class="placeholder col-12"></span>
</p>
```
  </div>
</details>

<details>
  <summary> 6-18. Popovers </summary>
  <div>
  ### 개요

- 팝오버는 서드파트 라이브러리인 `Popper`에 의존하고 있습니다. 부트스트랩 v5 이전이라면 `popper.min.js`를 추가하거나 v5 이후라면 `bootstrap.bundle.min.js`를 사용해야 합니다.
- 팝오버는 퍼포먼스를 위해 `opt-in` 되어 있기 때문에, 스스로 초기화를 해야 합니다.
- `길이가 0`인 title과 content 값은 팝오버를 표시하지 않습니다.
- 더 복잡한 컴포넌트(input group, button groups 등)의 렌더링 문제를 피하기 위해 `container: ‘body’`를 지정해줘야 합니다.
- `.disabled` 또는 `disabled` 요소의 팝오버는 그 바깥 요소에서 트리거 해야 합니다.

### 예시

- 팝오버 활성화
    
    팝오버를 사용하려면 사용 전에 팝오버를 `초기화`해줘야 합니다. 아래 코드르 <script> 태그 안에 추가해야 팝오버가 정상 작동 합니다. 
    
    ```jsx
    document.querySelectorAll('[data-bs-toggle="popover"]')
            .forEach(popover => {
              new bootstrap.Popover(popover)
    });
    ```
    

- Live demo
    
    팝오버의 title은 `data-bs-title`로, 바디 내용은 `data-bs-content`로 지정할 수 있습니다. 
      
    ```jsx
    <button type="button" class="btn btn-lg btn-danger" data-bs-toggle="popover" data-bs-title="Popover title" data-bs-content="And here's some amazing content. It's very engaging. Right?">Click to toggle popover</button>
    ```
    

### 사방위

팝오버는 `.data-bs-placement-{top|right|bottom|left}` 같이 4가지 옵션으로 표현할 수 있습니다. 

```jsx
<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="top" data-bs-content="Top popover">
  Popover on top
</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="right" data-bs-content="Right popover">
  Popover on right
</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="bottom" data-bs-content="Bottom popover">
  Popover on bottom
</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="left" data-bs-content="Left popover">
  Popover on left
</button>
```

### 다음 클릭으로 닫기

사용자가 다음 `토글 요소 이외의 요소`를 클릭했을 때 팝오버를 닫으려면 `focus 트리거`를 사용합니다. 

<aside>
⚠️ 브라우저나 플랫폼에 관계없이 제대로 다음 클릭으로 닫기를 위해서는 특정 html이 필요합니다. <button> 태그가 아닌 `<a> 태그`만 사용할 수 있으며, 반드시 `tabindex 속성`을 포함해야 합니다.

</aside>

```html
<a tabindex="0" class="btn btn-lg btn-danger" role="button" data-bs-toggle="popover" data-bs-trigger="focus" data-bs-title="Dismissible popover" data-bs-content="And here's some amazing content. It's very engaging. Right?">Dismissible popover</a>
```

```jsx
const popover = new bootstrap.Popover('.popover-dismiss', {
  trigger: 'focus'
})
```

### 비활성화 요소

disabled 속성을 추가해 팝오버를 비활성화 할 수 있습니다. 

```jsx
<span class="d-inline-block" tabindex="0" data-bs-toggle="popover" data-bs-trigger="hover focus" data-bs-content="Disabled popover">
  <button class="btn btn-primary" type="button" disabled>Disabled button</button>
</span>
``` 
  </div>
</details>

<details>
  <summary> 6-19. Popovers </summary>
  <div>

  ### 개요

- 팝오버는 서드파트 라이브러리인 `Popper`에 의존하고 있습니다. 부트스트랩 v5 이전이라면 `popper.min.js`를 추가하거나 v5 이후라면 `bootstrap.bundle.min.js`를 사용해야 합니다.
- 팝오버는 퍼포먼스를 위해 `opt-in` 되어 있기 때문에, 스스로 초기화를 해야 합니다.
- `길이가 0`인 title과 content 값은 팝오버를 표시하지 않습니다.
- 더 복잡한 컴포넌트(input group, button groups 등)의 렌더링 문제를 피하기 위해 `container: ‘body’`를 지정해줘야 합니다.
- `.disabled` 또는 `disabled` 요소의 팝오버는 그 바깥 요소에서 트리거 해야 합니다.

### 예시

- 팝오버 활성화
    
    팝오버를 사용하려면 사용 전에 팝오버를 `초기화`해줘야 합니다. 아래 코드르 <script> 태그 안에 추가해야 팝오버가 정상 작동 합니다. 
    
    ```jsx
    document.querySelectorAll('[data-bs-toggle="popover"]')
            .forEach(popover => {
              new bootstrap.Popover(popover)
    });
    ```
    

- Live demo
    
    팝오버의 title은 `data-bs-title`로, 바디 내용은 `data-bs-content`로 지정할 수 있습니다. 
       
    ```jsx
    <button type="button" class="btn btn-lg btn-danger" data-bs-toggle="popover" data-bs-title="Popover title" data-bs-content="And here's some amazing content. It's very engaging. Right?">Click to toggle popover</button>
    ```
    

### 사방위

팝오버는 `.data-bs-placement-{top|right|bottom|left}` 같이 4가지 옵션으로 표현할 수 있습니다. 

```jsx
<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="top" data-bs-content="Top popover">
  Popover on top
</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="right" data-bs-content="Right popover">
  Popover on right
</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="bottom" data-bs-content="Bottom popover">
  Popover on bottom
</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="left" data-bs-content="Left popover">
  Popover on left
</button>
```

### 다음 클릭으로 닫기

사용자가 다음 `토글 요소 이외의 요소`를 클릭했을 때 팝오버를 닫으려면 `focus 트리거`를 사용합니다. 

<aside>
⚠️ 브라우저나 플랫폼에 관계없이 제대로 다음 클릭으로 닫기를 위해서는 특정 html이 필요합니다. <button> 태그가 아닌 `<a> 태그`만 사용할 수 있으며, 반드시 `tabindex 속성`을 포함해야 합니다.

</aside>

```html
<a tabindex="0" class="btn btn-lg btn-danger" role="button" data-bs-toggle="popover" data-bs-trigger="focus" data-bs-title="Dismissible popover" data-bs-content="And here's some amazing content. It's very engaging. Right?">Dismissible popover</a>
```

```jsx
const popover = new bootstrap.Popover('.popover-dismiss', {
  trigger: 'focus'
})
```

### 비활성화 요소

disabled 속성을 추가해 팝오버를 비활성화 할 수 있습니다. 

```jsx
<span class="d-inline-block" tabindex="0" data-bs-toggle="popover" data-bs-trigger="hover focus" data-bs-content="Disabled popover">
  <button class="btn btn-primary" type="button" disabled>Disabled button</button>
</span>
```
    
  </div>
</details>

<details>
  <summary> 6-20. Progress </summary>
  <div>

  ### 작동원리

- `.progress`를 `wrapper`로 사용해 프로그레스 바에서 최대값을 가리킵니다.
- `.progress wrapper`는 `role="progressbar"`와 `aria 속성`(aria-label, aria-labelledby 등)을 필요로 합니다.
- 시각적인 바와 라벨을 위해 `inner .progress-bar`를 사용합니다.
- .`progress-bar`는 인라인 스타일, 유틸리티 클래스 혹은 custom CSS을 사용해 가로를 설정할 수 있습니다.
- 부트스트랩은 `multiple/stacked` 프로그레스 바를 만들기 위해 `.progress-stacked 클래스`를 지원합니다.

### 예시

```html
<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar" style="width: 0%"></div>
</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar" style="width: 25%"></div>
</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar" style="width: 50%"></div>
</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar" style="width: 75%"></div>
</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar" style="width: 100%"></div>
</div>
```

### Bar sizing

- width
    
    .progress-bar에 width를 설정할 수 있습니다. 
    
    ```html
    <div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
      <div class="progress-bar w-75"></div>
    </div>
    ```
    
- height
    
    `.progress`에는 `height 값`만 설정되어 있기 때문에, 이 값을 변경하면 내부 `.progress-bar`는 그에 따라 높이가 변경됩니다. 
    
    ```html
    <!--progress bar가 progress에 감싸기 때문에 같이 작아짐-->
    <!--html은 보여주기만 함-->
    <div class="progress" role="progressbar" aria-label="Example 1px high" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100" style="height: 1px">
      <div class="progress-bar" style="width: 25%"></div>
    </div>
    
    <div class="progress" role="progressbar" aria-label="Example 20px high" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100" style="height: 20px">
      <div class="progress-bar" style="width: 25%"></div>
    </div>
    ```
    

### Label

프로그레스 바에 라벨은 .progress-bar 안에 텍스트를 배치하면 됩니다. 

```html
<div class="progress" role="progressbar" aria-label="Example with label" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
  <!--div 태그 안에 있는 텍스트 값을 변경하면 됩니다-->
	<div class="progress-bar" style="width: 25%">25%</div>
</div>
```

만약 라벨 내부 내용이 프로그레스 바 길이보다 길다면, 이는 잘리게 됩니다. 

`.progress-bar`는 `overflow: hidden`으로 설정되어 있기 때문입니다. 

```html
<div class="progress" role="progressbar" aria-label="Example with label" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100">
      <div class="progress-bar overflow-visible text-dark" style="width: 10%">Long label text for the progress bar, set to a dark colorLong label text for the progress bar, set to a dark colorLong label text for the progress bar, set to a dark colorLong label text for the progress bar, set to a dark colorLong label text for the progress bar, set to a dark colorLong label text for the progress bar, set to a dark color</div>
</div>
```

### Background color

.progress-bar에 `.bg-success`를 추가하면 프로그레스바의 색상을 변경할 수 있습니다. 

```html
<div class="progress" role="progressbar" aria-label="Success example" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar bg-success" style="width: 25%"></div>
</div>
<div class="progress" role="progressbar" aria-label="Info example" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar bg-info" style="width: 50%"></div>
</div>
<div class="progress" role="progressbar" aria-label="Warning example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar bg-warning" style="width: 75%"></div>
</div>
<div class="progress" role="progressbar" aria-label="Danger example" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar bg-danger" style="width: 100%"></div>
</div>
```

### Multiple

`.progress-stacked`를 사용해 여러개의 프로그레스 바를 하나에 표현할 수 있습니다. 

```html
<div class="progress-stacked">

  <div class="progress" role="progressbar" aria-label="Segment one" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100" style="width: 15%">
    <div class="progress-bar"></div>
  </div>

  <div class="progress" role="progressbar" aria-label="Segment two" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="width: 30%">
    <div class="progress-bar bg-success"></div>
  </div>

  <div class="progress" role="progressbar" aria-label="Segment three" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" style="width: 20%">
    <div class="progress-bar bg-info"></div>
  </div>

</div>
```

### Stripe

`.progress-bar`에 `.progress-bar-striped`를 추가해 프로그레스 바의 배경색에 스트라이프를 적용할 수 있습니다. 

```html
<div class="progress" role="progressbar" aria-label="Default striped example" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar progress-bar-striped" style="width: 10%"></div>
</div>
<div class="progress" role="progressbar" aria-label="Success striped example" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar progress-bar-striped bg-success" style="width: 25%"></div>
</div>
<div class="progress" role="progressbar" aria-label="Info striped example" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar progress-bar-striped bg-info" style="width: 50%"></div>
</div>
<div class="progress" role="progressbar" aria-label="Warning striped example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar progress-bar-striped bg-warning" style="width: 75%"></div>
</div>
<div class="progress" role="progressbar" aria-label="Danger striped example" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar progress-bar-striped bg-danger" style="width: 100%"></div>
</div>
```

- 애니메이션 스트라이프
    
    .progress-bar에 .progress-bar-animated를 추가하면 css3 애니메이션으로 줄무늬를 오른쪽에서 왼쪽으로 애니메이션 시킬 수 있습니다. 
    
    ```html
    <div class="progress" role="progressbar" aria-label="Animated striped example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">
      <div class="progress-bar progress-bar-striped progress-bar-animated" style="width: 75%"></div>
    </div>
    ```
    
  </div>
</details>





