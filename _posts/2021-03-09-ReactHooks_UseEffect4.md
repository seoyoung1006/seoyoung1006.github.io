---
layout: post
title: ReactHooks_UseEffect4
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
```

<h3>useFadeIn</h3>

```
const useFadeIn = (duration = 1, delay = 0) => {
  if(typeof duration !== "number" || typeof delay !== "number") {
    return;
  }
  const element = useRef();
  useEffect(()=> {
    if(element.current){
      const{ current } = element;
      current.style.transition=`opacity ${duration}s ease-in-out ${delay}s`;
      current.style.opacity = 1;
    }
  },[]);
  return {ref: element, style: {opacity : 0}};
};
```

<h3>useNetwork</h3>-navigator가 online, offline되는걸 막아줄것이다 

```
const useNetwork = (onchange) => {
  const [status, setStatus] = useState(navigator.online);
  const handleChange = () => {
    if (typeof onchange === "function") {
      onchange(navigator.onLine);
    }
    setStatus(navigator.onLine);
  };
  useEffect(() => {
    window.addEventListener("online", handleChange);
    window.addEventListener("offline", handleChange);
    () => {
      window.removeEventListener("online", handleChange);
      window.removeEventListener("offline", handleChange);
    };
  }, []);
  return status;
};
```