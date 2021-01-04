# Section 3: I Am Rich - How to Create Flutter Apps From Scratch

 ## Structure
 - runApp()
> 실행문
 - myApp()
 > class로 따로 정의를 해야한다.
 - Material app()
 > style과 concept가 기본적으로 주어진다
 - flutter는 상속관계를 기반으로 만들어진다.
> ex. Material App 내부에 Text를 넣으면 기본적으로 top-left에 위치한다. 가운데로 위치시키기 위해서는 Center를 Text의 부모로 추가해준다.

### Widget
 - home: 
> 앱의 default route
 - Scaffold() 
> 앱의 상단, 중간, 하단, 버튼 등 골격을 지원
 -  body: 
> 가운데 영역
 - appBar: 
> 상단바
 - child: 
 > 자식 클래스임을 푯
 - Center
> 가운데 정렬
- Text('   ')
 - title: 
 - backgroundcolor:
> backgroundcolor: Colors.색깔[숫자]
 - Image:
	 - AssetImage()
		 > 로컬 파일
	 - NetworkImageL()
		> url

### 구현
In 'main.dart'

    void main() {  
	  runApp(  
	    MaterialApp(  
	      home: Scaffold(  
	        backgroundColor: Colors.lightGreen[800],  
		  appBar: AppBar(  
			title: Center(child: Text('새해 복 많이 받으세요!'),),  
			backgroundColor: Colors.blueGrey[400],  
	  ),  
		  body: Image(  
			image: NetworkImage(  
              'https://blog.kakaocdn.net/dn/mde3Q/btqRVp2oJrY/ASy5N86oZdvoPCXKAdNtA1/img.gif'),  
			),  
		),  	
		),  
	  );  

 Image <새해복 앱>
![enter image description here](https://ifh.cc/g/9ypIrY.jpg)
### Etc
- '=>'를 ' {  }'로 대체 가능하다.
- ()뒤에 꼭 ','를 붙이는 습관이 좋다. Reformat Code하면 자동으로 줄이 바뀌고 깔끔해진다.
- 주석은 '//'로, yaml에서는 '#'으로 처리한다.

## 이미지 삽입
 1. 맨 위 폴더에 'images'라는 폴더를 만든다.
 2.  'pubspec.yaml'의 assets 부분의 주석처리를 지워준다. 
 3. assets에 사용하는 이미지의 경로를 적는다. 

	    flutter:  
		  uses-material-design: true  
		  assets:  
		    - images/icon.png

## Icon 바꾸기
1. app Icon generator에서 이미지 파일 변환 후 저장

### Android
2.  [app] - [src] - [main] - [res]에서 'mipmap-hdpi' 파일 삭제하고 1번의 안드로이드 파일 안의 내용 넣기

### IOS
2. [Runner] - [Assets.xcassets] 파일 삭제하고 1번의 ios 파일 안의 내용 넣기

### 둥근 아이콘
[src] - [main] - [res] 우클릭 -> New -> ImageAsset -> path에서 원하는 사진 넣고 resize로 사이즈 조성 -> next -> finish
