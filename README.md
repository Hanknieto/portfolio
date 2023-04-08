<!DOCTYPE html>
<html>
<head>
    <title>Calculadora</title>
    <style>
        * {
            box-sizing: border-box;
        }
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            width: 240px;
            margin: 0 auto;
        }
        .calculator {
            background-color: #f2f2f2;
            border-radius: 5px;
            padding: 10px;
        }
        .screen {
            background-color: #fff;
            border: 1px solid #ddd;
            height: 40px;
            line-height: 40px;
            text-align: right;
            padding: 0 10px;
            margin-bottom: 10px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        .buttons button {
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 5px;
            height: 40px;
            line-height: 40px;
            text-align: center;
            font-size: 18px;
            cursor: pointer;
        }
        .buttons button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="calculator">
            <div class="screen" id="screen"></div>
            <div class="buttons">
                <button onclick="clearScreen()">C</button>
                <button onclick="deleteLastCharacter()">&#9003;</button>
                <button onclick="appendCharacter('/')">&#247;</button>
                <button onclick="appendCharacter('7')">7</button>
                <button onclick="appendCharacter('8')">8</button>
                <button onclick="appendCharacter('9')">9</button>
                <button onclick="appendCharacter('*')">&#215;</button>
                <button onclick="appendCharacter('4')">4</button>
                <button onclick="appendCharacter('5')">5</button>
                <button onclick="appendCharacter('6')">6</button>
                <button onclick="appendCharacter('-')">&#8722;</button>
                <button onclick="appendCharacter('1')">1</button>
                <button onclick="appendCharacter('2')">2</button>
                <button onclick="appendCharacter('3')">3</button>
                <button onclick="appendCharacter('+')">&#43;</button>
                <button onclick="appendCharacter('0')">0</button>
                <button onclick="appendCharacter('.')">.</button>
                <button onclick="calculateResult()">=</button>
            </div>
        </div>
    </div>

    <script>
        const screen = document.getElementById('screen');

        function appendCharacter(char) {
            screen.innerHTML += char;
        }

        function clearScreen() {
            screen.innerHTML = '';
        }

        function deleteLastCharacter() {
            screen.innerHTML = screen.innerHTML.slice(0, -1);
        }

        function calculateResult() {
            try {
                const result = eval(screen.innerHTML);
                screen.innerHTML = result;
            } catch (error) {
                screen.innerHTML = 'Error';
            }
        }
    </script>
</body>
</html>
