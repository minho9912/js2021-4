# 최민호 [201840135]

## [06월 01일]

> 오늘 배운 내용 요약<br>

#### 14-14 애니메이션

```jsx
$(document).ready(function () {
  $(".box").click(function () {
    $(this).animate(
      {
        left: 1000,
      },
      1000
    );
  });
});
```

#### 14-13 이벤트 제거

```jsx
$(document).ready(function () {
  var handler = function (event) {
    $("<h1></h1>").text($(this).text()).click(handler).appendTo("body");
    $(this).off();
  };
  $("h1").on("click", handler);
});
```

#### 14-12 이벤트 간접 연결

```jsx
$(document).ready(function () {
  //body 태그에 h1 태그의 click 이벤트 위임
  $("body").on("click", "h1", function (event) {
    //h1태그 생성후 바디에추가
    $("<h1></h1").text($(this).text()).appendTo("body");
  });
});
```

#### 14-11 이벤트 직접 연결

```jsx
$(document).ready(function () {
  //h1태그에 click이벤트를 연결
  $("h1").on("click", function (event) {
    //이벤트를 발생시킨 문서 객체의 문자를 추출
    var text = $(this).text();
    alert(text);
  });
});
```

#### 14-10 제이쿼리를 사용한 문서 객체 생성

```jsx
$(document).ready(function () {
  $("<h1></h1>").text("안녕하세요").attr("data-test", "test").css({ backgroundColor: "red", color: "white" }).appendTo("body");
});
```

#### 14-9 jQuery를 사용한 속성 조작

```jsx
    $(document).ready(function () {
       $("img").each(function (index, element) {
  $(this).attr("src", "http://placehold.it/" + (index + 1) * 100 + "x100");
 });});
    </script>
   <p class="text-1">test1</p>
   <p class="text-2">test2</p>
  <p class="text-3">test3</p>
   <p class="text-4">test4</p>
  <img src="" alt="" />
  <img src="" alt="" />
  <img src="" alt="" />
```

#### 14-8 스타일 조작

```jsx
$(document).ready(function () {
  for (var i = 0; i < 256; i++) {
    $("<div></div>")
      .css({
        height: 2,
        background: "rgb(" + i + "," + i + "," + i + ")",
      })
      .appendTo("body");
  }
});
```

#### 14-7 text()메소드, html()메소드의 set형태

```jsx
$(document).ready(function () {
  $(".text-1").text("<h1>text() 메소드</h1>");
  $(".text-2").html("<h1>html() 메소드</h1>");
});
```

#### 14-6 text,html메소드

```jsx
$(document).ready(function () {
  alert($("h1").text());
  alert($("h1").html());
});
```

#### 예제 14-5 문서 객체 반복

```jsx
$(document).ready(function () {
  $("h1").each(function (index, element) {
    // $(this).css("backgroundColor", "blue");
    $("h1:even").css("backgroundColor", "red");
  });
});
```

```jsx
$(document).ready(function () {
$("h1").each(function (index, element) {
 if (index % 2 == 1) {     $(this).css("backgroundColor", "blue");
}
});
);
```

#### 예제 14-4 문서 객체 반복

```jsx
$(document).ready(function () {
  let $headers = $("h1");
  for (let i = 0; i < $headers.length; i++) {
    if (i % 2 == 1) {
      let domElement = $headers.get(i);
      $(domElement).css("backgroundColor", "red");
    }
  }
});
```

#### 14장 $(document).ready()

```jsx
해당 코드는 문서 객체의 생성 완료 시점을 잡는 이벤트 연결이다.
```

#### 12장 navigator 객체

```jsx
appCodeName; // 웹 브라우저의 코드 이름
appName; // 웹 브라우저의 이름
appVersion; // 웹 브라우저 버전
platform; // 시스템 환경
```

#### 12장 location,history객체

```jsx
href; // 주소
host; // 호스트이름,포트번호
hostname; // 호스트 이름
port; // 포트번호
search; // 요청 매개 변수의값
protocol; // 프로토콜 종류
```

#### 12장 screen 객체

```jsx
width; // 화면너비
height; // 화면높이
availWidth; // 실제 너비
availHeight; // 실제 높이
```

#### 12장 window객체

```jsx
alert("메시지"); //경고창출력
prompt("메시지"); // 프롬포트출력
```

#### 12장 forEach

