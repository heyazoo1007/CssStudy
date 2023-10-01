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
  <div markdown="1">
    Reboot는 `단일 파일에 있는 요소별 css 변경 모음`을 의미하고, Bootstrap을 초기에 빌드하는 우아하고 일관되며 간단한 기준선을 제공합니다. 

> 몇몇 요소들의 margin-top이 제거되거나, 기본 폰트가 변경되는 등 **요소들의 기본 설정 값이 변경된 내용**을 설명하고 있습니다.
> 

### 제목

제목크기는 <h1>-<h6> 요소로 설정할 수 있으며, 구체적인 특징은 다음과 같습니다.

margin-top : removed

margin-bottom : .5rem(8px)

line-height : tightened 

### 문단

모든 <p> 요소는 모두 `margin-top이 제거`되어있고, `margin-bottom은 1rem` 입니다. 

### 링크

링크는 기본 색상과 underline이 적용됩니다. :hover일 때 링크는 변경되며, :visited일 때는 변경되지 않습니다.

### 목록

모든 목록(`<ul>, <ol>, <dl>`)에는 `margin-top과 margin-bottom: 1rem`이 제거됩니다. 중첩된 목록에는 margin-bottom이 없습니다. 

`<ul>, <ol> 요소`에서 padding-left를 재설정했습니다.

### 인라인 코드

인라인 코드는 <code> 태그로 묶고, html 꺽쇠 괄호는 ‘<’로 작성하는 것이 아닌, `&lt;` 나 `&rt;` 로 표현해서 꺽쇠를 escape 해야합니다.

```html
For example, <code>&lt;section&gt;</code> should be wrapped as inline.

<!--output : For example, <section> should be wrapped as inline-->
```

### 코드 블록

코드가 여러 줄일 때는 <pre></pre> 태그를 사용합니다. 

올바른 렌더링을 위해 `꺽쇠 괄호를 이스케이프`를 잊으면 안됩니다.

<pre> 요소는 margin-top을 제거하고 margin-bottom에 rem 단위를 사용하도록 재설정 됩니다.
  </div>
</details>

<details>
<summary> 4-2. Typography </summary>
  <div markdown="1">
		
  </div>
</details>

<details>
<summary> 4-2. Typography </summary>
  <div markdown="1">
    ### 전역 설정

- 각 os 및 기기에 가장 적합한 기본 글꼴 스택을 사용합니다
- 일반적으로 `16px`의 기본 글꼴 크기를 제공하고, 브라우저 기본값은 사용자가 지정 가능합니다
- <body>에 적용된 타이포그래피는 `$font-family-base`, `$font-size-base`, `$line-height-base` 속성을 사용합니다
- `$link-color`를 통해 글로벌 링크 색상을 설정합니다
- `$body-bg`를 사용해 <body>에 background-color를 설정합니다

### 제목

- <h1>~<h6>
    
    <h1>~<h6>을 사용해 제목 크기를 지정할 수 있습니다. 
    
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

- <mark>, .mark : 참조 또는 표기 목적으로 표시, 강조된 텍스트
- <small>, .small : 부가적인 댓글과 작은 텍스트
- <s>, .text-decoration-line-through : 더이상 관련이 없거나 더이상 정확하지 않은 요소
- <u>, .text-decoration-underline : 텍스트가 아닌 주석이 있음을 나타내는 방식, 렌더링 되어야 하는 인라인 텍스트 범위를 나타냄

### 인용문

`<blockquote class=”blockquote”>`를 사용해 문서 내의 다른 소스에서 콘텐츠 블록을 `인용`합니다. 

- 인용 출처
    
    인용에 대한 출처는 <blockquote>를 `<figure>`로 감싸고, <figure> 내에 `<figcaption>` 또는 `.blockquote-footer 클래스`를 통해 표현할 수 있습니다.
    
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
    
    인용구를 정렬하려면 <figure> 태그에 `.text-*` 를 적용합니다. `center`, `end` 등을 설정할 수 있습니다. 
    

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
	  ### 이미지

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
<details>
<summary> 4-4. Table </summary>
  <div markdown="1">
	  `테이블의 opt-in 스타일`에 대한 문서와 예시에 대한 설명입니다.

