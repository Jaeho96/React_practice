# 3. props로 컴포넌트에 값 전달하기

#### **props**는 properties의 약자

---

## props의 기본 사용법

App 컴포넌트에서 Hello 컴포넌트를 사용 할 때 name과 color라는 값을 보내고 싶을때 </br>
</br>
**App.js**

```jsx
import React from "react";
import Hello from "./Hello";

function App() {
  return <Hello name="react" color="red" />;
}

export default App;
```

**Hello.js**

```jsx
import React from "react";

function Hello({ color, name }) {
  //비구조화 할당(구조 분해)
  return <div style={{ color }}>안녕하세요 {name}</div>;
}

export default Hello;
```

---

## props.children 사용법

컴포넌트 태그 사이에 넣은 값을 조회하고 싶을 땐, props.children을 조회하면 된다. </br>
**Wrapper.js**

```jsx
import React from "react";

function Wrapper({ children }) {
  const style = {
    border: "2px solid black",
    padding: "16px",
  };
  return <div style={style}>{children}</div>;
}

export default Wrapper;
```

**App.js**

```jsx
import React from "react";
import Hello from "./Hello";
import Wrapper from "./Wrapper";

function App() {
  return (
    <Wrapper>
      <Hello name="react" color="red" />
      <Hello color="pink" />
    </Wrapper>
  );
}

export default App;
```
