# node.js 설치
- npm 설치 시 node_modules, package-lock.json 생성됨
- express 설치
- [공식 홈페이지](https://expressjs.com/ko/starter/installing.html)

## Hello World 예제 출력
```js
app.get('/', (req, res) => {
  res.send('Hello World!');
})
//req, res -> (request, response)
```
- 코드 내용 바뀌면 서버 재시작 필요

## 기본 라우팅
- C = Create
```js
app.post('/', function (req, res) {
  res.send('Got a POST request');
});
```
- R = Read
```js
app.get('/', function (req, res) {
  res.send('Hello World!');
});
```
- U = Update
```js
app.put('/user', function (req, res) {
  res.send('Got a PUT request at /user');
});
```
- D = Delete
```js
app.delete('/user', function (req, res) {
  res.send('Got a DELETE request at /user');
});
```

## nodemon 설치
- 코드 바뀔 때 일일이 재실행 필요 없도록
- npm install -g nodemon
- [nodemon 실행 오류 해결](https://velog.io/@kimy/VS-CODE-supervisor-nodemon-%EC%98%A4%EB%A5%98-ps1-%ED%8C%8C%EC%9D%BC%EC%9D%84-%EB%A1%9C%EB%93%9C%ED%95%A0-%EC%88%98-%EC%97%86%EC%8A%B5%EB%8B%88%EB%8B%A4)

## userId값 받기
```js
app.get("/users/:userId", (req, res) => {
  //res.json(users);  //응답 보내기
	// console.log(req.params.userId);  //내가 입력한 Id값 출력
  
	const user = users.find((user) => user.id === parseInt(req.params.userId));
  //res.json(user);

	if (!user) {
		res.status(404).send('요청한 userId를 찾을 수 없습니다') //상태코드(예외처리)
	}

	res.status(200).json(user);   //상태코드
});
```
- 사용자가 어떤 userId값을 입력할지 모름 -> 동적으로 이용되는 데이터는 앞에 : 붙임

### find 사용하기
- [find mdn](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

## post
```js
app.post("/users", (req,res) => {
	const newUser = req.body;

	if (Object.keys(newUser).length === 0) {
		res.status(400).send('user에 관한 정보를 입력해주세요');
	} else if (Object.keys(newUser).length < 4) {
		res.status(400).send('user를 추가하기 위해 필요한 정보를 모두 입력해주세요')
	} else {
    users.push({
      id: users[users.length - 1].id + 1,
      ...newUser, 
    });
	}

	res.json(users);
})
```
- ... : 안에 있는 객체들을 하나하나 복사하여 새로운 객체에 넣음

### postman
- api testing



