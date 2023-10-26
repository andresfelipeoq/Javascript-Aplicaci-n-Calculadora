# Javascript-Aplicaci-n-Calculadora


# Project Title

Crear una calculadora simple en JavaScript es un buen proyecto para principiantes que desean aprender sobre la programación web. A continuación, te proporcionaré un ejemplo básico de cómo crear una calculadora web utilizando HTML, CSS y JavaScript:

    HTML:
    <!DOCTYPE html>
<html>
<head>
    <title>Calculadora</title>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('+')">+</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('*')">*</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="calculateResult()">=</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="appendToDisplay('/')">/</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

CSS (Guárdalo en un archivo llamado styles.css):

body {
    font-family: Arial, sans-serif;
    text-align: center;
}

.calculator {
    margin: 50px auto;
    width: 250px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 5px #ccc;
    background-color: #f9f9f9;
}

#display {
    width: 95%;
    margin: 5px;
    padding: 5px;
    font-size: 18px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 5px;
    margin: 5px;
}

button {
    font-size: 20px;
}


JavaScript (Guárdalo en un archivo llamado script.js):

let display = document.getElementById('display');
let currentValue = '';
let operator = '';
let result = 0;

function appendToDisplay(value) {
    currentValue += value;
    display.value = currentValue;
}

function clearDisplay() {
    currentValue = '';
    operator = '';
    display.value = '';
}

function calculateResult() {
    switch (operator) {
        case '+':
            result = parseFloat(result) + parseFloat(currentValue);
            break;
        case '-':
            result = parseFloat(result) - parseFloat(currentValue);
            break;
        case '*':
            result = parseFloat(result) * parseFloat(currentValue);
            break;
        case '/':
            result = parseFloat(result) / parseFloat(currentValue);
            break;
        default:
            result = parseFloat(currentValue);
    }
    display.value = result;
    currentValue = '';
    operator = '';
    result = 0;
}

function setOperator(op) {
    operator = op;
    if (currentValue !== '') {
        result = currentValue;
        currentValue = '';
    }
}

document.addEventListener('DOMContentLoaded', function () {
    clearDisplay();
});




