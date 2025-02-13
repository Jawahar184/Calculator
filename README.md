<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body{ 
            text-align: center; 
            font-family: Arial; 
        }
        .calculator{ 
            width: 400px; 
            margin: auto; 
            padding: 20px; 
            background: #7b96bc; 
            border-radius: 10px;
        }
        #display{ 
            width: 100%; 
            height: 40px; 
            text-align: right; 
            font-size: 24px; 
            margin-bottom: 10px; 
        }
        button{ 
            width: 80px; 
            height: 45px; 
            font-size: 18px;
            margin: 5px; 
        }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" disabled>
    <br>
    <button onclick="clearDisplay()">AC</button>
    <button onclick="deleteLast()">DEL</button>
    <button onclick="Display('%')">%</button>
    <button onclick="Display('/')">/</button>   
    <br>
    <button onclick="Display('7')">7</button>
    <button onclick="Display('8')">8</button>
    <button onclick="Display('9')">9</button>
    <button onclick="Display('*')">*</button>
    <br>
    <button onclick="Display('4')">4</button>
    <button onclick="Display('5')">5</button>
    <button onclick="Display('6')">6</button>
    <button onclick="Display('-')">-</button>
    <br>
    <button onclick="Display('1')">1</button>
    <button onclick="Display('2')">2</button>
    <button onclick="Display('3')">3</button>
    <button onclick="Display('+')">+</button>
    <br>
    <button onclick="Display('0')">0</button>
    <button onclick="Display('.')">.</button>
    <button onclick="calculateResult()">=</button>
</div>

<script>
    function Display(value) {
        document.getElementById("display").value += value;
    }

    function clearDisplay() {
        document.getElementById("display").value = "";
    }

    function deleteLast() {
        let display = document.getElementById("display");
        display.value = display.value.slice(0, -1);
    }

    function calculateResult() {
        try {
            let display = document.getElementById("display");
            display.value = eval(display.value);
        } catch {
            display.value = "Error";
        }
    }
</script>

</body>
</html>
