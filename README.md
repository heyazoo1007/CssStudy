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



















