<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Simple Calculator</title>
<style>
  body { font-family: Arial, sans-serif; }
  .calculator {
    width: 250px;
    margin: 50px auto;
    padding: 10px;
    border: 2px solid #444;
    border-radius: 8px;
  }
  .display {
    width: 100%;
    height: 40px;
    font-size: 20px;
    margin-bottom: 10px;
    text-align: right;
    padding: 5px;
    border: 1px solid #ccc;
  }
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 5px;
  }
  button {
    height: 40px;
    font-size: 18px;
    cursor: pointer;
  }
</style>
</head>
<body>
<div class="calculator">
  <input type="text" class="display" id="display" readonly />
  <div class="buttons">
    <button onclick="appendToDisplay('7')">7</button>
    <button onclick="appendToDisplay('8')">8</button>
    <button onclick="appendToDisplay('9')">9</button>
    <button onclick="appendToDisplay('/')">/</button>

    <button onclick="appendToDisplay('4')">4</button>
    <button onclick="appendToDisplay('5')">5</button>
    <button onclick="appendToDisplay('6')">6</button>
    <button onclick="appendToDisplay('*')">*</button>

    <button onclick="appendToDisplay('1')">1</button>
    <button onclick="appendToDisplay('2')">2</button>
    <button onclick="appendToDisplay('3')">3</button>
    <button onclick="appendToDisplay('-')">-</button>

    <button onclick="appendToDisplay('0')">0</button>
    <button onclick="appendToDisplay('.')">.</button>
    <button onclick="calculateResult()">=</button>
    <button onclick="appendToDisplay('+')">+</button>

    <button onclick="clearDisplay()" style="grid-column: span 4; background-color: #f44336; color: white;">Clear</button>
  </div>
</div>

<script>
  const display = document.getElementById('display');

  function appendToDisplay(value) {
    display.value += value;
  }

  function calculateResult() {
    try {
      display.value = eval(display.value);
    } catch (e) {
      display.value = 'Error';
    }
  }

  function clearDisplay() {
    display.value = '';
  }
</script>
</body>
</html>

