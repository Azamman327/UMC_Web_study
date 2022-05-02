```js
const $div = document.querySelector('.container');
const $form = document.querySelector('form');
const $input = document.querySelector('input');
const $button = document.querySelector('button');


//1. 이벤트 핸들러
//target.이벤트이름 = 콜백함수
//동일한 대상의 동일한 이벤트가 있을 경우 마지막 것만 적용된다는 단점

$div.onclick = handleClick;

function handleClick () {
    console.log("clicked");
}

//2. addEventListener

$div.addEventListener('click', () => console.log('clicked'));
$div.addEventListener('click', () => alert('clicked'));

//3. removeEventListener
//2번처럼 익명함수를 넣을 수 없음. 
//함수가 분리된 형태여야지만 remove가능(1번의 형태)

$div.removeEventListener('click', handleClick);

//4. 현재 이벤트 정보 보기
$div.removeEventListener('click', handleClick);

function handleClick (event) {
    console.log(event);
}
//target속성을 가장 많이 봄.(이벤트가 일어난 부분 확인)
//ex) console.log(event.target);

//change이벤트
$input.addEventListener('change', handleChange);//사용자의 입력 값 받아오기

function handleChange(event) {
   console.log(evnet.target); 
}
//입력창 값을 받아오고 싶다면?
console.dir(evnet.target.value);


//form에 이벤트 추가
//1 새로고침 막기
$form.addEventListener('submit', handleSubmit);

function handleSubmit(event) {
    event.preventDefault();
    const inputValue = $input.value;//값 저장
    $input.value = '';//남아있는 값 삭제
}
```
