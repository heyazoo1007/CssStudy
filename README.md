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


## 1. Getting Start
<details>
<summary>1-1. Starter Template</summary>
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



















