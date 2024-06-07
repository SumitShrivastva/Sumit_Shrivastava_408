Web Calculator-->
Html-
<!DOCTYPE html>
<html lang="en">

<head>
  <link rel="stylesheet" href="calculator.css">
  <title>Scientific Calculator</title>
</head>

<body>
  <div class="container">
    <h1 class="heading">Scientific Calculator</h1>
    <div class="calculator-container">
      <div id="calculator">
        <input type="text" id="display" readonly>
        <div class="button-container">
          <button class="button clear" onclick="clearDisplay()">C</button>
          <button class="button" onclick="appendToDisplay('7')">7</button>
          <button class="button" onclick="appendToDisplay('8')">8</button>
          <button class="button" onclick="appendToDisplay('9')">9</button>
          <button class="button operator" onclick="appendToDisplay('+')">+</button>
          <button class="button" onclick="appendToDisplay('4')">4</button>
          <button class="button" onclick="appendToDisplay('5')">5</button>
          <button class="button" onclick="appendToDisplay('6')">6</button>
          <button class="button operator" onclick="appendToDisplay('-')">-</button>
          <button class="button" onclick="appendToDisplay('1')">1</button>
          <button class="button" onclick="appendToDisplay('2')">2</button>
          <button class="button" onclick="appendToDisplay('3')">3</button>
          <button class="button operator" onclick="appendToDisplay('*')">*</button>
          <button class="button zero" onclick="appendToDisplay('0')">0</button>
          <button class="button" onclick="appendToDisplay('.')">.</button>
          <button class="button equal" onclick="calculate()">=</button>
          <button class="button operator" onclick="appendToDisplay('/')">/</button>
          <button class="button function" onclick="calculateSquareRoot()">√</button>
          <button class="button function" onclick="appendToDisplay('Math.pow(')">x^</button>
          <button class="button function" onclick="appendToDisplay('Math.sin(')">sin</button>
          <button class="button function" onclick="appendToDisplay('Math.cos(')">cos</button>
          <button class="button function" onclick="appendToDisplay('Math.tan(')">tan</button>
          <button class="button function" onclick="appendToDisplay('Math.log(')">log</button>
          <button class="button" onclick="appendToDisplay('(')"> ( </button>
          <button class="button" onclick="appendToDisplay(')')"> ) </button>
        </div>
      </div>
    </div>
  </div>

  <script>
    let currentDisplay = '';
    document.querySelector('#display').value = currentDisplay;

    function appendToDisplay(value) {
      currentDisplay += value;
      document.querySelector('#display').value = currentDisplay;
    }

    function clearDisplay() {
      currentDisplay = '';
      document.querySelector('#display').value = currentDisplay;
    }

    function calculate() {
      let result = eval(currentDisplay);
      currentDisplay = result;
      document.querySelector('#display').value = currentDisplay;
    }

    function calculateSquareRoot() {
      let result = Math.sqrt(eval(currentDisplay));
      currentDisplay = result;
      document.querySelector('#display').value = currentDisplay;
    }
  </script>
</body>

</html>

CSS-
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.heading {
  text-align: center;
  font-size: 24px;
  margin-bottom: 20px;
}

.calculator-container {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 20px;
}

#calculator {
  text-align: center;
}

#display {
  width: calc(100% - 40px);
  margin-bottom: 15px;
  padding: 10px;
  font-size: 18px;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: none;
}

.button-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.button {
  width: 100%;
  padding: 15px 0;
  font-size: 18px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.clear {
  background-color: #ff6347;
  color: #fff;
}

.operator {
  background-color: #6b7c93;
  color: #fff;
}

.equal {
  background-color: #4caf50;
  color: #fff;
}

.function {
  background-color: #007bff;
  color: #fff;
}

.zero {
  grid-column: span 2;
}

.button:hover {
  filter: brightness(1.2);
}

