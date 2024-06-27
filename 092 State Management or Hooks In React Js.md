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
