---
layout: post
title: ReactHooks_UseEffect2
color: rgb(255, 111, 97)
tags: [os]
---
useclick을 이용해서 useRef()를 만들고 같은 reference를 return해줌
그리고 주어진 reference에 title을 줌(h1으로)

useEffect에서 할일은 reference안에 element.current가 있는지 확인 하는것->만족되면 click 버튼 부여함
useEffect는 componentDidMount상태에 동작한다. 그래서 마지막에는 eventLister을 지워줘야 하낟

useEffect가 mount되었을때 call한다,update되었을때도 마찬가지

*
니가 function을 return받았을때, 그 function은 componentWillUpdate로부터 호출된것임
component가 mount되었을때 eventlistener가 호출 , dependency가 없기때문에 당연
dependency가 없으면 부를때마다 매번 반복되고 우리가 원하는것 아님 그러니까 dependency적어줘야함
