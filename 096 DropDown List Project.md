![image](https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/f4a1b3a5-e70d-4fbe-bca4-a9d072c41e18)

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


# Using Prop Drealling

```
import React, { useState } from 'react'
import "./faq.css"


export function FAQ({ userInfo }) {

    const [Showtitle, setShowtitle] = useState(userInfo[0].ID);

    let titleComponent = userInfo.map((Userinformation, index) => {

        let userdata = {
            Userinformation,
            Showtitle,
            setShowtitle
        }

        return (
            <Description key={index} AllData={userdata} />
        )
    }
    );


    return (
        <div>
            <h1>What Is an FAQ Page?</h1>
            {titleComponent}
        </div>
    )
}

function Description({ AllData }) {

    let { Userinformation, Showtitle, setShowtitle } = AllData
    return (
        <div>
            <div className='Component'>
                <h1 onClick={() => setShowtitle(Userinformation.ID)} className='title'>{Userinformation.name}</h1>
                <p className={Showtitle === Userinformation.ID ? 'description' : 'hidedescription'}>{Userinformation.Description}</p>
            </div>
        </div>
    )
}

```
