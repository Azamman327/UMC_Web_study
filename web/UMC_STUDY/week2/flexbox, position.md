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

- main axis의 방향을 설정
- flex-container에 적용
- 위 사진 차례로 다음과 같다
  + row : 가로로 설정(1, 2, 3....)
  + row-reverse : 가로로 반대로 설정(10, 9, 8....)
  + column : 세로로 설정(1, 2, 3....)
  + column-reverse : 세로로 반대로 설정(10, 9, 8....)
ex)
```
.flex-container {
  flex-direction: column;
}
```
