---
layout: post
title: ReactHooks_UseStates
color: rgb(255, 111, 97)
tags: [os]
---
react앱 사용하면서의 단점
1.handing input
2.data가져오기=fetching

so...we make 2 hooks
1.relation with hooks
2.어떤 api이든 편하게 데이터를 요청할수 있는 것
axios

Hooks
react의 state machine에 연결하는 방법

```
const App= () => {
  const [item, setItem] = useState(1);
  const incrementItem = () => setItem(item + 1);
  const decrementItem = () => setItem(item - 1);
  return (
    <div className="App">
      <h1>Hello {item}</h1>
      <h2>Start editing to see some magic happen!</h2>
      <button onClick={incrementItem}>Increment</button>
      <button onClick={decrementItem}>Decrement</button>
    </div>
  );
}
```

```
class AppUgly extends React.Component{ 
  state= { 
    item: 1
  }  
  render(){ 
    const { item } = this.state;
    return ( 
      <div className="App">  
        <h1>Hello {item}</h1> 
        <h2>Start editing to see some magic happen!</h2>  
        <button onClick={this.incrementItem}>Increment</button> 
        <button onClick={this.decrementItem}>Decrement</button> 
      </div>  
    );  
  }    
  incrementItem = () => {   
    this.setState(state => {  
       return { 
      item:state.item. +1 
      }; 
    });
   };
  decrementItem = () => {
    this.setState(state => {
      return {
     item:state.item. -1
     };
   });
  };
}
```

<h3>useState</h3>
1.state를 초기화 시켜주고
2.첫번째 아이템인 currentindex는 index가 될것이고 두번째 아이템인 setCurrentIndex는 value를 바꿔줄것이다.
useState의 value를 초기화해주고 현재value와 value를 변경해주는것은 매우 간단
setState=> 모든것을 새로고침 해준다, rerender함. render function이 없다고 render이 안되는게 아님.
