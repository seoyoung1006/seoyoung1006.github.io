---
layout: post
title: ReactStyle
color: rgb(255, 111, 97)
tags: [os]
---
[Intro]
<p>
javascript에서 NodeJs를 이용해서 GraphQL을 하고, Front-end를 이용해 GraphQL하기
</p>
<div>
graphql-yoga => creat-react-app 명령어랑 비슷한데 GraphQL 프로젝트를 빠르게 시작할수 있게 한다. Backend 개발을 쉽게 만들어줌
</div>
<div>
nodemon => 내가 파일을 수정할때마다 서버를 재시작해준다.
</div>
<h3>GraphQL로 해결할 수 있는 문제</h3>
<ol>
<li>over-fetching</li>
<ul>
사용자가 요청한 영역의 정보보다 불필요하고 그 이상의 많은 정보를 받는것
</ul>
<li>under-fetching</li>
<ul>
Rest에서 하나를 완성하기위해서 많은 소스를 요청하는것(정보 3개 받을려고 3번 요청을 보냄)/테이블이 많이 나뉘어져 있으면 나뉘어진만큼 요청을 보내고 response를 받는다.
</ul>
</ol>
한 query에 정확하게 내가 원하는 정보만 받을 수 있다. 
<p>
Query는 Database에서 무언가를 요청하고 GraphQL언어로 내가 원하는 정보를 알려줄 수 있다. <br>
API로 조정하거나 모양을 바꾸어서 
</p>