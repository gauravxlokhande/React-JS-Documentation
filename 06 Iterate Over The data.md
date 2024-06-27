![image](https://github.com/gauravxlokhande/React-JS-Documentation/assets/119065314/e192ca4a-acd9-4c4b-be04-227f0b370eb7)



```
import "./App.css";
import Button from "react-bootstrap/Button";
import Card from "react-bootstrap/Card";
import { UserData } from "./Data/UserData";

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
        <Card.Title>Card Title</Card.Title>
        <Card.Text>{item.bio}</Card.Text>
        <Button variant="primary">Go somewhere</Button>
      </Card.Body>
    </Card>
  );
}

```

```
export let UserData = [
    {
        "name": "Adeel Solangi",
        "language": "Sindhi",
        "id": "V59OF92YF627HFY0",
        "bio": "Donec lobortis eleifend condimentum. Cras dictum dolor lacinia lectus vehicula rutrum. Maecenas quis nisi nunc. Nam tristique feugiat est vitae mollis. Maecenas quis nisi nunc.",
        "version": 6.1
    },
    {
        "name": "Afzal Ghaffar",
        "language": "Sindhi",
        "id": "ENTOCR13RSCLZ6KU",
        "bio": "Aliquam sollicitudin ante ligula, eget malesuada nibh efficitur et. Pellentesque massa sem, scelerisque sit amet odio id, cursus tempor urna. Etiam congue dignissim volutpat. Vestibulum pharetra libero et velit gravida euismod.",
        "version": 1.88
    },
    {
        "name": "Aamir Solangi",
        "language": "Sindhi",
        "id": "IAKPO3R4761JDRVG",
        "bio": "Vestibulum pharetra libero et velit gravida euismod. Quisque mauris ligula, efficitur porttitor sodales ac, lacinia non ex. Fusce eu ultrices elit, vel posuere neque.",
        "version": 7.27
    },
    {
        "name": "Abla Dilmurat",
        "language": "Uyghur",
        "id": "5ZVOEPMJUI4MB4EN",
        "bio": "Donec lobortis eleifend condimentum. Morbi ac tellus erat.",
        "version": 2.53
    },
    {
        "name": "Adil Eli",
        "language": "Uyghur",
        "id": "6VTI8X6LL0MMPJCC",
        "bio": "Vivamus id faucibus velit, id posuere leo. Morbi vitae nisi lacinia, laoreet lorem nec, egestas orci. Suspendisse potenti.",
        "version": 6.49
    }]
```
