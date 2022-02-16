# 작성한 코드
```
create table user (
    user_id varchar2(20) primary key, 
    user_pw varchar2(20),
    user_name varchar2(20),
    user_gender varchar2(20),
    user_email varchar2(50)
)
```
## 오류메시지
> 오류 보고 -<br>
> ORA-00903: 테이블명이 부적합합니다<br>
> 00903. 00000 -  "invalid table name"<br>
> *Cause:    <br>
> *Action:<br>

(첫 번째 열에서 오류가 난다.)

<br><br><br><br>

이것때문에 1시간 끌었다<br>
처음에는 권한 설정이 문제인 건가 싶었는데 테이블 이름을 user로 해서 안된 것 같다.<br>
이름을 user에서 user_table로 바꾸었더니 해결이 되었다.<br>
sql에 user라는 키워드가 있던 거였을까......?
