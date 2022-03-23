# 2-4 flexbox
## flexbox와 axis
<img src="https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flex_terms.png" />
    
- flexbox는 flex-container과 flex-item으로 이루어져 있다.
- main axis와 cross axis
  * main axis : main이 되는 축
  * cross axis : main axis와 반대가 되는 축
  * 반드시 main axis가 가로방향인 것은 아니다. 바뀔 수 있음.
## flex-direction
<img src="https://funncy.github.io/assets/img/css/css-18.png" width="500px" height="300px"/>

- 주축의 방향을 설정
- flex-container에 적용한다.
- 위 사진 차례로 다음과 같다
  + row : 가로로 설정(왼->오)
  + row-reverse : 가로로 반대로 설정(오->왼)
  + column : 세로로 설정(위->아래)
  + column-reverse : 세로로 반대로 설정(아래->위)
ex)
```
.flex-container {
  flex-direction: column;
}
```

## justify-content
<img src="https://miro.medium.com/max/434/1*iigDGiNFBOUVJQ_07C1B2g.png" />

- main axis가 가로일 때 정렬 방법
- flex-container에 적용한다.
    + flex-start : 기본값, 시작점에 붙여서 정렬
    + flex-end : 끝점에 붙여서 정렬
    + center : 가운데 정렬
    + space-between : 양 옆 아이템은 양 끝쪽에 두고, 나머지 아이템 간 공백을 동일하게 배치
    + space-evenly : 양 옆과 아이템 사이의 공백을 일정하게 분배
    + space-around : space-evenly와 유사하지만, 양 끝 공백이 아이템 사이의 공백의 반절
- ex)코드 작성예시
```
.flex-container {
    justify-content: space-evenly;
}
```
- 주의할 점 : flex-container에 <b>padding</b>을 넣었다면 space-between을 해도 <b>양 끝 공백이 생길 수 있다.</b>
- *개발자 도구*로 어느 코드 때문에 이렇게 되었는지 확인 가능

## align-items
<img src="https://yohanproblogasset.s3.ap-northeast-2.amazonaws.com/images/flexbox/3.png" width="500px" height="600px"/>

- cross-axis를 정렬하는 속성
- flex-container에 적용한다.
    + flex-start : 맨 위 정렬
    + flex-end : 맨 밑 정렬
    + center : 가운데 배치
    + stretch : 기본값, 늘려서 화면 가득 채움
    + baseline : 텍스트를 기준으로 정렬
- 코드작성예시
```
.flex-container {
    align-items: flex-end;
}
```

## flexbox를 쓰는 이유
- 반응형 웹페이지에 최적화
- 화면 크기를 줄이면 item크기가 줄어들거나 레이아웃이 변경되도록 할 수 있음.

## flex-grow
- 고정 크기 말고, 화면 크기에 따라 객체를 얼마나 키울 것인가
- 남은 공백 크기를 flex-grow객체끼리 설정된 비율로 나누어가짐
- 기본값 0

## flex-shrink
- 화면을 줄일 때, 객체 크기를 얼마나 줄일 것인가
- 화면이 줄어들어 부족해진 공간을 flex-shrink 객체들이 지정된 비율만큼 부담하여 줄어든다.
- 기본값 1(따로 설정해주지 않아도 화면 줄어들 때 크기가 줄어든다는 뜻)

## flex-wrap
- 화면 크기를 줄여도 객체의 크기가 줄어들지 않도록 하는 속성
    + nowrap : 기본값, 화면 줄이면 객체 크기도 줄어든다.
    + wrap : 크기가 줄어들지 않음. 화면을 줄여서 공간이 줄어들면 객체가 작아지지 않고 다음 줄로 넘어감
    + wrap-reverse : wrap과 비슷하지만 끝점에서부터 정렬한다.

## align-content
<img src="https://codingapple.com/wp-content/uploads/2019/07/%EC%BA%A1%EC%B2%986-1.png" width="500px" height="600px"/>

- align-items와 justify-content를 합쳐놓은 형태
- <b>flex-wrap이 wrap일때만 적용 가능</b>
    + flex-start : 시작점에 모이도록 정렬
    + flex-end : 끝점에 모이도록 정렬
    + center : 가운데 모이도록
    + space-evenly : cross-axis의 방향인 수직 축에서 공백이 균일하게 배분됨.

## flexbox 연습 사이트
- flexbox froggy
(https://flexboxfroggy.com/#ko)
- css diner
(https://flukeout.github.io/)


