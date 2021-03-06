# about_Backend
백엔드를 공부하며 중요한 것을 기록하는 저장소입니다.

# If else VS Swicth-case
### If else
- 조건문 체크 : 값의 범위나 조건(condition)을 체크한다.
- 이상적인 상황 : Boolean 결과값이 나오는 다양한 조건문들이 있을 때.
- 점프 테이블 : 점프 테이블을 만들지 않으며 모든 케이스는 런타임에 실행된다.
- 검색 타입 : 선형 검색
- 조건문 표현 : 여러 조건문들을 사용 가능
- 평가 : integer, character, pointer, floating-point, boolean
- 실행 순서 : if 실행 혹은 else 실행
- 기본 실행 : if조건문이 거짓이라면 else문의 코드가 실행된다.
- 값 : values are based on the constraint
- 사용 : 조건문이 true or false인지 판단하기 위해 사용됨
- 수정 : 중첩되어 있는 경우 수정하기 어렵다.

# MIME (Multipurpose Internet Mail Extensions)
- MIME이란? 간략히 파일 변환을 뜻함.
- 이메일과 함께 동봉할 파일을 텍스트 문자로 전환해서 이메일 시스템을 통해 전달하기 위해 개발되었기 때문에 이름이 Internet Mail Extension. 현재는 웹을 통해서 여러 형태의 파일을 전달하는데 쓰임.

- MIME 이전에는 UUEncode 방식. 
- 예전에는 텍스트파일을 주고 받는데 ASCII 표준을 따랐음. 하지만 바이너리 파일을 보내느 경우가 생김. 바이너리 파일을 기존의 시스템에서 문제 없이 전달하기 위해 텍스트 파일로 변환이 필요하게 됨. 이러한 텍스트 파일로 변환을 인코딩, 텍스트 파일을 바이너리 파일로 변환하는 과정을 디코딩 이라고 함. 
- 이러한 과정을 통해 텍스트만 전달할 수 있는 기존의 이메일 시스템에서도 여러 바이너리 파일을 주고 받을 수 있게 됨.
- MIME으로 인코딩 한 파일은 Content-type 정보를 파일의 앞부분에 담게 된다. 

## MIME 형식
- 파일의 종류/파일 포맷 (image/gif)
- 대부분 소문자로 쓰임s

## 개별 타입
- 특정 서브타입이 없는 텍스트 문서들은 text/plain으로 사용되어야 하고, 특정 서트바입이 없는 이진문서는 application/octetOstream이 사용되어야 함.
### text : 특정 문자셋으로 구성된 텍스트 정보나 스크립트 같은 formatted text 정보 전송에 사용.
- subtype ex) : text/plain, text/html, text/css, text/javascript
### image : 모든 종류의 이미지를 나타내며, 비디오는 포함되지 않음.
- subtype ex) : image/gif, image/png, image/jpeg, image/bmp, image/webp
### audio: 
- subtype ex) : audio/midi, audio/mpeg, audio/webm, audio/ogg, audio/wav
### video
- subtype ex) : video/webm, video/ogg
### application
- subtype ex) : application/octet-stream, application/pkcs12, application/vnd.mspowerpoint, application/xhtml+xml, application/xml, application/pdf


## 멀티 파트 타입
- 멀티파트 타입은 일반적으로 각기 다른 MIME 타입들로 개별적으로 나눌 수 있는 타입. 즉 합성된 문서를 나타내는 방법. 
- html forms의 post 메소드에 사용되는 "multipart/form-data"와 
전체 문서의 하위 집합만 전송하기 위한 206 Partial Content 상태 메시지와 함께 사용되는 multipart/byteranges를 제외하고는 http가 멀티 파트 문서를 다룰 수 있는 방법은 없음.  


- subtype ex) :  multipart/mixed, multipart/digest, multipart/alternative, multipart/related, multipart/report, multipart/signed, multipart/encrypted

## 주요 MIME 타입
### application/octet-stream 
- 이진타입을 위한 기본 값
- 잘 알려지지 않은 이진 파일을 의미. 브라우저는 보통 자동으로 실행하지 않거나 자동 실행할 지 묻기도 함. Content-Disposition 헤더가 값 attachment와 함께 설정되었고 'Save As' 파일을 제한하는지 여부에 따라 브라우저가 그것을 다루게 됨.
### text/plain 
- 텍스트 파일에 대한 기본값.
- 실제로 알려지지 않은 텍스트 파일일지라도 브라우저들은 그것을 디스플레이 할 수 있다고 가정함. 
### text/css 
- 웹페이지 내에서 보통 인터프리터 되어야 하는 모든 CSS 파일들은 text/css 파일이 되어야함. 
### text/html
- 모든 html 컨텐츠는 이 타입과 함께 서브되어야 함.

