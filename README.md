<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dark Theme Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #2c2c2c;
        }

        .calculator {
            background-color: #1c1c1c;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.4);
            width: 300px;
        }

        .display {
            width: 100%;
            padding: 15px;
            font-size: 32px;
            text-align: right;
            margin-bottom: 20px;
            border: none;
            border-radius: 8px;
            background-color: #333;
            color: white;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        button {
            padding: 20px;
            font-size: 22px;
            border: none;
            background-color: #444;
            border-radius: 8px;
            color: white;
            cursor: pointer;
            transition: background-color 0.4s ease;
        }

        button:hover {
            background-color: #555;
        }

        button:active {
            background-color: #666;
        }

        button:nth-child(16) {
            grid-column: span 2;
            background-color: #4CAF50;
            color: white;
        }

        button:nth-child(16):hover {
            background-color: #45a049;
        }

        button:nth-child(16):active {
            background-color: #3e8e41;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" class="display" disabled />
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="deleteLast()">DEL</button>
            <button onclick="appendToDisplay('/')">/</button>
            <button onclick="appendToDisplay('*')">*</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('+')">+</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="calculate()">=</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
        </div>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function deleteLast() {
            let currentValue = document.getElementById('display').value;
            document.getElementById('display').value = currentValue.slice(0, -1);
        }

        function calculate() {
            let expression = document.getElementById('display').value;
            try {
                document.getElementById('display').value = eval(expression);
            } catch (e) {
                document.getElementById('display').value = 'Error';
            }
        }
    </script>
</body>
</html>
