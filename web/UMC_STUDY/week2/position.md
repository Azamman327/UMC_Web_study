# position
## static
```
.item:nth-child(2) {
  position: static;
}
```
- 정적 위치 지정 방식
- top, right, bottom, left에 영향을 받지 않음.

## relative
```
.item:nth-child(2) {
  position: relative;
}
```
- static을 기준으로 한 상대적 위치
- z-index : 어떤 아이템을 위로 보낼 것인지 설정
  + 레이어설정, 기본값 0
  + 양수의 경우, 숫자가 클수록 더 앞으로 보냄
  + 음수의 경우, 맨 뒤로 보냄

## absolute
```
.item:nth-child(2) {
  position: absolute;
}
```
- static이 아닌 다른 position값을 가진 부모를 기준으로 한다.
- position을 가진 부모가 없을 경우, root element인 body를 기준으로 한다.
- 원래 있던 html 문맥에서 나와 다른 레이어에서 작동한다.
- relative와 자주 같이 쓰인다.

## fixed
```
.item:nth-child(2) {
  position: fixed;
}
```
- absolute처럼 원래 문맥에서 나와 다른 태그들보다 위에 위치한다.
- 웹사이트의 상단 헤더처럼 스크롤을 내려도 그대로 있는 객체를 만들 때 사용(absolute와의 차이점)

## sticky
```
.item:nth-child(2) {
  top: 50px;
  left: 0px;
  position: absolute;
}
```
- fixed와 유사
- top, right, bottom, left등의 offset을 결정할 속성 필요
- 스크롤을 내릴 때 내가 정한 offset에 닿으면 닿은 순간부터 고정된다.
