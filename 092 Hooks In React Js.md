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
