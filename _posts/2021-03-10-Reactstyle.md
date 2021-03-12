---
layout: post
title: ReactStyle
color: rgb(255, 111, 97)
tags: [os]
---
props가 직접 스타일로 가게 하는 방법. 애니메이션 효과도 줄수 있음
class명도 필요 없이 만약 css에서 하면 class명 2-3개 필요하고 animation speed도 component에서 변경 불가하다. 할꺼면 state사용여기서는 rotationTime을 이용해서 변경가능!

<움직이는 버튼만들기>

class App extends Component {
    render() {
      return (
          <Component>
            <Button>Hello</Button>
            <Button danger rotationTime={5}>Hello</Button>
            <Anchor href="http://google.com">Go to google</Anchor>
          </Component>
      );
    }
}

const Button = styled.button`
    border-radius: 50px;
    padding: 5px;
    min-width: 120px;
    color: white;
    font-weight: 600;
    -webkit-appearance: none;
    cursor: pointer;
    &:active,
    &focus {
        outline: none;
    }
    background-color: ${props => (props.danger ? "#e74c3c" : "#2ecc71")};
    ${props => {
        if(props.danger){
            return `animation: ${rotation} ${props.rotationTime} 2s linear infinite`;
        }
    }}
`;

const Anchor = Button.withComponent("a").extend`
   text-decoration: none;
`;

const rotation = keyframes`
  from{
    transform: rotate(0deg);
  }
  to{
    transform: rotate(360deg);
  }
`
₩₩₩

