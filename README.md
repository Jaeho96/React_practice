## 2. JSX란

---

### 규칙

1. 태그는 꼭 닫혀있어야 한다.

```jsx
<div>태그는 꼭 닫혀야 한다!</div>
<Hello />
```

2. 두개 이상의 태그는 무조건 하나의 태그로 감싸져야 한다.

```jsx
<>
  <div>두개 이상의</div>
  <p>태그는 감싸자</p>
</>
```

3. JSX 내부에 js 변수를 보여줄때는 {}로 감싸야 한다.

```jsx
const name = "이렇게";
return <div>JavaScript 값 보여줄 땐, {name} </div>;
```

4. JSX는 camel casing을 지향한다. ex) className ...etc
   </br>
   </br>
5. JSX 주석처리는 이런 형식으로 작성한다.

```jsx
{
  /* 주석은 이렇게 */
}
```