```jsx
최신버전;
const array = [1, 2, 3, 4, 5];
array.forEach((i, idx) => {
  console.log(`${i}: ${idx}`);
});
익스플로러;
var array = [1, 2, 3, 4, 5];
for (var i = 0; i < array.length; i++) {
  var index = i;
  var item = array[i];
  console.log(item + " : " + index);
}
```

#### 12장 for of 반복문

```jsx
최신버전;
const array = ["가", "나", "다"];
for (let item of array) {
  console.log(item);
}
익스플로러;
var array2 = ["가", "나", "다"];
for (var item in array2) {
  console.log(array2[item]);
}
```

#### 12장 화살표함수

```jsx
최신버전;
let fnc = () => {};
익스플로러;
let fnc = function () {};
```

#### 12장 템플릿문자열

```jsx
최신버전
let variable =273;
console.log(`변수의값은 ${variable}입니다.`);
익스플로러
console.log("변수의값:"+variable+"이다".);
```

#### 12장 let,const키워드

```jsx
최신버전;
let variable = 273;
const constant = "hello";
익스플로러;
var variableA = 273;
var constant = "hello";
```

## [05월 25일]

> 오늘 배운 내용 요약<br>

#### 11장 RESTful 웹 서비스 개요

<table border=1>
RESTful 웹서비스 구조
<tr>
<td>GET</td>
<td>컬렉션을 조회한다</td>
</tr>
<tr>
<td>POST</td>
<td>컬렉션에 새로운 데이터를 추가한다</td>
</tr>
<tr>
<td>PUT</td>
<td>컬렉션 전체를 한꺼번에 변경한다</td>
</tr>
<tr>
<td>DELETE</td>
<td>컬렉션 전체를 삭제한다</td>
</tr>
</table>

#### 예제 10-10 morgan 미들웨어

```jsx
const express = require("express");
const morgan = require("morgan");
const bodyParser = require("body-parser");

//서버 생성
const app = express();
app.use(express.static("public"));
app.use(morgan("combined"));
app.use(bodyParser.urlencoded({ extended: false }));

//request 이벤트 리스너 설정
app.get("/", (request, response) => {
  //html형식의 문자열 생성
  let output = "";
  output += '<form method="post">';
  output += '<input type="text" name="a">';
  output += '<input type="text" name="b">';
  output += '<input type="submit">';
  output += "</form>";
  //응답
  response.send(output);
});

app.post("/", (request, response) => {
  response.send(request.body);
});

//서버 실행
app.listen(52277, () => {
  console.log("Server running at http://127.0.0.1:52277");
});
```

#### 10-9 morgan 미들웨어

```jsx
const express = require("express");
const morgan = require("morgan");
//서버 생성
const app = express();
app.use(express.static("public"));
app.use(morgan("combined"));

//request 이벤트 리스너 설정
app.get("*", (request, response) => {
  response.send("명령 프롬포트를 확인해주세요!");
});
//서버 실행
app.listen(52275, () => {
  console.log("Server running at http://127.0.0.1:52275");
});
```

#### 10-8 정적 파일 제공

```jsx
const express = require("express");
const app = express();
app.use(express.static("public"));
//request 이벤트 리스너 설정
app.get("*", (request, response) => {
  response.send(404);
  response.send("해당경로에는 아무것도없습니다");
});
//서버 실행
app.listen(52274, () => {
  console.log("Server running at http://127.0.0.1:52274");
});
```

#### 예제 10-7 요청 매개 변수 추출

```jsx
const express = require("express");
const app = express();
//request 이벤트 리스너 설정
app.get("*", (request, response) => {
  console.log(request.query);
  response.send(requset.query);
});
app.listen(8096, () => {
  console.log("Server running at http://127.0.0.1:8096");
});
```

## 예제 10-6 리다이렉트

```jsx
const express = require("express");
const app = express();
//request 이벤트 리스너 설정
app.get("*", (request, response) => {
  response.redirect("http://hanbit.co.kr");
});
app.listen(8093, () => {
  console.log("Server running at http://127.0.0.1:8093");
});
```

#### 예제 10-5 상태 코드

```jsx
const express = require("express");
const app = express();
app.get("*", (request, response) => {
  response.status(404);
  response.send("해당 경로에는 아무것도 없습니다.");
});
app.listen(8091, () => {
  console.log("Server running at http://127.0.0.1:8091");
});
```

#### 예제 10-4 그림과 음악 파일 제공

