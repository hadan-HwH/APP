# Section 6: MiCard - How to Build Beautiful UIs with Flutter Widgets(1)

## Hot Reload
> 개발자가 직접 작성하는 'Write Code'와 코드가 기기에 반영되어 보여지는 'Test Code'가 있다. 코드를 작성하고 테스트하는 cycle을 통해서 개발을 하는데 이 cycle의 시간을 단축해주는 것이 'Hot Reload'이다.
> 
> 에러를 줄일 수 있고, 카운트 앱처럼 이미 실행하여 작동을 한 앱인 경우 리셋 없이 변동사항을 적용할 수 있다.


1. **stless**
- material앱 전체를을 return 에 넣고 runApp에는 MyApp( )을 넣는다.
-  build( )
> 새로운 버전의 위젯을 만들 때마다 콜이 가능하다.

2. console 옆 :zap:'Hot Reload'를 누르거나  Contrl + S 를 누르면 device에서 곧바로 볼 수 있다.
```
void main() {  
  runApp(  
    MyApp()  
  );  
}  

class MyApp extends StatelessWidget {  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      home: Scaffold(    
	  body: Container(  
              color: Colors.white,   
		)  
),),);}}
```
## Layout
### Container
> - div와 비슷하다.
> - child가 없으면 디바이스 화면 전체를 가리킨다. 
> - left top에 기본적으로 위치하는데 어떤 기기의 경우 상태창에 가려지거나 보이지 않는 경우가 있다.

![enter image description here](https://ifh.cc/g/rqH4Tf.jpg)
### SafeArea
> 위와같은 오류를 피하기 위해 SafeArea를 사용하여사용자가 사용하는 visible한 공간을 만들어준다.
- SafeArea 위젯 안에 child로 Container를 넣는다.
```
return MaterialApp(  
  home: Scaffold(  
    backgroundColor: Colors.black,  
    body: SafeArea(  
        child: Container(  
          color: Colors.white,  
	  child: Text('hello'),  
	  )  
	), 
    ),  
);
```
 ### SizedBox
> container 사이에 공간이 필요할 때 container 사이에 넣는다.
 
 ## UI
 - height: / width:
 > - **double.infinity**: 화면에서 가능한 최대 길이
 > 
 - margin: / padding:
> margin은 container의 외부 여백
> padding은 container 내부의 여백
> - **EdgeInsets.all( )**- 모든 방향에 여백
> - **EdgeInsets.symmetric(horizontal: x, vertical: y )**- 위아래, 좌우 대칭으로 여백
> - **EdgeInsets.fromLTRB( left, top, right, bottom)**- 각각 따로 여백주기
> - **EdgeInsets.only( )**- 원하는 방향만 여백주기


## Column & Row
> 여러 container를 배치할 때 편리하다.
> Column or Row (children: [...], )
> ... 안에는 여러개의 container가 들어가기 때문에 child가 아닌 children을 사용한다.
```
body: SafeArea(  
  child: Column(  
    children: [  
      Container(  
        margin: EdgeInsets.symmetric(),  
	color: Colors.white,
	)  
    ],  
  ),  
),
```
### in  Column & Row
> Column을 쓰면 vertical이 메인 방향(기준 방향)이 되고 horizontal이 cross 축이 된다., Row를 쓰면 horizontal이 메인 방향이 된다.
- mainAxisSize:
> 메인방향으로 축의 SIZE를 min으로 최소화 할 수 있고 max로 화면끝까지 늘릴 수 있다. cross 축은 container의 사이즈이다.
> ex. child: Column(mainAxisSize: MainAxisSize.min, )
```
child: Column(  
  mainAxisSize: MainAxisSize.max,  
  children: [  
    Container(  
      width: 100.0,  
  height: 100.0,  
  color: Colors.white,  
  )  
  ],
 ```
- verticalDirection:
> - verticalDirection: VerticalDirection.up- 처음부터 끝방향으로 container가 차곡차곡 정렬
> - verticalDirection: VerticalDirection.down- 끝부터 처음방향으로 container가 차곡차곡정렬
- mainAxisAlignment:
> - **mainAxisAlignment: MainAxisAlignment.start** - 처음에 위치
> - **mainAxisAlignment: MainAxisAlignment.end** - 끝에 위치
> - **mainAxisAlignment: MainAxisAlignment.center** - 가운데에 위치
> - **mainAxisAlignment: MainAxisAlignment.spaceEvenly**- container끼리 띄워서 가운데 위치(양 사이드에 여백 있음) 
> -**mainAxisAlignment: MainAxisAlignment.spaceBetween**- container끼리 띄워서 가운데 위치(양 사이드에 여백 없음) 

- crossAxisAlignment:
> - **crossAxisAlignment: CrossAxisAlignment.start**- cross 방향(column이면 row, row면 column)의 처음방향에 위치
> - **crossAxisAlignment: CrossAxisAlignment.end**- cross 방향의 끝방향에 위치
> - **crossAxisAlignment: CrossAxisAlignment.stretch**- cross 방향의 화면 최대로 늘어남


## 실습

```
import 'package:flutter/material.dart';  
  
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
          backgroundColor: Colors.teal,  
  body: SafeArea(  
            child: Row(  
              mainAxisAlignment: MainAxisAlignment.spaceBetween,  
  children: [  
                Container(  
                  width: 100.0,  
  height: double.infinity,  
  color: Colors.red,  
  ),  
  Column(  
                  mainAxisAlignment: MainAxisAlignment.center,  
  children: [  
                  Container(  
                    width: 100.0,  
  height: 100,  
  color: Colors.yellow,  
  ),  
  Container(  
                    width: 100.0,  
  height: 100,  
  color: Colors.greenAccent,  
  )  
                ],),  
  Container(  
                  width: 100.0,  
  height: double.infinity,  
  color: Colors.blue,  
  ),  
  ],  
  ),  
  ),  
  ),  
  ),  
  );  
  }  
}
```
![쉽다쉬워](https://ifh.cc/g/yuFufd.jpg)
