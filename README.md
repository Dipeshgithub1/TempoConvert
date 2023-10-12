# TempoConvert
 "TempoConvert" project is a user-friendly and interactive tool for converting temperatures between Celsius and Fahrenheit, and it provides a visual history of the user's interactions with the converter.

 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TEMPERATURE CONVERTER</title>
    <style>
      body{
        padding: 50px 100px;
      }
      h1{
        text-align: center;
      }
      #container {
        text-align: center;
        background-color: chartreuse;
        padding: 50px;
      }
      .input-div{
        display: inline-block;
      }
      .inp{
        padding: 5px 10px;
        margin: 5px;
        font-size: 35px;
        font-weight: bold;
      }
      label{
        font-size: 25px;
        font-weight: bolder;
      }
      #history {
        text-align: left;
        margin: 20px;
      }
      /* Increase button size */
      #clear {
        font-size: 24px;
        padding: 10px 20px;
      }
    </style>
</head>
<body>
    <h1>TEMPERATURE CONVERTER</h1>
    <div id="container">
        <div class="input-div">
            <label>Celsius</label><br>
            <input type="number" value="0" id="cel" class="inp">
        </div>
        <div class="input-div">
            <label>Fahrenheit</label><br>
            <input type="number" value="32" id="far" class="inp">
        </div>
        <div>
            <button id="clear">Clear</button>
        </div>
    </div>
    <div id="history">
        <h2>Conversion History</h2>
        <ul id="historyList"></ul>
    </div>
    <script>
        var cel = document.getElementById("cel");
        var far = document.getElementById("far");
        var clearButton = document.getElementById("clear");
        var historyList = document.getElementById("historyList");
        
        clearButton.addEventListener('click', function() {
            cel.value = 0;
            far.value = 32;
        });

        cel.addEventListener('input', function(){
            let c = this.value;
            let f = (c * 9/5) + 32;
            if(!Number.isInteger(f)){
                f = f.toFixed(4);
            }
            far.value = f;
            historyList.innerHTML += `<li>Celsius: ${c} &rarr; Fahrenheit: ${f}</li>`;
        });

        far.addEventListener('input', function(){
            let f = this value;
            let c = (f - 32) * 5/9;
            if(!Number.isInteger(c)){
                c = c.toFixed(4);
            }
            cel.value = c;
            historyList.innerHTML += `<li>Fahrenheit: ${f} &rarr; Celsius: ${c}</li>`;
        });
    </script>
</body>
</html>

