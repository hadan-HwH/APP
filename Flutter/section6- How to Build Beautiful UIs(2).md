# Section 6: MiCard - How to Build Beautiful UIs with Flutter Widgets(2)

> Tip: 위젯이 사용하는 docs를 알고 싶을 때, 해당 위젯에서 Control + Q 를 누르면 quick docs를 볼 수 있다.

## CircleAvatar
> 원모양 위젯
> 'radius:' 를 통해 사이즈 조절

## Font
### font 파일 넣기
1. new Directory로 font 폴더를 생성하고 font 파일을 넣는다.
2. [pubspec.yaml]에서 font 설정
> Tip: #으로 주석처리 되어있는 부분을 드래그하여  control + / 를 누르면 주석처리가 풀린다.
```
flutter:  
  uses-material-design: true 
  assets:  
    - images/selfi2.jpg  
  fonts:  
    - family: maruburi  
      fonts:  
        - asset: font\MaruBuri-Regular.otf  
    - family: nanumpen  
      fonts:  
        - asset: font\NanumPen.ttf
```
3. yaml 파일 상단의 pub get을 통해 적용해준다.

### TextStyle
- Text 위젯에서 TextStyle을 통해 폰트를 적용할 수 있다.
> - fontSize: - 글자 크기
> - color: Colors.*teal.shade50* - 글자색. 
> (shade- 색을 더 진하게, 연하게 조정할 수 있다)
> - fontWeight: FontWeight.*bold*- 글자 굵기
> - fontFamily: *'maruburi'*- 적용할 폰트
> - letterSpacing: - 자간
```
Text(  
  'hello',  
  style: TextStyle(  
    fontSize: 20,  
    color: Colors.teal.shade50,  
    fontWeight: FontWeight.bold,  
    fontFamily: 'maruburi'
    letterSpacing: 20,
  ),
```

## Icon
> flutter에서 기본적으로 제공하는 아이콘
> [Material Design Icon](https://material.io/resources/icons/) 참고
```
Icon(  
  Icons.*eighteen_mp*,  
  size: 100,  
  color: Colors.teal.shade100,  
)
```

## Card
> 모서리가 둥글고 shade가 있는 container라고 생각하면 된다.
> color를 넣지 않아도 기본적으로 흰색으로 되어있다.
> padding: 을 넣으면 오류가 뜬다. 대신 Padding을 child에 넣을  수 있다.

### ListTile
- leading: title 앞에 오는 위젯
- title: ListTile의 content 위젯
```
Card(  
    margin: EdgeInsets.symmetric(vertical: 10.0, horizontal: 25.0),  
    child: ListTile(  
      leading: Icon(  
        Icons.phone,  
	color: Colors.teal,  
  ),  
    title: Text(  
        'won1012@gmail.com',  
	style: TextStyle(  
          color: Colors.teal.shade900,  
	  fontFamily: 'Source Sans Pro',  
	  fontSize: 20.0,  
	 ),  
  ),  
  ),)
```

## Divider
> 가운데에 horizontal line을 만든다.
```
SizedBox(  
  height: 20.0,  
  width: 150.0,  
  child: Divider(  
    color: Colors.teal.shade100,  
  ),  
),
```

## 실습
```
void main() {  
  runApp(MyApp());  
}  
  
class MyApp extends StatelessWidget {  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      home: Padding(  
        padding: const EdgeInsets.all(8.0),  
  child: Scaffold(  
          backgroundColor: Colors.tealAccent.shade50,  
  body: SafeArea(  
            child: Column(  
              mainAxisAlignment: MainAxisAlignment.center,  
  children: [  
                CircleAvatar(  
                  radius: 100,  
  backgroundImage: AssetImage('images/selfi2.jpg'),  
  ),  
  SizedBox(  
                  height: 10,  
  ),  
  Text(  
                  'hello',  
  style: TextStyle(  
                    fontSize: 20,  
  color: Colors.teal.shade300,  
  fontWeight: FontWeight.bold,  
  fontFamily: 'maruburi',  
  letterSpacing: 20,  
  ),  
  ),  
  SizedBox(  
                  height: 20.0,  
  width: 150.0,  
  child: Divider(  
                    color: Colors.teal.shade100,  
  ),  
  ),  
  Card(  
                    margin: EdgeInsets.symmetric(vertical: 10.0, horizontal: 25.0),  
  child: ListTile(  
                      leading: Icon(  
                        Icons.phone,  
  color: Colors.teal,  
  ),  
  title: Text(  
                        '+82 010-1234-1234',  
  style: TextStyle(  
                          color: Colors.teal.shade900,  
  fontFamily: 'Source Sans Pro',  
  fontSize: 20.0,  
  ),  
  ),  
  )),  
  ],  
  ),  
  ),  
  ),  
  ),  
  );  
  }  
}
```
![enter image description here](https://ifh.cc/g/ViiAvH.jpg)
