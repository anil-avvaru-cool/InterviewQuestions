
## Major features of react
- JSX
- Virtual DOM instead of actual DOM
- One way data binding
- Server side rendering
- Reusable components
## React version
2025 Jan - Version 19

## JSX
JSX is a syntactic sugar of
React.CreateElement(type, props, ...children)
```javascript:

export default function App(){
    return <h1 className="greeting">
    {"Hello, this is JSX code!"}
    </h1>;
}
```

## What is the difference between Element vs Component?

Element is a plain object like builtin elements like div

```javascript:
const element = React.CreateElement("div",{id:"login-btn", "Login"})
```
Component is having more functionality.
```javascript:
const Button = ({handleLogin})=>
(
    <div id="login-btn" onClick={handleLogin} >
    Login
    </div>
);
```

