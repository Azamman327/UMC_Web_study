# HTML 소개(UMC 1주차 Web 강의내용)
## HTML ( Hyper Text Markup Language )
    
Hyper Text : 링크
    
Markup : mark를 태그라고 생각하고 , plain text 위에 의미를 부여하기 위한 것이다. html은 태그가 전부라고 할 수 있다.
    
Element : Opening tag + Content + Closing tag
    
정말 여러 종류의 태그가 있고, **MDN 사이트**를 이용해서 필요한 태그를 적절히 검색해 사용하면 된다. 공식 문서는 아니지만 공식 문서처럼 사용된다. 
    
[MDN Web Docs](https://developer.mozilla.org/ko/)

<br><br>

## h1-h6
html, css, js를 작성하면 바로 결과를 확인할 수 있는 **codepen**을 간단한 작업을 할 때 사용한다. 
    
[codepen으로 이동](https://codepen.io/pen/)
    

주석 : ctrl + / 
    
- 1에서 6으로 갈수록 폰트 크기가 작아진다.
- h1은 주로 제목, 나머지는 부제나 가제에 사용한다.
- h1은 전체 html 파일에서 제목을 표시할 때 사용하므로 페이지당 한 번만 사용하는 것을 권장한다.
- h1부터 차례대로 쓰는 것을 권장한다. h2를 사용하고 h3를 사용하지 않고 h4를 사용하는 것을 권장하지 않는다. 에러를 띄우는 건 아니지만 MDN에서 권장하는 방식이므로 최대한 권장하며 사용하는 게 좋다.
- 글씨 크기로 인해서 헤딩 태그를 사용하는 것은 오해다. 글씨 크기나 굵기는 css로 적용하면 된다. h3를 원래는 사용해야 하는데, 글씨 크기가 너무 작아서 h2를 사용하는 일은 없어야 한다.

<br><br>

## div & semantic
- div는 division의 약자로, 주로 레이아웃을 구성할 때 사용한다.
- div는 가장 많이 남용되는 태그이다. 다른 태그를 쓸 때 보다 div태그를 사용할 때는 한 번 더 생각해보는 것이 좋다. div가 남발되면, 아무 의미 없이 막 쓴 태그라는 인식이 강하기 때문이다.
    
- div가 남발되는 것을 막고자 등장한 게 semantic태그이다.
                
- semantic태그는 기존의 div태그에 더 의미를 부여해주기 위해 나온 태그이다. 가운데 section에 contents를 표시한다. semantic태그들은 이 외에도 여러 가지가 있다.
- semantic태그가 나오기 전에는 모두 다 div태그로 표시 됐었다. 하지만 이들이 갖는 역할들이 다른데 div태그로 동일하게 감싸주면 안되겠다는 판단 하에 div에 각 영역별 역할을 더해서 semantic태그가 나왔다.
- 페이지마다 다 쓰는 것은 아니다. 페이지마다, 웹 사이트마다 레이아웃이 다 다르기 때문이다.

<br><br>

## video, img
- ul태그 : unordered list, 순서 없는 리스트 만들 때
- ol태그 : ordered list, 순서 있는 리스트 만들 때
- li태그 : list item, ul태그와 ol태그 속

- self-closing태그와 그렇지 않은 것들을 구별하는 팁이 있다.
- 처음과 끝이 명확한 내용을 쓸 때는 closing태그를 쓴다. img태그와 같이 처음과 끝이 없고, 그냥 이미지 하나를 삽입하는 경우 하나의 태그로 해결 가능하다.
- 다만 video태그는 source가 여러 개일 수 있기 때문에 closing태그를 쓴다.
- self-closing태그는 하나의 태그이고, contents도 사이에 없기 때문에 정보가 매우 부족해서 거의 항상 속성이 있다. 태그 맨 뒤에 /를 붙여주는 게 좋다.
  
- video태그 속 여러 속성을 추가할 수 있다. controls는 속성값 없이 속성명만 쓰는데, 재생버튼, 정지버튼, 음량조절버튼 등이 생긴다.
- img태그 속 여러 속성을 추가할 수 있다.
- 연습할 때 여러 이미지와 동영상이 필요할 텐데, 추천 사이트가 있다.
- 이미지 - 다운로드 or 우클릭, 이미지 주소 복사
       
[Beautiful Free Images & Pictures | Unsplash](https://unsplash.com/)
        
[동영상 다운로드](https://pixabay.com/ko/)

<br><br>

## 구조
vscode에서 live server 설치한다. live server는 작성한 html을 브라우저에서 확인가능하도록 해주는 기능이다. 우클릭 + open with live server 클릭하면 작성한 문서가 브라우저에서 나타난다. 
    
! + tab 하면 html 기본 구조 태그들이 나온다.
    
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
        
</body>
</html>
```
    
- <b>!DOCTYPE html</b> : 이 문서가 html 5버전을 사용하고 있다.
- <b>< lang="en"></b> : 이 문서가 html임을 나타낸다. 한 번 더 명시해준다.
- <b>head</b> : 우리가 확인하지 못하는 정보들을 담고 있다. 홈페이지에 대한 설명이나 검색 결과에 노출될 키워드 등이 들어간다.
- <b><title></b> : 웹 페이지의 제목, 이건 사용자가 볼 수 있다.
- <b>meta</b> : 제목 이외에 header에 필요한 모든 정보들을 담을 때 사용한다. charset은 html문서의 문자 인코딩을 설정하는 방식을 의미한다. "UTF-8"은 페이지에 쓰는 이모티콘을 포함해 거의 모든 나라 언어를 지원하기 때문에 많이 사용하는 인코딩 형식이다. 나머지는 써도 되고 안써도 된다.
- 우리가 배운 모든 태그들은 body 태그 내에 들어간다.
  
  
