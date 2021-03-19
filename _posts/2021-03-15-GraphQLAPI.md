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
<div>
babel-node => 더 좋게 코드를 만들어준다. <br>
nodemon이 babel-node랑 index.js를 실행시켜줄것임.
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
GraphQL로 서버를 시작하는거는 서버를 가장 쉽게 시작할 수 있는 방법이다. graphql-yoga 사용은 진짜 서버를 간단하게 시작하게 해줌
schema나 다른것도 필요하지만
creat-react-app과 같은 것
+원하는 정보의 영역만 적으면 그 정보만 호출이 됨. 
</p>
<p>
schema
내가 사용자에게 보내거나 사용자로부터 받을 data에 대한 설명
+query는 단지 내가 정보를 받을때만 사용됨,mutation은 정보를 변형할때 사용(서버나 database,메모리에서 정보를 바꿀때)
</p>
<p>
resolver이 query문제 해결해줌
</p>
<p>
API를 이용한 프로젝트를 익히는 개발자들에게 아주 유용한 사이트
graphql-playground => GraphQL yoga안에 있는 것
+API안에 있는 기억하기 어려운 것들을 설명해주는 장점이 있음(나의 database를 이해할수 있는 도구를 가질수 있다)
</p>
<h2>조금 난이도 높은 GraphQL</h2>
<p>
user가 우리에게 준 id데이터를 어떻게 받을까?
GraphQL resolvers는 GraphQL서버에서 요청을 받는다. GraphQL서버가 Query나 Mutation의 정의를 발견하면, Resolver함수를 찾을 것이고, 그 함수를 실행 할 것임
=>즉, 무슨 일이 일어나는지 설명하는 파일 만들어서 설명하고, 이를 실행하는 파일 만들어서 실행하게끔 하면 된다. 
</p>
<p>
Mutation
Database의 상태가 변할때 사용되는 것
</p>
<p>
yts의 영화 리스트 코드 받아서 사용함.
Rest API를 GraphQL API로 감싸는 방법 배움
Django나 Express를 이용하면 뭐 해야할것도 많고 오래 걸리지만, GraphQL 이용하면 index,schema, resolvers, database
마지막에 node-fetch를 axios로 바꿔준다. 
</p>
