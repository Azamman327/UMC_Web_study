# UMC 2주차 스터디 정리(css기본)
## 2-1 <css 소개>
- css란?    
   외관의 기능, 못생긴 html에 디자인을 입히는 기능       
- html파일과 css파일 연결하는 방법
```html
<link rel="stylesheet" href="상대경로 or 절대경로">
```

## 2-2 <css 선택자>
- 태그, 클래스, 아이디가 있음.
- 태그
```
tagName {
  여기에 속성을 적어줍니다.
}
```
- class
```
.className {
  여기에 속성을 적어줍니다.
}
```
> 여러개의 요소에 같은 class 지정 가능
> 하나의 엘리먼트에 여러개의 class 지정 가능
> 여러개를 지정했을 경우, 더 뒤에 쓰여진 속성이 적용됨.
- id
```
#idName {
  여기에 속성을 적어줍니다.
}
```
> id의 경우, class와 다르게 단 하나의 요소에만 id를 사용할 수 있음.
> class처럼 하나의 요소가 여러개의 id를 갖는 것 또한 안됨.
    
<br>    
    
<b>선택자의 우선순위</b>    
> id가 가장 높고, class, 태그 순이다.    
> 범위가 작을수록 우선순위가 높다고 생각하면 된다.    
> 모든 우선순위를 무시하는 것은 !important이다.    
> !important는 속성값 바로 뒤에 적어주면 된다.    
```
background-color: pink !important
```

- 가상선택자
> 선택자 뒤에 :가상선택자 를 붙여 사용    
> <b>예시</b> : 마우스를 요소 위에 올렸을 때, 방문했던 링크일 때
```
div:hover {
  background-color: green;
}
```
_마우스를 div태그 객체 위에 올리면 배경색이 green으로 변합니다._    

- 이 외에 다른 가상 선택자들
  - active : 마우스로 클릭하고 있으면 실행
  - focus : input태그에서 사용 가능, 한 번 클릭하면 실행됨

## 2-3 properties
<b><html 요소의 분류></b>
- html 태그는 두 종류로 나뉜다.
   * block-element : 요소 크기에 상관 없이 한 줄을 통째로 차지하는 태그(ex)p, div, ul)
   * inline-element : 요소 크기만큼 차지하는 태그(ex)span, a, img)
- display 속성으로 block, inline을 설정해 줄 수 있다 => p태그를 inline-element처럼 가능
   * none : 공간 차지 X
   * inline : 요소 크기만큼 차지
   * block : 한 줄 차지    
<br><br>
   
<b><박스 모델(box model)></b><br><br>
<img src="https://user-images.githubusercontent.com/77380889/159197282-5606a84d-b9ea-48d4-a0c5-bcdf5dde8768.png" />
- padding : 테두리와 내용 사시의 간격
- border : 테두리
- margin : 테두리부터 다른 요소와의 간격
- 1, 2, 4 개의 값을 지정해 줄 수 있다.
   * 1개 : 상하좌우px값
   * 2개 : 첫번째 값은 상하, 두번째 값은 좌우
   * 4개 : top, right, bottom, left 순서
- border : 5px solid blue(두께, 스타일, 색상 지정 가능)
- border-top-width : 이런 시긍로 하면 하나의 테두리에만에도 설정 가능
- 모든 태그 선택자 : *
- box-sizing : content-box | border-box | initial | inherit
   * 무엇을 기준으로 box의 사이즈를 정할 것인가
   * content-box : content영역
   * border-box : 테두리 기준
   * initial : 기본값
   * inherit : 부모 요소의 속성값
   
- 태그도 포함관계 있음
   * ex)
   ```
   div span {
      ...
   }
   ```
   div 태그에 포함되어있는 span 태그를 가리킴
