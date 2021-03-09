---
layout: post
title: ReactHooks_UseEffect
color: rgb(255, 111, 97)
tags: [os]
---
<h3>useBeforeLeave</h3>-tab을 닫을 때 실행되는 함수
아무것도 return 하지 않는다. 
```
const useBeforeLeave = (onBefore) => {
  if (typeof onBefore !== "function") {
    return;
  }
  const handle = (event) => {
    const { clientY } = event;
    if (clientY <= 0) {
      onBefore();
    }

    console.log("leaving");
  };
  useEffect(() => {
    document.removeEventListener("mouseleave", handle);
  }, []);
};

<h3>useFadeIn</h3>
<p>

</p>