# xxx
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Custom Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f1f1f1;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .calculator {
            background-color: #000;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
            width: 320px;
        }

        .screen {
            background-color: #333;
            color: #fff;
            font-size: 2em;
            text-align: right;
            padding: 20px;
            margin-bottom: 10px;
            border-radius: 10px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .buttons button {
            padding: 20px;
            font-size: 1.5em;
            border: none;
            border-radius: 10px;
            color: white;
            background-color: #444;
            transition: background-color 0.2s;
        }

        .buttons button.operator {
            background-color: #f1a33b;
        }

        .buttons button.clear {
            background-color: #d7263d;
        }

        .buttons button.equal {
            background-color: #2ecc71;
        }

        .buttons button:hover {
            background-color: #666;
        }

        .buttons button.operator:hover {
            background-color: #d98b2b;
        }

        .buttons button.clear:hover {
            background-color: #c41b2b;
        }

        .buttons button.equal:hover {
            background-color: #27ae60;
        }
    </style>
</head>
<body>

<div class="calculator">
    <div class="screen" id="screen">0</div>
    <div class="buttons">
        <button class="clear" onclick="clearScreen()">C</button>
        <button onclick="appendNumber('7')">7</button>
        <button onclick="appendNumber('8')">8</button>
        <button onclick="appendNumber('9')">9</button>

        <button class="operator" onclick="appendOperator('/')">/</button>
        <button onclick="appendNumber('4')">4</button>
        <button onclick="appendNumber('5')">5</button>
        <button onclick="appendNumber('6')">6</button>

        <button class="operator" onclick="appendOperator('')"></button>
        <button onclick="appendNumber('1')">1</button>
        <button onclick="appendNumber('2')">2</button>
        <button onclick="appendNumber('3')">3</button>

        <button class="operator" onclick="appendOperator('-')">-</button>
        <button onclick="appendNumber('0')">0</button>
        <button onclick="appendOperator('.')">.</button>
        <button class="equal" onclick="showMissYou()">=</button>

        <button class="operator" onclick="appendOperator('+')">+</button>
    </div>
</div>

<script>
    let screen = document.getElementById('screen');
    let expression = '';

    function clearScreen() {
        expression = '';
        screen.innerText = '0';
    }

    function appendNumber(number) {
        if (screen.innerText === '0' || expression === '') {
            expression = number;
        } else {
            expression += number;
        }
        screen.innerText = expression;
    }

    function appendOperator(operator) {
        if (expression !== '') {
            expression += operator;
            screen.innerText = expression;
        }
    }

    function showMissYou() {
        screen.innerText = 'I Miss U :(';
        expression = '';
    }
</script>

</body>
</html>
