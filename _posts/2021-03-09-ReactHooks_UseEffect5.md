---
layout: post
title: ReactHooks_UseEffect5
color: rgb(255, 111, 97)
tags: [os]
---
<h3>useScroll</h3>
user가 스크롤해서 내려갈때 색깔을 바꾸거나 다른 변화를 주어야 할때가 있다. 

```
const useScroll = () => {
  const [state, setState] = useState({
    x: 0,
    y: 0
  });
  const onScroll = () => {
    setState({ y: window.scrollY, x: window.scrollX });
  };
  useEffect(() => {
    window.addEventListener("scroll", onScroll);
    return () => window.removeEventListener("scroll", onScroll);
  }, []);
  return state;
};
...

<h1 style={{ position: "fixed", color: y > 100 ? "red" : "blue" }}>Hi</h1>
```

<h3>useFullScreen</h3>

```
const useFullScreen = (callback) => {
  const element = useRef();
  const triggleFull = () => {
    if(element.current){
      element.current.requestFullScreen();
      if(callback && typeof callback === "function"){
        callback(true);
      }
    }
  };
  const exitFull = () => {
    document.exitFullscreen();
    if(callback && typeof callback === "function"){
      callback(false);
  }
  return { element, triggleFull, exitFull };
};
```
