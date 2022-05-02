# localstorage
기존의 페이지는 새로고침을 하면 정보가 날아갔는데, 정보가 안날아가도록 할 수 있다.
<br><br>
## 사용 방법
개발자도구 -> application -> local storage
<br><br>
## 저장
### setItem
> localstorage 정보를 저장할 때 사용하는 메소드
예시코드
```js
localStorage.setItem(key, value);

localStorage.setItem('name', 'booeung');
localStorage.setItem('age', 22);
```
- localStorage에 저장되는 값은 모두 문자열 형태이다.
<br><br>
## 값 가져오기
### getItem
```js
const result = localStorage.getItem('age');
```
- 문자열로 가져와진다.

```js
const travel = {
  destinations : ['paris'. 'sydny', 'taipei'],
  days: 100,
  mate: undefined,
  isAvailable: true;
}

localStorage.setItem('travel', travel); //object로 들어가게 된다(문자열X)
```
이때 사용하는 것이 JSON.stringify, JSON.parse

### JSON.stringify
```js
localStorage.setItem('travel', JSON.stringify(travel));
//travel객체를 문자열 형태로 변환하여 저장한다.
```
하지만 이런 식으로 저장을 하면 data.destinations과 같은 object.name형식으로 불러오기 어렵다.
- 다시 객체 형태로 변환시키기
```js
const data = JSON.parse(localStorage.getItem('travel'));
//data.destinations로 접근 가능
```

## 삭제하기
```js
//데이터 삭제
localStorage.removeItem('name');

//저장된 모든 데이터 삭제
localStorage.clear();
```
