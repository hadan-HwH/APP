﻿## Section 2: I Am Rich - How to Create Flutter Apps From Scratch



main.dart에서

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


