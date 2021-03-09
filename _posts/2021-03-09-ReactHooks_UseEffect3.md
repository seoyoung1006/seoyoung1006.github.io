---
layout: post
title: ReactHooks_UseEffect3
color: rgb(255, 111, 97)
tags: [os]
---

사용자가 버튼을 클릭 하는 작업을 하면 실행하기 전에 메세지를 보여주는것, 예를들어 '정말 그렇게 하고 싶니?'와 같은 메세지s
<h3>Confirm</h3>

```
export const useConfirm = (message = "", onConfirm, onCancel) => {
  if (!onConfirm || typeof onConfirm !== "function") {
    return;
  }
  if (onCanel && typeof onCancel !== "function") {
      return;
  }
  const confirmAction = () => {
    if (confirm(message)) {
      onConfirm();
    } else {
      onCancel();
    }
  };
  return confirmAction;
};
```

<h3>usePreventLeave</h3>-우리가 창을 닫을때 에를 들어 "야ㅑ 아직 저장 안했다!!"라고 말해주는 기능
function은 onLeaving을 실행 해줄때 됨
beforeunload=> 창이 닫히기 전에 함수 실행되는것을 허락해준다. 

```
const usePreventLeave = () => {
  const listener = (event) => {
    event.preventDefault();
    event.returnValue = "";
  }
  const enablePrevent = () => window.addEventListener("beforeunload", listener);
  const disablePrevent = () =>
    window.removeEventListener("beforeunload", listener);
  return { enablePrevent, disablePrevent };
}
```