```jsx
const express = require("express");
const fs = require("fs");
// 서버 생성
const app = express();
//request 이벤트 리스너 설정
app.get("/image", (request, response) => {
  fs.readFile("image.png", (error, data) => {
    //이미지 파일 제공
    response.type("image/png");
    response.send(data);
  });
});
app.get("/audio", (request, response) => {
  fs.readFile("audio.mp3", (error, data) => {
    //이미지 파일 제공
    response.type("audio/mpeg");
    response.send(data);
  });
});

//서버실행
app.listen(8092, () => {
  console.log("Server running at http://127.0.0.1:8092");
});
```

#### 예제 10-3 response 객체의 메소드

```jsx
const express = require("express");
const app = express();
app.get("*", (request, response) => {
  response.status(404);
  response.set("methodA", "ABCDE");
  response.set({
    methodB1: "FGHIJ",
    methodB2: "KLMNO",
  });
  response.send("내마음대로 본문확인");
});
app.listen(8091, () => {
  console.log("Server running at http://127.0.0.1:8091");
});
```

#### 예제 10-2 페이지 라우팅

```jsx
//모듈의 객체 생성
const express = require("express");
const app = express();
app.get("/page/:id", (request, response) => {
  const id = request.params.id;
  response.send(`<h1>${id} Page</h1>`);
});
app.listen(8090, () => {
  console.log("Server running at http://127.0.0.1:8090");
});
```

#### 예제 10-1 express

```jsx
const express = require("express");
const app = express();
app.use((Request, Response) => {
  Response.send("<h1>hello world</h1>");
});

app.listen(52273, () => {
  console.log("server running at http://127.0.0.1:52273");
});
```

## [05월 18일]

> 오늘 배운 내용 요약<br>

#### 예제 9-14 cheerio

> const request = require("request");<br>
> const cheerio = require("cheerio");<br> ><br>
> const url = "http://naver.com";<br> ><br>
> request(url, (error, response, body) => {<br>
> const $ = cheerio.load(body);<br>
> console.log($("strong.new").text());<br>
> });

#### 예제 9-13 request

> const request = require("request");<br>
> request("http://naver.com", (error, response, body) => {<br>
> console.log(body);<br>
> });

#### 예제 9-12 비동기코드예외처리

> const fs = require("fs"); <br>
> fs.readFileSync("none.txt", (error, file) => {<br>
> if (error) {<br>
> console.log("파일을 읽어 들이는데 문제가 발생했습니다.");<br>
> console.log(error);<br>
> } else {<br>
> console.log(file);<br>
> console.log(file.toString());<br>
> }<br>
> });

#### 예제 9-11 동기코드예외처리

> const fs = require("fs");<br>
> try {<br>
> const file = fs.readFileSync("none.txt");<br>
> console.log(file);<br>
> console.log(file.toString());<br>
> } catch (exception) {<br>
> console.log("파일을 읽어 들이는데 문제가 발생했습니다.");<br>
> console.log(exception);<br>
> }

#### 예제 9-10 파일쓰기 (비동기)

> const fs = require("fs");<br>
> fs.writeFileSync("output.txt", error => {<br>
> console.log("파일 쓰기 완료");<br>
> });

#### 예제 9-9 파일쓰기 (동기)

> const fs = require("fs");<br>
> fs.writeFileSync("output.txt", "안녕");<br>
> console.log("파일 쓰기 완료");

#### file system모듈

> const fs = require("fs");<br>
> const async = require("async");<br> ><br>
> async.parallel(<br> > [<br>
>
> > callback => {<br>
> > fs.readFile("a.txt", callback);<br>
> > },<br>
> > callback => {<br>
> > fs.readFile("b.txt", callback);<br>
> > },<br>
> > callback => {<br>
> > fs.readFile("c.txt", callback);<br>
> > },<br>
> > ],<br>
> > (error, results) => {<br>
> > console.log(results);<br>
> > }<br>
> > );

#### 예제 9-8 (file 비동기식)

> const fs = require("fs");<br> ><br>
> fs.readFile("test.txt", (error, file) => {<Br>
> console.log(file);<br>
> console.log(file.toString());<br>
> });

#### 예제 9-7 (file 동기식)

> const fs = require("fs");<br>
> const file = fs.readFileSync("test.txt");<br>
> console.log(file);<br>
> console.log(file.toString());

