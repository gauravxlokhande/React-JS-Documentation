
```
https://docs.fontawesome.com/web/use-with/react/
```

![image](https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/74ed1978-40ba-4d92-a1f2-7d1edda0aea0)

```
import "./App.css";
import Button from "react-bootstrap/Button";
import Card from "react-bootstrap/Card";
import { UserData } from "./Data/UserData";
import { FontAwesomeIcon } from "@fortawesome/react-fontawesome";
import { faTwitter } from "@fortawesome/free-brands-svg-icons";
import { faUser } from "@fortawesome/free-solid-svg-icons";
import { library } from "@fortawesome/fontawesome-svg-core";

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
      <h1 style={{ margin: "40px" }}>All Cards Below:</h1>
      {UserData.map((item, index) => {
        return <CardComponent item={item} key={index} />;
      })}
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
