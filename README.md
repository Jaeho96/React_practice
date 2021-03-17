# 4. 조건부 렌더링

#### **조건부 렌더링**이란, 특정 조건에 따라 다른 결과물을 렌더링하는 것을 의미한다.

예를 들어서, App 컴포넌트에서 Hello 컴포넌트를 사용 할 때, isSpecial이라는 props를 설정해보겠다.

---

## 조건부 렌더링하는 첫 번째 방법: 삼항 연산자

**보통 삼항 연산자**는 **특정 조건에 따라 보여줘야 하는 내용이 다를 때 사용**한다. </br>
</br>
**App.js**

```jsx
import React from "react";
import Hello from "./Hello";
import Wrapper from "./Wrapper";

function App() {
  return (
    <Wrapper>
      <Hello name="react" color="red" isSpecial={true} />
      <Hello color="pink" />
    </Wrapper>
  );
}

export default App;
```

**Hello.js**

```jsx
import React from "react";

function Hello({ color, name, isSpecial }) {
  return (
    <div style={{ color }}>
      {isSpecial ? <b>*</b> : null}
      {/*isSpecial값이 true면 *이 렌더링되고 false면 null*/}
      안녕하세요 {name}
    </div>
  );
}

Hello.defaultProps = {
  name: "이름없음",
};

export default Hello;
```

---

## 조건부 렌더링하는 두 번째 방법: &&(and) 연산자

지금은 내용이 달라지는게 아니라, 단순히 특정 조건이 true이면 보여주고 그렇지 않다면 숨겨주기 때문에
&&(and) 연산자를 사용하는게 더 간편하다. </br>
**Hello.js**

```jsx
import React from "react";

function Hello({ color, name, isSpecial }) {
  return (
    <div style={{ color }}>
      {isSpecial && <b>*</b>}
      안녕하세요 {name}
    </div>
  );
}

Hello.defaultProps = {
  name: "이름없음",
};

export default Hello;
```