#### 예제 9-6( url )

> const foo = require("url");<br>
> console.log(foo.parse("http://naver.com"));

#### 예제 9-5( os모듈 )

> const foo = require("os");<br> ><br>
> console.log(foo.hostname());<br>
> console.log(foo.cpus());

#### 예제 9-4

> //이벤트 매개변수 exit
> process.on("exit", () => {<br>
> console.log("프로세스가 종료되었습니다.");<br>
> });<br>
> // uncaughtException 이벤트의 연결<br>
> process.on("uncaughtException", () => {<br>
> console.log("예외가 발생했습니다.");<br>
> });<br>
> // 예외를 강제로 발생시킴<br>
> error.error.error();

#### 예제 9-3

> //exit 이벤트의 연결<br>
> process.on("exit", code => {<br>
> console.log("프로세스가 종료되었습니다.");<br>
> console.log("About to exit with code: " + code);<br>
> });<br>
> // uncaughtException 이벤트의 연결<br>
> process.on("uncaughtException", err => {<br>
> console.log("예외가 발생했습니다.");<br>
> console.log("About to uncaughtException with code : " + err);<br>
> });<br>
> //예외를 강제로 발생시킴<br>
> error.error.error();

#### 예제 9-2

> console.log("- process.env: ", process.env);<br>
> console.log("- process.version: ", process.version);<br>
> console.log("- process.arch: ", process.arch);<br>
> console.log("- process.platform: ", process.platform);

#### 예제 9-1 (js파일 경로확인)

> console.log(**filename);<br>
> console.log(**dirname);

## [05월 11일]

> 오늘 배운 내용 요약<br>

#### TypeError 예외처리

> function callTherrTimes(callback) {<br>
> for (let i = 0; i < 3; i++) {<br>
> callback();<br>
> }<br>
> }<br>
> callTherrTimes(function () {<br>
> console.log("안녕하세요");<br>
> });

#### underscore.js

>    <script>
> let foo = [<br>
> {<br>
>  name: "고구마",<br>
> price: 1000,<br>
> id: "c",<br>
> },<br>
> {<br>
>  name: "감자",<br>
>  price: 500,<br>
>  id: "c",<br>
> },<br>
> {<br>
> name: "바나나",<br>
> price: 1500,<br>
> id: "c",<br>
> },<br>
> ];<br>
> const output = _.sortBy(foo, item => item.name);<br>
> console.log(output);
> </script>

#### 프로토타입에 메소드 추가

> String.prototype.contain = function (input) {<br>
> return this.indexOf(input) >= -1;<br>
> };<br>
> console.log("안녕하세요".contain("안녕"));<br>
> console.log("안녕하세요".contain("데굴데굴"));

#### 예제 7-10 (ECMA5)

> let foo2 = [1, 30, 40, 50, 100];<br>
> //forEach<br>
> foo2.forEach((item, index) => {<br>
> console.log(index + "-" + item);<br>
> });<br> <br>
> //map()<br>
> let bar = foo2.map((item, index) => {<br>
> return item;<br>
> });<br>
> console.log(bar);<br> <br>
> //filter()<br>
> let foobar = foo2.filter((item, index) => {<br>
> return item % 2 != 0;<br>
> });<br>
> console.log(foobar);

#### Array

> let foo3 = [1, 30, 40, 50, 100];<br>
> let foo = [<br>
>
> > {<br>
> > name: "고구마",<br>
> > price: 1000,<br>
> > },<br>
> > {<br>
> > name: "감자",<br>
> > price: 500,<br>
> > },<br>
> > {<br>
> > name: "바나나",<br>
> > price: 1500,<br>
> > },<br>
> > ];

#### 7-7 Date 객체 예제

> let now = new Date();<br>
> let before = new Date("December 9, 2020");<br>
> let interval = now.getTime() - before.getTime();<br>
> console.log(interval);<br>
> interval = Math.floor(interval / (1000 _ 60 _ 60 \* 24));<br>
> console.log(interval);

#### 7-6 Date 객체 예제

> let date = new Date();<br>
> console.log(date);<br>
> date.setFullYear(date.getFullYear() + 1);<br>
> ate.setMonth(date.getMonth() + 11);<br>
> date.setDate(date.getDate() + 3);<br>
> console.log(date);

#### 7-5 Date 객체

