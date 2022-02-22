## 1. 연결할 jsp파일, db파일 준비하기<br><br>
이건 미리 준비해야 한다.<br><br>

## 2. java파일이 필요하다.<br>
하나는 getter, setter가 들어가는 java파일(user.java)<br>
나머지 하나는 db와 jsp파일을 연결시키는 코드가 들어간다.(userDAO.java)<br><br>
<hr>
* user.java(getter, setter파일)<br>
getter, setter가 들어가는 파일은 db에 있는 필드값을 받는다.<br>
예를 들어 db에 id, password, animal의 필드가 있으면<br>
user.java파일에는 id, password, animal변수를 선언하고, getter와 setter를 작성해준다.<br> <br>
<hr>
* userDAO.java(db와 jsp연결)
<h4>1.Connection import하기</h4>
ctrl + shift + o로 java.sql.Connection를 import하거나 우클릭->Source->Organize Imports를 해준다.<br>
<h4>2.연결 위한 변수 선언, db연결</h4>
연결을 위한 변수, 질의문을 저장할 변수, 결과를 저장할 변수를 선언한다<br>

```
	private Connection conn;
	private PreparedStatement pstmt;
	private ResultSet rs;
```

<h4>생성자 만들기, db와 연결하기</h4><br>

```
	public UserDAO() {
		try {
			String dbURL = "jdbc:mysql://localhost:3306/db이름";
			String dbID = "db계정id";
			String dbPassword = "db계정비밀번호";
			Class.forName("com.mysql.jdbc.Driver");
			conn = DriverManager.getConnection(dbURL, dbID, dbPassword);
			System.out.println("연결되었습니다.");
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
```

생성자 안에 작성하여 로그인 시도 시 바로 실행될 수 있도록 한다.<br>
우선은 dbURL, dbID, dbPassword를 선언해준다.<br>
dbURL은 위와 같이 작성해준다. localhost:3306은 내 노트북 포트를 의미한다.<br>
dbID와 dbPassword에는 각각 연결할 db계정의 ID, 비밀번호를 적어준다.<br>
Class.forName("com.mysql.jdbc.Driver");<br>
conn = DriverManager.getConnection(dbURL, dbID, dbPassword);로 해당 db와 연결할 수 있다.<br>
<br><hr>
이 글의 코드는 웹페이지의 login기능을 구현하기 위해 작성한 파일이지만<br>
db가 제대로 연결되었는지 확인하고 싶다면 새로운 jsp파일에서 실행시켜보는 방법이 있다.<br>
실행시 디버그창에 "연결되었습니다." 메시지가 뜨면 정상적으로 연결이 된 것이다.<br>

*유튜브 동빈나 채널의 "jsp 게시판 만들기 강좌"를 참고하였습니다.