<table>에 .table을 넣으면 우리의 선택 수정자 클래스 또는 커스텀 스타일로 확장할 수 있습니다. 

### 개요

Bootstrap에서 .table 기반 테이블을 표현하는 방법입니다. 

- 코드
    
    ```html
    <table class="table">
    
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">First</th>
          <th scope="col">Last</th>
          <th scope="col">Handle</th>
        </tr>
      </thead>
    
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>Mark</td>
          <td>Otto</td>
          <td>@mdo</td>
        </tr>
    
        <tr>
          <th scope="row">2</th>
          <td>Jacob</td>
          <td>Thornton</td>
          <td>@fat</td>
        </tr>
    
        <tr>
          <th scope="row">3</th>
          <td colspan="2">Larry the Bird</td>
          <td>@twitter</td>
        </tr>
      </tbody>
    
    </table>
    ```
    

### 테이블 강조

`.table-striped`를 사용해 <tbody> 내의 테이블 행에 줄무늬를 추가합니다.

```html
<table class="table table-striped"> ... </table>

<table class="table table-columns"> ... </table>

// 테이블 색상(dark), 테이블 줄무늬 패턴 추가
<table class="table table-dark table-striped"> ... </table>
<table class="table table-dark table-striped-columns"> ... </table>

// 테이블 색상(dark), 테이블 줄무늬 패턴 추가
<table class="table table-success table-striped"> ... </table>
<table class="table table-success table-striped-columns"> ... </table>
```

### hover를 할 수 있는 행

`.table-hover`를 추가해 <tbody> 내의 `테이블 행에 마우스 오버 상태를 활성화`합니다.

```html
<table class="table table-hover"></table>
<table class="table table-dark table-hover"></table>
<table class="table table-striped table-hover"></table>
```

### 활성화 테이블

`.table-active 클래스`를 추가해 테이블 행 또는 셀을 강조 표시합니다. 

### 테이블 테두리

- 테두리가 있는 테이블
    
    셀의 모든 면에 테두리가 있는 테이블을 만들려면 .table-border를 추가하면 됩니다.
    
    ```html
    <table class="table table-bordered"> ... </table>
    
    // 색상 변경
    <table class="table table-bordered border-primary"> ... </table>
    ```
    
- 테두리가 없는 테이블
    
    ```html
    <table class="table table-borderless"> ... </table>
    
    // 색상 변경
    <table class="table table-dark table-borderless"> ... </table>
    ```
    
- 얇은 테이블
    
    .table-sm을 추가해 모든 셀의 padding을 반으로 잘라 .table을 더 간결하게 만듭니다. 
    
    ```html
    // 기본 버전 
    <table class="table table-sm"> ... </table>
    
    // dark 버전
    <table class="table table-dark table-sm"> ... </table>
    ```
    

### 테이블 그룹 나누기

<thead>, <tbody> 또는 <tfoot>에 `.table-group-divider 클래스`를 추가하면 됩니다.

### 테이블 이름

`<caption>`은 테이블 이름과 같은 기능을 합니다. 테이블에 이름을 설정하면, 스크린 리더를 사용하는 사용자가 테이블을 찾고 그 내용을 이해하고 읽을 것인지 결정할 수 있도록 도와줍니다. 
	

```html
<table class="table table-sm">
  <caption>List of users</caption>
  <thead>
    ...
  </thead>
  <tbody>
    ...
  </tbody>
</table>

<!--테이블 이름을 상단에 올리기-->
<table class="table caption-top"> 
```

### 반응형 테이블

.table-responsive 클래스로 반응형 테이블을 만들면 테이블을 쉽게 가로로 스크롤할 수 있습니다. breakpoint에 따라 반응형 테이블을 설정할 수 있습니다. (`.table-responsive{-sm|-md|-lg|-xl|-xxl}`)

- `overflow-y: hidden`을 사용하면 테이블의 하단 또는 상단 가장자리를 벗어나는 콘텐츠를 잘라냅니다. 특히 드롭다운 메뉴 및 기타 서드 파티 위젯을 잘라낼 수 있습니다.
		
  </div>
</details>



