> let dateA = new Date();<br>
> console.log(dateA.getHours());<br>
> console.log(dateA);<br>
> let dateB = new Date(692281800000);<br>
> console.log(dateB);<br>
> let dateC = new Date("December 9, 1991 21:30:00");<br>
> console.log(dateC);<br>
> let dateD = new Date(1991, 12 - 1, 9, 21, 30, 0, 0);<br>
> console.log(dateD);

## [05월 04일]

> 오늘 배운 내용 요약<br>

#### 문자열 분해

> let string = '감자,고구마,바나나,사과';<br>
> let array = string.split(',');<br>
> console.log(array);

#### 문자열 포함

> let string3 = "안녕하세요, 좋은 아침입니다.";<br>
> if (string3.indexOf("아침") >= 0) {<br>
> console.log("좋은 아침이에요...!");<br>
> }

#### 잘못된 String 객체 메소드 사용

> let string = "abcedfg";<br>
> string.toUpperCase();<br>
> console.log(string);

#### 올바른 String 객체 메소드 사용

> let string = "abcedfg";<br>
> string = string.toUpperCase();<br>
> console.log(string);

#### String 객체 생성

> let stringFromLiteral = "안녕하세요";<br>
> let stringFromLiteral2 = new String("안녕하세요");

#### Number 생성자 함수의 속성

> let numberA = Number.MAX_VALUE;<br>
> let numberB = Number.MIN_VALUE + 22;<br>
> console.log(numberA);<br>
> console.log(numberB);

#### 생성자 함수에 속성과 메소드 추가

> function Constructor() {}<br>
> Constructor.property = 273;<br>
> Constructor.method = function () {};<br>
> console.log(Constructor.property);<br>
> console.log(Constructor.method);

#### Number 객체의 메소드

> let number = 273.5210332;<br>
> console.log(number.toFixed(1));<br>
> console.log(number.toFixed(4));

#### 프로토타입에 메소드 추가

> let primitiveNumber2 = 273;<br>
> Number.prototype.method = function () {<br>
> return "Primitive Method";<br>
> };<br>
> console.log(primitiveNumber2.method());

#### 기본자료형과 객체자료형의 메소드 추가

> let primitiveNumber = 273;<br>
> primitiveNumber.method = function () {<br>
> return "Primitive Method";<br>
> };<br>
> console.log(primitiveNumber.method());

#### 기본형과 객체 자료형의 메소드 사용

> let string2 = "과자|1500원";<br>
> console.log(string2.split("|"));<br>
> let string2 = new String("과자|1500원");<br>
> console.log(string2.split("|"));

#### 기본형과 객체 자료형의 차이

> let number = 273;<br>
> let string = "안녕하세요";<br>
> let boolean = true;<br>
> console.log(typeof number);<br>
> console.log(typeof string);<br>
> console.log(typeof boolean);

#### null 값과 자료형

> console.log(null);<br>
> console.log(typeof(null));

#### 프로토타입

