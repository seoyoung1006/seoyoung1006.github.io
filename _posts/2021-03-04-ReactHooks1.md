---
layout: post
title: ReactHooks_1
color: rgb(255, 111, 97)
tags: [os]
---
<style>
p {
  background-Color: black;
  color: gray;
}
</style>
react앱 사용하면서의 단점
1.handing input
2.data가져오기=fetching

so...we make 2 hooks
1.relation with hooks
2.어떤 api이든 편하게 데이터를 요청할수 있는 것
axios

Hooks
react의 state machine에 연결하는 방법

<p>
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
</p>
<p>
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
</p>