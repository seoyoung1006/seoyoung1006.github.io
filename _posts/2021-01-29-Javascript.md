---
layout: post
title: Javascript
color: rgb(255, 111, 97)
tags: [os]
---
<head>Javascript배우기 by 생활코딩
    <meta charset="utf-8">
    <style>
    h3 {
        border:1px dotted yellow;
        color: green;
    }
    </style>
</head>
<p>
웹페이지만 존재하는것이 아니라 사용자와 상호작용을 하기 위해서 만든 언어
</p>
<h3>HTML과 Javascript의 만남!</h3>
<ul>
<li>script태그<br>body태그안에 script태그를 만들어서 기능을 추가한다.</li>
<li>input태그<br>사용자와 상호작용할 수 있는 이름있는 버튼을 만들고 버튼을 눌렀을때 변화도 줄수있다.
<ul style="font-size:17px;">
<li>type으로 버튼,체크박스, 텍스트박스를 만들기</li>
<li>value로 type으로 만든것 이름 지정하기</li>
<li>event로 웹브라우저 위에서 일어나는 사건을 만든다.  onclick, onchanged, onkeydown..</li>
</ul>
<p style="font-size: 17px">ex)input type="botton" value="click" onclick="alert('again')"</p>
<li>document<br>document는 내가 사용하고 있는 문서를 가리키는 객체를 의미해서 뒤에 .write & .querytSelector & .script등등을 덧붙여 활용한다. 
<br style="font-size:17px; color:deepskyblue;">ex)가장대표적인 쉽고 흔한 것은 script태그 속에 document.write()를 적는 것이다. 이 기능은 내부에 숫자식을 적으면 계산이 된 값이 나오고 ''를 이용해서 글을 적으면 문자열로 인식이 되어서 그대로 글이 적힌다. </li>
<li>비교연산자</li>
<ul>
<li>===  //표기할때 같다는 기호를 3개 쓴다.</li>
<li>a&lt;b  //태그 표시가 <(악어입)이라서 코드로 나타낼떄에는 lt(less than의 약자)를 사용해서 표기한다.</li>
</ul>
<h3>console이용</h3>
<p>(mac)웹페이지에서 개발자용에서 웹 속성안에 있는 console에 원하는 값을 출력하는 코드를 붙여 놓으면 간단히 원하는 값만 출력할 수 있어서 개발하기 유용하다.</p>
<h3>조건문</h3>
<p style="color:gray; font:bold;">if (조건문) {<br>
      조건문이 참일 때 실행할 문장;<br>
    }else {  <br>
        조건문이 거짓일 때 실행할 문장;} 형식으로 적는다.</p>
<h3>배열</h3>
<p style="color:gray; font:bold;">var 변수명=['value1','value2'];로 배열을 만들수 있다. 
<ul>
<li>value1을 꺼내 적기위해 할 방법 = document.write(변수명[0]);</li>
value3값 추가 하는 방법 = 변수명.push('value3');</li>
key명에 들어있는 배열 개수 구하는 방법 = document.write(변수명.length);</li></ul>
</p>
<h3>반복문</h3>
<ul>
<li>while-무한 루프</li>
<p style="color:gray; font:bold;">횟수를 칭하는 변수를 0으로 둔다.<br>
while(횟수조건) {<br>
    조건이 참일때 반복할 문장;<br>
    한번 반복할때마다 변수에 1을 늘인다.<br>
}
<li>for-반복 횟수 알 때</li>
 <p style="color:gray; font:bold;">for(var key in 변수) { <br>
    반복할 문장
 }
<h3>Function</h3>
같은 작업을 반복할 경우 함수를 만들어서 그 작업이 들어가는 곳에는 함수명만 적어주면 되기때문에 코드의 길이를 줄이고 반복도 안할수 있다. 
<h3>객체(object)</h3>
<p>var 객체명 = { <br>
    객체 내부작업 명칭1: 안에 사용될 코드들{~},
    객체 내부작업 명칭2: 안에 사용될 코드들{~} <br>
}