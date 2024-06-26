## Props is used to pass the data from Parent To Child.

<img width="469" alt="Screenshot 2024-06-26 172516" src="https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/bcb64d1e-5afe-4a4a-8055-1b1eb4172a80">
<img width="480" alt="Screenshot 2024-06-26 172650" src="https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/9d1cc7f9-4f1d-4805-8383-9bd634a17930">
<img width="391" alt="image" src="https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/bd212e3a-2165-4719-83e2-a9be2d298ba5">

app.js
```
import "./App.css";
import { Header } from "./Header/Header";
import { Footer } from "./Footer/Footer";

function App() {
  let Userinfo = {
    Name: "Gaurav Lokhande",
    Phone: "9511767637",
    Email: "gauravlokhande@gmail.com",
  };

  return (
    <>
      <Header name={"Gaurav"} UserInfo={Userinfo} />

      <Footer />
    </>
  );
}

export default App;
```


Header.jsx
```
export function Header(props) {
    console.log(props);
    return (
        <div>
            <h1>Header {props.name} {props.UserInfo.Phone}</h1>
        </div>
    )
}
```