### multipart/form-data

- multipart/form-data is **one of the value of enctype attribute**, which is used in form element that have a file upload. multi-part means form data divides into multiple parts and send to server.

- html form의 내용을 전송 시 사용. 멀티 파트 문서 형식으로 경계가 구분되어지는 다른 파트들로 구성됨. 각 파트는 그 자체로 개체이며 자신만의 HTTP 헤더를 가짐. 파일 업로드 필드를 위한 헤더로 Content-Dispositionk 그리고 가장 일반적인 것 으로 Content-Type을 가짐.

### enctype attribute ?
- 이 속성은 \<form\>요소의 method 속성값이 post인 경우에만 사용.
- enctype(인코드 타입) 속성은 서버로 데이터가 보내지기 전에 어떻게 인코딩이 되어야하는지 명시해주는 속성이다.
- 기본값은  "application/x-www-form-urlencoded". 공백은 "+" 로, 특수 문자는 아스키코드로 변환되어 인코딩된다.  
<br/> --> (key=value&key=value 형태로 전송되며, 영숫자가 아닌 문자는 퍼센트 기호 및 문자의 ASCII 코드를 나타내는 두 개의 16 진수로 변환됨. 우리가 전송하려는 데이터가 영숫자가 아닌 경우 3바이트로 표현하기 때문에 바이너리 파일을 전송할 경우 페이로드를 3배로 만들기에 무척 비효율적)
- "multipart/form-data". 모든 문자를 인코딩하지 않음. 파일이나 이미지를 서버에 전송할 때 주로 사용.
<br/> --> (바이너리 데이터를 효율적으로 전송할 수 있으나 웹에서 많이 사용되는 텍스트로만 이루어진 POST 전송은 오히려 MIME 헤더가 추가되기 때문에 오버 헤드가 발생됨)
- "text/plain". 공백문자는 "+" 로 변환되지만, 나머지 문자는 모두 인코딩 되지 않음.
<br/><br/>

### Switch-case
- 조건문 체크 : single integer, 상수화된 값, 스트링 객체를 테스트
- 이상적인 상황 : 고정된 데이터 값이 있는 경우
- 점프 테이블 : 컴파일 시 컴프테이블 생성, 선택된 케이스만 런타임 시 실행됨.
- 검색 타입 : 이진 검색
- 조건문 표현 : 하나의 표현만 사용 가능
- 평가 : character, integer. 
- 실행 순서 :각 케이스에서 break 문을 만나거나 구문이 끝나야 다음 구문을 실행한다. 
- 기본 실행 : 모든 케이스를 검사 하고도 맞는 케이스가 없을 때 기본 구문을 실행한다.
- 값 : values are based on user choice.
- 사용 : 같은 변수 중 여러 값들을 판단할 때 사용.
- 사용 : 수정하기 용이하다.
<br/><br/>

# DTO vs JSON (+직렬화)
### DTO (Data Transfer Object)
- 데이터를 한 번에 전달하기 위해 만든 클래스가 DTO. 
- 객체로 정리된 DTO일 경우 외부 통신을 하기 위한 직렬화에 대한 로직은 내부에 캡슐화하여 가지고 있을 수 있기 때문에 코드가 명확해진다.
### JSON
- json은 직렬화의 한 종류. 외부와 통신하기 위해 dto를 json으로 직렬화하여 사용할 수 있다.
## Serialization(직렬화)
- 메모리를 디스크에 저장하거나 네트워크 통신에 사용하기 위한 형식으로 변환하는 것. 
### 직렬화 필요 이유.
### 값 형식 데이터 vs 참조 형식 데이터
- 값 형식 -> 기본형 데이터들은 스택에 메모리가 쌓이고 직접 접근이 가능.
- 참조 형식 -> 힙에 메모리가 할당되고 스택에서는 힙 메모리를 참조함.
- 디스크에 저장하거나 통신할 때는 값 형식 데이터만 가능 !!
### 직렬화의 결과
- 직렬화를 하게 되면 각 주소값들이 가지는 데이터를 모두 끌어모아 값 형식 데이터로 변환.  
<br/><br/>

