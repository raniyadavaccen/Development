# Development
Develop one basic calculator using HTML,CSS and Javascript

HTML file

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Basic Calculator</title>
    <link rel="stylesheet" href="calculator.css" />

  </head>
  <body>
  
        <!-- Create table -->
        <div class="buttons">
        <table id="calcu"> 
            <tr> 
                <td colspan="3"> 
                    <input type="text" id="result"> 
                </td> 
                <td><input type="button" value="AC" id="clear"></td> 
            </tr> 
      
            <tr> 
                <td><input type="button" value="9" id="num"></td> 
                <td><input type="button" value="8" id="num"></td> 
                <td><input type="button" value="7" id="num"></td> 
                <td><input type="button" value="+" id="operator"></td> 
            </tr> 
            <tr> 
                <td><input type="button" value="4" id="num"></td> 
                <td><input type="button" value="5" id="num"></td> 
                <td><input type="button" value="6" id="num"></td> 
                <td><input type="button" value="-" id="operator"></td> 
            </tr> 
            <tr> 
                <td><input type="button" value="1" id="num"></td> 
                <td><input type="button" value="2" id="num"></td> 
                <td><input type="button" value="3" id="num"></td> 
                <td><input type="button" value="/" id="operator"></td> 
            </tr> 
            <tr> 
                <td><input type="button" value="." id="num"></td> 
                <td><input type="button" value="0" id="num"></td> 
                <td><input type="button" value="=" id="num"></td> 
                <td><input type="button" value="*" id="operator"></td> 
            </tr> 
        </table>
        </div>
        <script src="Calculator.js"></script>

  </body>
</html>
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

CSS File
table { 
    border: 1px solid black; 
    margin-left: auto; 
    margin-right: auto; 
} 
  
input[type="button"] { 
    width: 100%; 
    padding: 20px 40px; 
    background-color: black; 
    color: white; 
    font-size: 24px; 
    font-weight: bold; 
    border: none; 
} 
  
input[type="text"] { 
    padding: 20px 30px; 
    font-size: 24px; 
    font-weight: bold; 
    border: none; 
    border: 2px solid black; 
} 

#num {
  background-color: black;
  border:none;
}

#operator{
    background-color: grey;
}

#clear{
    background-color:rgb(18, 121, 94);
}

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Javascript File
document.addEventListener("DOMContentLoaded", function () {
    // Get elements
    const resultField = document.getElementById("result");
    const buttons = document.querySelectorAll(".buttons input");

    // Add click event listeners to the buttons
    buttons.forEach((button) => {
        button.addEventListener("click", function () {
            const buttonValue = button.value;

            if (buttonValue === "=") {
                try {
                    resultField.value = eval(resultField.value);
                } catch (error) {
                    resultField.value = "Error";
                }
            } else if (buttonValue === "AC") {
                resultField.value = "";
            } else {
                resultField.value += buttonValue;
            }
        });
    });
});
