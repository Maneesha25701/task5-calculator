# task5-calculator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-9">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #F0F0F0;
            padding: 20px;
        }
        .calculator-container {
            max-width: 200px;
            margin: 0 auto;
            background-color: white;
            padding: 10px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        .calculator-container input, .calculator-container button {
            width: 75%;
            font-size: 18px;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .button-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
        }
        button {
            background-color: #4CAF50;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #45a049;
        }
        input[disabled] {
            background-color: #f0f0f0;
        }
    </style>
</head>
<body>
    <div class="calculator-container">
        <input type="number" id="inputX" placeholder="Enter value for X" />
        <input type="number" id="inputY" placeholder="Enter value for Y" />
        <input type="text" id="result" placeholder="Result" disabled />

        <div class="button-container">
            <button onclick="performOperation('add')">Add (X + Y)</button>
            <button onclick="performOperation('subtract')">Subtract (X - Y)</button>
            <button onclick="performOperation('multiply')">Multiply (X * Y)</button>
            <button onclick="performOperation('divide')">Divide (X / Y)</button>
        </div>
    </div>

    <script>
        function performOperation(operation) {
            const x = parseFloat(document.getElementById("inputX").value);
            const y = parseFloat(document.getElementById("inputY").value);
            let result = '';

            if (isNaN(x) || isNaN(y)) {
                result = 'Invalid input';
            } else {
                switch (operation) {
                    case 'add':
                        result = x + y;
                        break;
                    case 'subtract':
                        result = x - y;
                        break;
                    case 'multiply':
                        result = x * y;
                        break;
                    case 'divide':
                        result = (y === 0) ? 'Cannot divide by zero' : x / y;
                        break;
                }
            }

            document.getElementById("result").value = result;
        }
    </script>
</body>
</html>
