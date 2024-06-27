![image](https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/389c1b13-d383-464d-885f-7c83e9d593de)

![image](https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/d27d4437-13cc-4590-b9e5-eb525fc99dc3)

```
import "./App.css";
import Button from "react-bootstrap/Button";
import Card from "react-bootstrap/Card";
import { FontAwesomeIcon } from "@fortawesome/react-fontawesome";
import { faTwitter } from "@fortawesome/free-brands-svg-icons";
import { faUser } from "@fortawesome/free-solid-svg-icons";
import { library } from "@fortawesome/fontawesome-svg-core";
import { UserData } from "./Data/UserData";
import ReactImage from "./Images/logo192.png";

// Add icons to the library
library.add(faTwitter, faUser);

function App() {
  return (
    <div
      style={{
        display: "flex",
        flexDirection: "row",
        flexWrap: "wrap",
      }}
    >
      <h1 className="text-3xl font-bold underline">All Cards Below:</h1>
      {UserData.map((item, index) => {
        return <CardComponent item={item} key={index} />;
      })}

      <img
        src={ReactImage}
        alt="Girl in a jacket"
        width="500"
        height="600"
      ></img>
    </div>
  );
}

export default App;

function CardComponent({ item }) {
  return (
    <Card
      style={{
        width: "20rem",
        backgroundColor: "aqua",
        margin: "20px",
      }}
    >
      <Card.Body>
        <Card.Title>
          <FontAwesomeIcon icon="user" /> {item.name}
        </Card.Title>
        <Card.Text>{item.bio}</Card.Text>
        <Button variant="primary">Go somewhere</Button>
      </Card.Body>
    </Card>
  );
}

```