# 정규식 (생활코딩)
### case 1 기본패턴
- 특정 문자 
- 대소문자 구별

### case 2 \(" "\)
- 화이트 스페이스 구별
- 스페이스, 탭, 뉴 라인

### case 3 (^, &)
- ^ , &
- ^패턴 -> 패턴으로 시작되는 텍스트 선택.
- 패턴& -> 패턴으로 끝나는 텍스트 선택.

### case 4 (이스케이프 문자)
- \
- \$ -> "$"를 찾게 됨
- ^\$ -> 문자열의 시작에서 "$"을 찾음

### case 5, 6 (.)
- . : Point(.) matches any character
- 점(Point)을 문자로 사용하려면 이프케이프 문자를 반드시 사용.

### case 7 (\[\]) - square bracket
- \[\] -> \[\]안의 있는 문자 중, 한 문자로 보고 찾음.

### case 8 \[-\]
- 문자들의 범위를 특정할 때 사용. (알파벳, 숫자 순)

### case 9 \[^\]
- ^가 대괄호 안에 있으면 범위 내의 문자를 제외하고 선택 -> case1과 전혀 다른 개념. 

### subpattern ( | | )
- |로 구별되는 단어들을 묶어서 찾음. 

### quantifiers (수량자 "\*", "\+", "?")
- 패턴이 몇번 등장할 수 있는지 정해줌. 
- * -> \* 앞에 등장하는 패턴이 0개 ~ 여러개.
- + -> \+ 앞에 등장하는 패턴이 1개 ~ 여러개
- ? -> ? 앞에 등장하는 패턴이 0개 ~ 1개. 

### quantifiers (수량자 "{}")
- 원하는 수량을 지정할 수 있음.
- ex) {1,3} -> 1개 이상 3개 이하 선택
- ex) {3,} -> 3개 이상

### 수량자 + "?" -> 1. 최소 수량 선택
- 수량자 뒤에 ? 가 붙으면 수량자가 가질 수 있는 수 중 가장 적은 수 선택. 
- ex) r.\*\? -> \* 뒤에 ?가 붙어서 0개가 선택됨. r의에 어떤 것이든 0개를 선택-> r만 선택 

### 수량자 + "?" -> 1. lazy 선택자
- lazy하게 선택해줌. 

### 경계 ("\w", "\W", "\d", "\D", "\b", "\B", "\A", "\Z")
- \w -> 단어(알파벳, 숫자, 언더라인)를 선택
- \W -> 단어가 아닌 것을 선택
- \d -> 숫자들을 선택
- \D -> 숫자가 아닌 것을 선택
- \b -> 단어의 앞뒤 경계를 선택 
- \B -> 단어의 경계가 아닌 것을 선택 
- \A -> 맨 앞의 경계(멀티라인X)-cf) ^(멀티라인O)
- \Z -> 맨 뒤의 경계(멀티라인X)-cf) &(멀티라인O)

### assertions "(?=<pattern>)"
- 선택한 문자열에서 패턴을 제외 (선택하는데는 영향을 준다)

### 플래그를 사용한 고급검색
- var re = /pattern/flags;
### g 
- 전역 검색
### i
- 대소문자 구분없는 검색
### m
- 다중행 검색
### s
- .에 개행문자도 매칭
### u
- 유니코드; 패턴을 유니코드 코드 포인트의 나열로 취급
### y
- "sticky" 검색을 수행. 
- 문자열의 현재 위치부터 검색을 수행. 
  

<br/><br/>
# View를 분리하는 이유
- 외부의 함수를 그대로 사용하는 경우, 함수의 반환값이나 사용방식이 달라지면 뷰에서 해당 함수를 사용한 모든 위치를 찾아서 변경해야 한다.  이렇게 생성된 html을 다른 곳에서 사용하기도 쉽지 않다. 이 파일을 다른 파일에서 불러오게 되면 파일 내 포함된 모든 기능을 호출하게 됨. 이 파일을 다시 사용하더라도 작성했을 당시의 의도를 바꾸기 어렵다.
- 부가 분리되어 있어도 뷰에서 전역변수에 접근하는 방식으로 데이터에 접근하면 어떤 변수를 사용하고 있는지 뷰 코드를 들여다보기 전까지 알기 어렵다. 이런 방식으로 뷰를 재사용하면 해당 파일을 include하기 전에 어떤 변수를 php 내부에서 사용하고 있는지 살펴본 후, 모두 전역 변수로 선언한 다음 include를 수행해야 한다.
