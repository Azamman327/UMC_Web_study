# DOM
<b>css처럼 js와 html이 연결되어야 한다.</b>

### getElementByTagName
```js
const $body = document.getElementsByTagName('body');
```
_변수 앞 $표시는 생략해도 무방_
- 태그 이름으로 접근
- 위 코드의 body는 유사배열
- 값에 접근할 때는 body[0]처럼 인덱스로 접근한다.
  + Tag는 여러개일 수 있기 때문이다.
<br><br>

### getElementByClassName
```js
const $body = document.getElementsByClassName('container');
```
- 클래스 이름으로 접근
- 값에 접근할 때는 container[0]처럼 인덱스로 접근한다.
  + Class는 여러개일 수 있기 때문이다.
<br><br>

### getElementById
```js
const $title = document.getElementsById('title');
```
- id로 접근
- console.log($title);로 인덱스 없이 바로 접근한다.
  + 같은 이름의 id는 하나밖에 없기 때문
<br><br>

- 위의 예시에서 document의 경우, 문서의 범위를 제한하는 역할(document는 문서 전체)
- 같은 원리로 특정한 구역으로 범위를 제한할 수 있다.
- ex)
```js
const $cityList = document.getElementById("cityList");
const $cities = $cityList.getElementsByTagName("li");

console.log($cities[index].innerHTML);
```
-li중 원하는 인덱스의 city를 콘솔창에 출력

### querySelectorAll
```js
const $cities = $cityList.querySelectorAll('li');
```
- cityList중 li에 해당하는 모든 요소들을 가져온다.
- foreach문 가능

### querySelector
```js
const $cities = $cityList.querySelector('li');
```
- cityList중 li에 해당하는 모든 요소들을 가져온다.
- foreach문 불가능(유사배열)
- 배열 형태로 바꿔주면 foreach문 사용 가능하다.
- 배열 형태로 바꾸어주는 방법
  + 1
    ```js
    const newCities = [...$cities];
    console.log(newCities);
    ```
  + 2. Array.from
    ```js
    const newCities = Array.from($cities);
    ```

### innerText
  + tag를 제외하고 변수(여기서는 body[0])에 있는 텍스트를 모두 나열해준다.
```js
console.log($body[0].innerText);
```
<br><br>

### innerHTML
  + html의 내용(태그 + 텍스트)를 문자열 형태로 보여준다.
```js
console.log($body[0].innerHTML);
```
<br><br>
<hr>

## js에서 스타일 변경하기 - 권장하지는 않음.
```js
$body[0].style.backgroundColor = 'teal';
```
- js에서는 -을 쓸 수 없음.(backgroundColor)
- body가 앞에서 TagName으로 선언되었으니 인덱스 지정
<br><br>

## js에서 element 추가하기
```js
const worstCity = document.createElement('ul');
const worstCityArr = ["Cairo", "London", "Risbon", "Sydney"];

worstCityArr.map((city) => {
  const worstCityItem = document.createElement("li");
  worstCityItem.innerText = city;
  console.log(worstCityItem);
  worstCity.appendChild(worstCityItem);   //ul에 넣기
});
```
이걸 html에 표시하려면
```js
worstCityDiv.appendChild(worstCity);  //이렇게 하거나

// const worstCityList = `
// <ul>
//   <li>Cairo</li>
//   <li>London</li>
//   <li>Risbon</li>
//    <li>Sydney</li>
// <ul>
// `  

// $cityDiv.insertAdjacentHTML('beforeend', worstCityList);  //이렇게 한다.(태그 자식 중 맨 뒤에 넣는다)
```
  + insertAdjacentHTML
    * beforebegin : element 앞에
    * afterbegin : element 안에 가장 첫번째 child
    * beforebegin : element 안에 가장 마지막 child
    * afterbegin : element 뒤에

### 클래스 추가하기 - classList.add()
```
worstCityDiv.classList.add("city");
```
- 클래스를 삭제하고 싶으면 worstCityDiv.classList.remove("city"); 하면 된다.

### 속성 추가하기 - setAttribute
```js
worstCity.setAttribute("name", "worstCity");
```
- name = "worstCity"라는 속성이 적용됨.
