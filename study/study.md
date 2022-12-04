# ReactJS 공부 기록

- React.createElement("") : 반드시 생성하고자 하는 HTML 태그와 똑같아야함
- React.createElement("",{ : ""}, "")
  = 첫 번째에는 태그
  - 두 번째에는 태그의 property (class name, id, style 등 가능)
    - property에 eventListener 넣는 것도 가능
    - {onClick: () => }
  - 세 번째에는 태그의 content(내용)

## React JS & React-dom

- React JS : 어플리케이션이 interactive 하도록 만들어주는 library (엔진과 같음)
- React-dom : library or package. 모든 react element들을 HTML body에 둘 수 있도록 해줌

- ReactDOM.render() : React element를 가지고 HTML로 만들어 배치한다는 의미(**사용자에게 보여준다**)

  - ReactDOM.render(span, span이 가야할 위치)

- 바닐라 JS는 HTML -> JS 순서
- React는 JS -> HTML 순서 --> 이것이 React 핵심 !

- 두 가지 const를 render 하고자 하는 경우 div를 만든 후 React.createElement("div", null, [span,btn])과 같이 배열을 만들어 content 위치에 넣어줌
