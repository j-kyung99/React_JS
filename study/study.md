# ReactJS 공부 기록

- React.createElement("") : 반드시 생성하고자 하는 HTML 태그와 똑같아야함
- React.createElement("",{ : ""}, "")
  = 첫 번째에는 HTML 태그
  - 두 번째에는 태그의 property (class name, id, style 등 가능)
    - property에 eventListener 넣는 것도 가능
    - {onClick: () => }의 형식
  - 세 번째에는 태그의 content(내용)

## React JS & React-dom

- React JS : 어플리케이션이 interactive 하도록 만들어주는 library (엔진과 같음)
- React-dom : library or package. 모든 react element들을 HTML body에 둘 수 있도록 해줌

- ReactDOM.render() : React element를 가지고 HTML로 만들어 배치한다는 의미(**사용자에게 보여준다**)

  - ReactDOM.render(span, span이 가야할 위치)

- 바닐라 JS는 HTML -> JS 순서
- React는 JS -> HTML 순서 --> 이것이 React 핵심 !

- 두 가지 const를 render 하고자 하는 경우 div를 만든 후 React.createElement("div", null, [span,btn])과 같이 배열을 만들어 content 위치에 넣어줌

- div에 const를 넣으려면 const를 함수로 만들어야함
  - const Btn = () => (); (arrow function)
  - 위 arrow function은 function Btn() {return ();} 과 같음
- 컴포넌트의 첫 글자는 반드시 대문자 (소문자로 작성 시 우리가 작성한 요소가 아니라 기존 HTML 태그로 인식)

- 리액트의 장점 : ui에서 바뀐 부분만 업데이트

### 암기하면 좋아요

- 리액트는 변경된 부분만 업데이트가 됨

  - 리액트가 아닌 바닐라 JS를 사용한 브라우저는 노드정보가 바뀔때마다 노드트리를 처음부터 다시 생성해야함
  - 리액트는 가상돔을 사용하므로 사용자 시야에 보이는 부분만 수정해서 보여줌 -> 모든 업데이트가 끝나면 일괄로 합쳐져 돔에 전달함
  - **즉, 브라우저 작동원리와 연관이 있음** / 렌더트리 단계를 얼마나 최적화하는게 중요한가가 프엔의 핵심!

- const [counter, setCounter] = React.useState(0);

  - modifier 함수를 가지고 state를 변경할 때 컴포넌트가 재생성 됨(새로운 값으로 리렌더링)

- state를 세팅하는 두 가지 방법

  1. 직접 할당 : setState(state + 1)
  2. 함수 할당 : setState(state => state + 1) -> 함수의 첫번째 인자는 현재 state

- JSX는 class / for과 같은 JavaScript에서 선점된 문법 용어 사용을 금함

  - class => className, for => htmlFor로 변경하여 사용

- state 값으로 input의 enabled/disabled 여부 결정 가능

### 4.1

- props에 function을 보낼 수 있음
  - JSX이므로 html 태그 자체에 이벤트 리스너를 넣는것과는 전혀 다름
  - 이벤트를 실행시키는 함수가 프로퍼티로 들어간 것
  - 결론 : 커스텀 컴포넌트에서의 onClick은 이벤트 리스너가 아닌 단지 하나의 props임
- 불필요한 re-render는 React.memo()로 관리 가능
  - 부모 컴포넌트의 state 변경 시 자식 컴포넌트들도 re-render이 일어나게 됨 -> 이를 방지하기 위하여 memo사용
