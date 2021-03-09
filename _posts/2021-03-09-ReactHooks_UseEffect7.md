---
layout: post
title: ReactHooks_UseEffect7
color: rgb(255, 111, 97)
tags: [os]
---

<h3>useAxios</h3>
axios=> HTTP request를 만드는것임

[index.js]
```
import React, { useEffect, useState, useRef } from "react";
import ReactDOM from "react-dom";
import useAxios from "./useAxios";

const App = () => {
  const { loading, data, refetch } = useAxios({
    url: "https://yts.am/api/v2/list_movie_json"
  });
  return (
    <div className="App" style={{ height: "1000vh" }}>
      <h1>{data && data.status}</h1>
      <button onClick={refetch}>Refetch</button>
      <h2>{loading && "Loading"}</h2>
    </div>
  );
};
const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);
```

[useAxios.js]
```
import defaultAxios from "axios";
import { useEffect, useState } from "react";

const useAxios = (opts, axiosInstance = defaultAxios) => {
  const [state, setState] = useState({
    loading: true,
    error: null,
    data: null
  });
  const [trigger, setTrigger] = useState(0);
  if (!opts.url) {
    return;
  }
  const refetch = () => {
    setState({
      ...state,
      loading:true
    });
    setTrigger(Date.now());
  }
  
  useEffect(() => {
    axiosInstance(opts).then(data => {
      setState({
        ...state,
        loading: false,
        data
      });
    }).catch(error => {
      setState({...state, loading:false, error });
    });
  }, [trigger]);
  return {...state, refetch };
};

export default useAxios;
```
