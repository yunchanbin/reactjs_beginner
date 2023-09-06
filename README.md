# ReactJS로 영화 웹 서비스 만들기

- [ReactJS로 영화 웹 서비스 만들기](#reactjs로-영화-웹-서비스-만들기)
- [2 THE BASICS OF REACT](#2-the-basics-of-react)
  - [- 2.0 Introduction](#--20-introduction)
  - [- 2.1 Before React](#--21-before-react)
  - [- 2.2 Our First React Element](#--22-our-first-react-element)
  - [- 2.3 Events in React](#--23-events-in-react)
  - [- 2.4 Recap](#--24-recap)
  - [- 2.5 JSX (JavaScript XML)](#--25-jsx-javascript-xml)
  - [- 2.6 JSX part Two](#--26-jsx-part-two)
- [3 STATE](#3-state)
  - [- 3.0 Understanding State](#--30-understanding-state)
  - [- 3.1 setState part One](#--31-setstate-part-one)
  - [- 3.2 setState part Two](#--32-setstate-part-two)
  - [- 3.3 Recap](#--33-recap)
  - [- 3.4 State Function](#--34-state-function)
  - [- 3.5 Input and State](#--35-input-and-state)
  - [- 3.6 State Practice part One](#--36-state-practice-part-one)

# 2 THE BASICS OF REACT

### - 2.0 Introduction

리액트는 interactive한 웹사이트를 만들기 위해서 쓴다.

<br>

### - 2.1 Before React

바닐라 js를 이용한 코드 작성을 해봄.

<br>

### - 2.2 Our First React Element

HTML을 이용하지 않고 javascript 와 ReactJS만을 이용해서 element를 생성할 것이다.

ReactJS는 HTML을 생성한다.
ReactJS는 엔진. Interactive한 UI를 만들 수 있게 함.

ReactDOM is library (or package). It makes all React Elements can be into HTML body.

- `ReactDOM.render([리액트 요소])` : 리액트 요소를 HTML 요소로 만들어 배치한다는 뜻. 사용자에게 보여지도록 하는 것.

<br>

### - 2.3 Events in React

eventListener 대신에 React에서 바로 event 관리하는 방법.

코드 작성
![](md-img/2.3-1.png)
property 자리에 object로 넣어주면 됨. (props?)

결과
![](md-img/2.3-2.png)
![](md-img/2.3-3.png)
h3 위에 마우스를 올리거나 버튼을 클릭하면 console에 찍힌다.

<br>

### - 2.4 Recap

개발자로서 앞으로 이렇게 프로그램을 짤 일은 없다. 즉, 앞으로는 createElement를 사용하지 않는다.(다른 방법 사용.)

<br>

### - 2.5 JSX (JavaScript XML)

HTML에서 사용한 문법과 비슷한 문법으로 리액트 요소를 만들 수 있게 해준다.

코드 작성
![](md-img/2.5-1.png)
아래 형식으로 작성하고 babel을 설치하면 JSX 문법을 사용할 수 있다.

https://unpkg.com/@babel/standalone/babel.min.js

<br>

### - 2.6 JSX part Two

먼저, Title과 Button을 함수로 만들어 준다.
![](md-img/2.6-1.png)
`() =>` 쓰면 함수로 만들어 줄 수 있음(arrow funtion)
![](md-img/2.6-2.png)
이렇게 return 써서 함수 만드는 거랑 완전히 같음.

![](md-img/2.6-3.png)
컴포넌트의 이니셜은 반드시 대문자로.
저 노란색 자리에 return 값이 들어간다고 생각하면 됨. 실제로 컴포넌트를 나누지 않고 저기다 그냥 한번에 적어도 상관 없음.

![](md-img/2.6-4.png)
마지막으로 Container도 함수로 만들어주고 컴포넌트를 렌더링 하면 된다.

<br>

# 3 STATE

### - 3.0 Understanding State

변수들을 JSX에 전달하는 방법을 알아야 한다.
![](md-img/3.0-1.png)
혹은 함수를 새로 만들어서
![](md-img/3.0-2.png)
버튼을 누를 때마다 counter가 바뀌도록 설정.

![](md-img/3.0-3.png)
UI는 변하지 않지만 counter는 제대로 증가하고 있는 것을 확인.

![](md-img/3.0-4.png)
countUp 함수가 실행될 때 마다 re-rendering 시켜주면 ui도 새로고침 된다.

![](md-img/3.0-4.png)
아예 render라는 함수를 새로 정의해서 사용.

여기서 바닐라 js랑 차이점은, counter가 바뀌면서 span 전체가 새로고침 되는게 아니라 {counter} 부분만 re-rendering 된다.

<br>

### - 3.1 setState part One

이제 React.js 어플 내에서 데이터를 보관하고 자동으로 리랜더링을 일으킬 수 있는 방법을 배운다.(트리거가 발동해서 리랜더링 시켜줌)

(일단 데이터를 let 변수에 담는 것이 기존의 컨셉이었다.)

- `React.useState([초기값])`
  ![](md-img/3.1-1.png)
  여기서 undifined 된 부분이 데이터고, 뒤에 f가 data를 바꿀때 하용하는 함수.

> - 배열에서 item을 꺼내서 각각의 변수에 담는 법
>   ![](md-img/3.1-2.png)
>   이렇게 하면 myFavFood는 tomato가 되고, mySecondFavFood는 potato가 된다.

배열에 이름을 붙여줌.
![](md-img/3.1-3.png)

<br>

### - 3.2 setState part Two

![](md-img/3.2-1.png)
counter가 바뀌기 때문에 let으로 바꿔주고, 버튼에 이벤트 리스너 달고, 함수 만들어서 실행시켜주면 counter가 잘 올라가고 있다.

이까지는 앞과 동일하고, 어떻게 리랜더링 시켜줄 것인지가 문제.

- modifier function : 데이터를 그 값으로 업데이트 한 후 자동으로 리랜더링을 일으킨다.

![](md-img/3.2-2.png)
다시 const로 선언한 거 잘 봐라. modifier로 데이터 값을 바꾸면 const로 선언해도 된다.

<br>

### - 3.3 Recap

React.js에서는 데이터가 바뀔때마다 컴포넌트를 리랜더링하고 UI를 refresh한다.

<br>

### - 3.4 State Function

- `[function name]([현재 값] => [현재 값에 연산])` :
  이전 데이터를 바탕으로 새로운 데이터를 설정하고 싶다면,
  ![](md-img/3.4-1.png)
  이렇게 계산하는 것이 안전하다. 왜냐면 current값이 변질되지 않은 현재 값이라는 것을 보증해주기 때문.

<br>

### - 3.5 Input and State

분->시간 단위 바꾸기

![](md-img/3.5-1.png)
<small>lable -> label 오타 수정</small>

JSX에서 이렇게는 안됨. for은 javascript에서 사용되는 언어이므로 html에서 사용하듯이 property를 추가할 수 없다. class도 똑같이 쓸 수 없음.

class는 className으로,
for은 htmlFor로 사용해야 함.

- uncontrolled :
  input의 value를 통제할 수 없기 때문에 React.js에서 이러한 input을 uncontrolled라고 한다.
  ![](md-img/3.5-2.png)

코드 작성
![](md-img/3.5-3.png)
event 이용하는 건 javascript에서랑 똑같이 하면 됨.

<br>

### - 3.6 State Practice part One

코드 작성
![](md-img/3.6-1.png)
