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
2. [Customize](#1.-Customize)
  - Sass
  - Component
  - CSS variable 
3. [Layout](#1.-Layout)
  - Breakpoints
  - Containers
  - Grid System
  - Columns
  - Gutters
4. [Contents](#1.-Contents)
  - Reboot
  - Typography
  - Image
  - Table
5. [Forms](#1.-Forms)
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