> Product.prototype.print = function () {<br>
> console.log(pro3.name + "의 가격은" + pro3.price + "원입니다.);<br>
> };<br>
> let pro3 = new Product("바나나", 1200);<br>
> pro3.print();

#### 생성자 함수

> function Product(name, price) {<br>
> this.name = name;<br>
> this.price = price;<br>
> }<br>
> let pro2 = new Product("바나나", 1200);<br>
> console.log(pro2);

## [04월 27일]

> 오늘 배운 내용 요약<br>

#### 함수를 외부로 보낸 형태

> function printProduct(products) {<br>
> console.log(products.name + "의 가격은: " + products.price);<br>
> }

#### 객체 배열

> let products = [ <br>
>
> > { name: "바나나", price: 1200 },<br>
> > { name: "사과", price: 1300 },<br>
> > { name: "키위", price: 1400 },<br>
> > ];

#### 객체의 속성중 함수

> let number = 2223;<br>
> let object2 = {<br>
> number: 273,<br>
> string: "Rinlant",<br>
> array: [1, 2, 3, 4, 5],<br>
> ascz12: function () {<br>
> console.log(this.string + " " + this.number);<br>
> },<br>
> };

#### 객체의 속성

> let object = {<br>
> number: 273,<br>
> string: "Rinlant",<br>
> array: [1, 2, 3, 4, 5],<br>
> };

#### 반복문으로 배열 받아오기

> let array2 = ["사과1", "바나나1", "망고1", "딸기1"];<br>
> for (let arr123 in array2) {<br>
> console.log("array2: " + array2[arr123]);<br>
> }

#### 객체선언

> let product = {<br>
> 제품명: "7D 건조 망고",<br>
> 가격: "10000원",<br>
> 원산지: "대한민국",<br>
> };<br>
> console.log(product.가격);

#### 배열

> let array = ["사과", "바나나", "망고", "딸기"];<br>
> console.log(array[0]);

#### 익명함수와 화살표함수(this)

> (function () {<br>
> console.log(this);<br>
> })();<br>
> (() => {<br>
> console.log(this);<br>
> })();

#### 코드 5-20 (함수 덮어쓰기)

> ''객체에 선언되어있는 함수가 출력 우선순위가 더높다''<br>
> fooo = function () {<br>
> console.log("첫번째 함수");<br>
> };<br>
> function fooo() {<br>
> console.log("두번째 함수");<br>
> }

#### 코드 5-19 (함수 덮어쓰기)

> let fooo;<br>
> fooo = function () {<br>
> console.log("첫번째함수");<br>
> };<br>
> fooo = () => {<br>
> console.log("두번째함수");<br>
> };

#### 익명함수와 선언적함수

> let bar;<br>
> bar = 10;<br>
> bar = 20;<br>
> console.log(bar);

#### ClearInterval

> setTimeout(function () {<br>
> clearInterval(foo);<br>
> },3000)

#### 무명 함수

> let foo = setInterval(() => {<br>
> console.log("출력합니다.");<br>
> }, 1000);

## [04월 13일]

> 오늘 배운 내용 요약<br>

#### 콜백 타이머 함수

> setTimeout(function () {<br>
> console.log("1초가 지낫습니다.");<br>
> }, 1000);<br>
> let setset = setInterval(function () {<br>
> console.log("1초마다 호출");<br>
> }, 1000);<br>
> setTimeout(function () {<br>
> clearInterval(setset);<br>
> }, 3000);

#### 숫자 변환 함수

``

> let inputA = "52";<br>
> let inputB = "52.273";<br>
> let inputC = "1401동";<br> > <br>
> console.log(parseInt(inputA));<br> <br>
> console.log(parseInt(inputA));<br>
> console.log(parseInt(inputB));<br> <br>
> console.log(parseFloat(inputA));<br>
> console.log(parseFloat(inputB));<br> <br>
> console.log(parseInt(inputC));<br>
> console.log(parseFloat(inputC));

#### 콜백 함수

> function CallTenTimes(callback) {<br>
> for (let i = 0; i < 10; i++) {<br>
> callback();<br>
> }<br>
> }<br>
> CallTenTimes(function () {<br>
> console.log("함수 호출");<br>
> });

#### 함수 매개변수 초기화

> function print(name, count) {<br>
> console.log(`${name}(이)/가 ${count}개 있습니다.`);<br>
> }<br>
> print("사과", 10);

#### 매개 변수 리턴

> function sum(min, max) {<br>
> let output = 1;<br>
> for (let i = min; i <= max; i++) {<br>
> output \*= i;<br>
> }<br>
> return output;<br>
> }<br>
> console.log(sum(1, 10));

#### 리턴 없는 함수

> function print(x) {<br>
> console.log(`"${x} 라고 말했습니다."`);<br>
> }<br>
> print("안녕하세요");

#### 매개변수가 여러개인 함수

> function multiply(x, y) {<br>
> return x + y;<br>
> }

#### 함수의 기본형태

> function power(x) {<br>
> return x \* x;<br>
> }<br>
> console.log(power(10));

#### 화살표 함수

> let 함수 = () => {<br>
> console.log("첫번째줄1");<br>
> console.log("두번째줄2");<br>
> };

#### 선언적 함수

> function 함수() {<br>
> console.log("첫번째줄");<br>
> console.log("두번째줄");<br>
> }

#### 리터럴

> 변수 안에 들어 있는 상태가 아니라, 문자 그대로 자료를 나타내는 것<br>

#### 익명 함수

> let 함수 = function() {<br>
> console.log("함수의 첫번째 줄");<br>
> console.log("함수의 두번째 줄");<br>
> }

## [04월 06일]

> 오늘 배운 내용 요약<br>

#### 호이스팅

> let a = 1;<br>
> {<br>
> console.log(a);<br>
> let a = 2; // '해당블록에서 사용할 변수를 미리 확인해서 정리하는 작업'<br>
> }

#### 스코프

> 스코프 == 블록이다.<br>
> if (<표현식>){<br>
> '블록'<br>
> }<br>
> for(<조건식>){<br>
> '블록'<br>
> }<br>
> 블록 내부에 선언된 변수는 해당 변수 내부에서만 사용 가능.<br>
> 블록 내부에서 이름이 같아 상위 블록에 있는 변수의 이름을 가리는 것을 섀도잉 이라한다.

#### continue 문

> for (let i = 1; i < 10; i++) {<br>
> if (i % 2 === 0) {<br>
> continue;<br>
> }<br>
> console.log(i);<br>
> }

#### break 문

> let i = 0;<br>
> let array = [1, 31, 273, 57, 11, 22];<br>
> let output;<br>
> while (true) {<br>
> if (array[i] % 2 === 0) {<br>
> output = array[i];<br>
> break;<br>
> }<br>
> i++;<br>
> }<br>
> console.log("가장 먼저 발견환 짝수는 " + output + "입니다");

#### for 중첩 반복문

> let p = "";<br>
> for (let i = 0; i < 10; i++) {<br>
> for (let j = 0; j < i + 1; j++) {<br>
> p += "\*";<br>
> }<br>
> p += "\n";<br>
> }<br>
> console.log(p);

#### for of

> let array = [1, 2, 3, 4, 5, 6];<br>
> for (let i of array) {<br>
> console.log(i);<br>
> }

#### for in

> let array = ["사과", "배", "포도", "딸기"];<br>
> for (let i in array) {<br>
> console.log(`${i}번째 요소: ${array[i]}`);<br>
> }

#### for 역 배열 반복문

> let array = [1, 2, 3, 4, 5, 6];<br>
> for (let i = array.length - 1; i >= 0; i--) {<br>
> console.log(array[i]);<br>
> }

#### for 반복문 곱셈

> let output = 1;<br>
> for (let i = 1; i <= 20; i++) {<br>
> output \*= i;<br>
> }<br>
> console.log(output);

#### for 반복문

> let output = 0; <br>
> for(let i=0; i<=100; i++{<br>
>
> output += i;<br> ><br>
> }console.log(output)

## [03월 30일]

> 오늘 배운 내용 요약<br>

#### if else if 조건문

> if(조건){<br>
> } else if(조건){<br>
> } else if(조건){<br>
> }else{<br>
> }

#### Switch문

> switch(조건)&nbsp;&nbsp;{<br>

> &nbsp;case(조건):<br> > &nbsp;&nbsp;출력문<br> > &nbsp;&nbsp;break;<br> > &nbsp;&nbsp;default:<br> > &nbsp;&nbsp;출력문<br> > &nbsp;&nbsp;break;<br>
> }

#### 삼항연산자

> <불표현식> ? <참> : <거짓><br>
> ex: number % 2 == 0 ? true : false <br>

#### 짧은 초기화 조건문

> 삼항 연산자를 활용한 변수 초기화<br>
> ex: test = test || "초기화 합니다 1"<br>
> console.log(test);

#### 짧은 초기화 조건문

> 삼항 연산자를 활용한 변수 초기화<br>
> ex: test = test || "초기화 합니다 1"<br>
> console.log(test);

#### Node.js의 input<br>

const repl = require('repl');<br>

repl.start({<br>
prompt: "숫자 입력> ",<br>
eval: (command, context, filename,callback)=> {<br>
let number = Number(command);<br>
if(isNaN(number)){<br>
console.log("숫자아님"); <br>
}else{<br>
console.log("숫자맞음"); <br>
}<br>
callback();<br>
}<br>
})

#### 배열

> 여러 개의 자료를 한꺼번에 다룰 수 있는 자료형이다.<br>
> 대괄호 내부의 각 자료형은 쉼표(,) 로 구분한다.
> ex: let array = [52,23,'아침밥','점심밥',true,false]<br>
> console.log(array[0]);

#### while 반복문

> 가장 기본적인 반복문으로, if조건문과 달리 조건식이 참인 동안에는 계속 실행된다<br>
> 조건이 변하지 않으면 무한 반복 하므로 반드시 조건을 false로 만들 수 있는 문장을 포함해야한다.<br>
> ex: while(true){ <br>
> console.log("무한반복);<br>
> }

#### for 반복문

> 맨 먼저 초기식을 실행하고 조건식을 확인한다.<br>
> 조건식이 false면 반복문을 빠져나가고, true면 문장과 종결식을 차례로 실행해 다시<br>
> 조건식이 true인지 확인한다.<br>
> ex: let sum=0; <br>
> for(let i=0; i<=100; i++){<br>
> sum+=i;<br>
> }console.log(sum)<br>
> }

---

## [03월 23일]

> 오늘 배운 내용 요약<br>

- 탬플릿 문자열 : console.log('`52 + 273 = ${52 + 273}`'); // 52+273=325
- 불 : true,false // 비교연산자 : ==,!=,>,<,>=,<= // 논리연산자 : !,!!,&&<br>
  -- ex: let hours = new Date().getHours(); // console.log(hours < 3 || hours > 8);
- 변수 : let으로 선언 // let a = 10;
- 복합 대입 연산자 : +=,-=,/=,\*= // let a=0, // a=a+1,a=a-1;
- 증감 연산자 : 변수++,++변수,변수--,--변수
- 자료형 검사 : type of
- undefined 자료형 : let a; //선언만하기
- 강제 자료형 변환 : Number(),String(),Boolean()
- NaN: 무조건적으로 다름, 확일할 때는 isNaN()함수 활용
- Boolean() 함수
- 자동 자료형 변환 : // console.log(52+273),("52"+273)
- 불 자료형 자동 변환 // console.log(!!0),(!!"")
- 일치 연산자 : ===,!== // 자료형과 값이 같느냐/다르냐
- 상수 : const // 변하지 않는다 , 변수값.
- 조건문 : if,if else, else if , 중첩 조건문
  > 요약<br>
- 탬플릿 문자열 방식은 연산할 부분을 ${}안에 넣어주면 된다.
- 불 은 참과 거짓을 구별하는 것이고, ==,!= 등의 비교연산자나 !같은 논리연산자를 사용한다.
- 변수는 let으로 선언한다.
- 복합 대입 연산자, 증감 연산자, 자료형 검사
- undefined 자료형, 강제 자료형 변환, NaN, Boolean()함수
- 자동 자료형 변환은 콘솔 내부에서 연산 작업시 자동으로 형을 변환해주는 것이다.
- 일치 연산자는 값만 같느냐, 자료형과 값이 같으냐에 대한 물음 이다.
- 상수는 값이 변하지 않는 변수이다.
- 조건문은 if,else if,if else가 있는데, if안에 if, else안에 else도 가능하다.

---

## [03월 16일]

> 오늘 배운 내용 요약<br>

- JS 출력 결과 확인 방법 : 크롬 F12(개발자도구) - console 에서 명령문 입력 후 Enter 클릭
- node 버전 확인 방법 : cmd - 'node -v' 입력 후 Enter 클릭
- js 출력문 예시 : console.log('hello world') , alert('hello world')
- js 키워드 : break, else, switch, void, while, continue 등등
- 식별자 규칙<br>
  -- 키워드 사용 안됨, 특수문자는 \_와$만 허용, 숫자로 시작하면 안됨, 공백 입력 안됨
- 주석<br>
  -- 한 줄 주석 처리 : //주석 (ctrl+/)<br>
  -- 여러 줄 주석 처리 : /_ 주석 _/
- 자료형 - 숫자형 출력 (+,-,*,/)<br>
  -- console.log(5+3)or(5-3)or(5 *3)or(5/3)
- 자료형 - 문자열 출력<br>
  -- console.log("This is String")
- 이스케이프 형식 출력<br>
  --console.log("이름\t나이"),("안녕\n하세요"),("\\\\\\\\"),("출\\'력\\'")
- 문자열 연결 연산자 출력 예시<br>
  -- console.log("가나다"+"라마"+"바사아"+"자차카타"+"파하")<br>
  > 요약<br>
- 자바스크립트는 console.log() 를 사용하여 콘솔 창에서 원하는 결과를 출력할 수 있다.
- alert() 함수를 활용하여 팝업창으로도 결과를 출력시킬 수 있다.
- 자바스크립트에는 다양한 기능을 하는 키워드가 존재한다.
- 식별자를 만들 때에 지켜야 할 규칙이 있다.
- 표시하고 싶지 않거나, 부가적인 설명을 하는 부분은 주석 처리를 한다.
- 자료형에는 숫자형과 문자열이 있다.

---
