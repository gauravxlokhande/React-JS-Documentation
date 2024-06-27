


```
import "./App.css";
import { useState } from "react";
import { userdata } from "./Data/data.jsx";
import { FiActivity } from "react-icons/fi";

function App() {
  const [first, setfirst] = useState(userdata[0].pin);

  console.log(first);
  return (
    <div>
      {userdata.map((item, index) => {
        return (
          <div className="component">
            <div className="title">
              <h1 className="heading">{item.name}</h1>
              <FiActivity
                className="icon"
                onClick={() => setfirst(item.name)}
              />
            </div>
            <div className={first === item.name ? "activeinfo" : "info"}>
              {item.company} {item.email}
            </div>
          </div>
        );
      })}
    </div>
  );
}

export default App;

```

```
.component {
  width: 80%;
  margin-left: 80px;
}

.title {
  display: flex;
  justify-content: space-between;
  background-color: black;
  color: white;
  margin-top: 20px;
}

.heading {
  margin-left: 10px;
}
.icon {
  margin-right: 10px;
  width: 90px;
  height: 50px;
  margin-top: 13px;
}
.info {
  border: 2px solid black;
  padding: 0px;
  transform: scaleY(0);
  margin: 0;
  height: 0;
}
.activeinfo {
  padding: 13px;
  transform: scaleY(1);
  transition: 1s;
}

```
