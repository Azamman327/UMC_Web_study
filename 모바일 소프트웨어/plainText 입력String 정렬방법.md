plainText 초기 값은 왼쪽 정렬으로 되어있다.<br>
이거를 오른쪽 정렬을 하고 싶어서 .xml파일에서 gravity를 right로 설정해주었다.
```
android:gravity="right" 
```
이렇게 했는데도 안돼서 MainActivity.java에 다음과 같이 추가해주었더니 잘 적용이 되었다.
```
EditText content = new EditText(this);
...
content.setGravity(Gravity.RIGHT);
...
```
ActivityMain.xml과 MainActivity.java 둘 다 설정해야 적용이 되는 것 같다.

참고 사이트 : https://blog.daum.net/meatmall/675543
