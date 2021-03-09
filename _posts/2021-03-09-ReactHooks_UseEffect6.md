---
layout: post
title: ReactHooks_UseEffect6
color: rgb(255, 111, 97)
tags: [os]
---
<h3>useNotification</h3>
알림창 뜨게 하는것

```
const useNotification = (title, options) => {
  if (!("Notification" in window)) {
    return;
  }
  const fireNotif = () => {
    if (Notification.permission !== "granted") {
      Notification.requestPermission().then((permission) => {
        if (permission === "granted") {
          new Notification(title, options);
        } else {
          return;
        }
      });
    } else {
      new Notification.options();
    }
  };
  return fireNotif;
};
```