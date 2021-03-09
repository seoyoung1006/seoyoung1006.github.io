---
layout: post
title: ReactHooks_UseEffect1
color: rgb(255, 111, 97)
tags: [os]
---
<body>
<ul>
<li></li>
<li></li>
</ul>
componentWillUnMount,componentDidMount, componentWillUpdate
모든게 function으로 작동

useEffect의 dependency가 비어있으면 몇번에 상관없이 딱 한번만 실행된다.
useEffect로 부터 Function이 리턴된다=>componentWillUpdate

<h3>UseTitle</h3>
<p style="background : black"> 
const useTitle = (initialTitle) => {
   const [title, setTitle] = useState(initialTitle);
   const updateTitle = () => {
     const htmlTitle = document.querySelector("title");
     htmlTitle.innerText = title;
   };
   useEffect(updateTitle, [title]);
   return setTitle;
};
</p>

</body>