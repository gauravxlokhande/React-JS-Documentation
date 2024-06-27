```
import "./App.css";
import { useState } from "react";

function App() {
  let OnclickButton = () => {
    console.log(setCount(Count + 5));
  };

  const [Count, setCount] = useState(5);

  return (
      <Button variant="primary" onClick={OnclickButton}>
  );
}

export default App;
```
```
import { useState } from "react";
import "./App.css";
import btnStyle from "./Modules/Button.module.css";

function App() {
  const [pState, setpState] = useState(false);

  return (
    <div>
      <input
        style={{ backgroundColor: "red", width: "40%" }}
        type={pState ? "text" : "password"}
      />

      <button className={btnStyle.Standerd} onClick={() => setpState(!pState)}>
        {pState ? "Hide" : "Show"}
      </button>
    </div>
  );
}

export default App;

```



![image](https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/df556ffd-fc94-4d09-8416-e9b4defe4f66)


```
import "./App.css";
import { useState } from "react";
import { userdata } from "./Data/data.jsx";

function App() {
  const [first, setfirst] = useState(userdata[0].pin);
  console.log(first);
  return (
    <div>
      {userdata.map((item, index) => {
        return <h1 onClick={() => setfirst(item.name)}>{item.name}</h1>;
      })}
    </div>
  );
}

export default App;

```
