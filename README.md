<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <!-- CSS from Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>
<body>
    <div class="container">
        <div class="card mt-4">
            <div class="card-body">
                <form action="" id="calculateForm">
                    <!-- First Number -->
                <label for="">First Number</label>
                <input type="number" 
                name="" id="num1" 
                class="form-control mt-2" 
                placeholder="Enter First Number">
                <small class="text-danger" id="num1Error">First Number required!</small>
                <br>
                
                <!-- Second Number -->
                <label for="" class="mt-3">Second Number</label>
                <input type="number" 
                name="" id="num2" 
                class="form-control mt-2" 
                placeholder="Enter Second Number">
                <small class="text-danger" id="num2Error">Second Number required!</small>
                <br>

                <!-- Select Operators -->
                <div class="form-group mt-4">
                    <label for="">Select Operators</label>
                    <select name="" id="operators" class="form-control mt-2">
                        <option value="empty">Choose Operator...</option>
                        <option value="add">+</option>
                        <option value="minus">-</option>
                        <option value="multiply">*</option>
                        <option value="division">/</option>
                    </select>
                </div>
                <small class="text-danger" id="operatorsError">Operators required!</small>
                <br>
                </form>
                
                <!-- buttons -->
                <button class="btn btn-dark text-white mt-4" id="btnClaculate" type="button" onclick="calculate()">Calculate</button>
                <button class="btn btn-danger text-white mt-4" id="btnClear" type="button" onclick="clearForm()">Clear</button>
            </div>
                <!-- Result / Footer -->
            <div class="card-footer">
                <label for="" class="mb-4">Result</label>
                <h3 id="result">0</h3>
            </div>
        </div>
    </div>
    <script>
        // Hide error message
        var num1Error = document.getElementById("num1Error");
        var num2Error = document.getElementById("num2Error");
        var operatorsError = document.getElementById("operatorsError");
        var status = true;

        num1Error.style.display = "none";
        num2Error.style.display = "none";
        operatorsError.style.display = "none";

        // result
        var result = document.getElementById("result");

        

        //Get User Input
        function calculate(){
            var num1 = document.getElementById("num1").value;
            var num2 = document.getElementById("num2").value;
            var operators = document.getElementById("operators").value;
            var output;
            
            
            if(num1 == "" || num1 == null){
            num1Error.style.display = "block";
        }else{
            num1Error.style.display ="none";
        }
        
        if(num2 == "" || num2 == null){
            num2Error.style.display = "block";
        }else{
            num2Error.style.display ="none";
        }
       
        if(operators == "empty"){
            operatorsError.style.display = "block";
        }else{
            operatorsError.style.display ="none";
        }

        // Output or Calculate
        
        switch(operators){
            case "add": 
            output = parseInt(num1) + parseInt(num2); break;
            case "minus":
            output = parseInt(num1) - parseInt(num2); break; 
            case "multiply": 
            output = parseInt(num1) * parseInt(num2); break;
            case "division": 
            output = parseInt(num1) / parseInt(num2); break;
        }
        result.innerText = output;
        }





        // Clear 
        var form = document.getElementById("calculateForm");

        function clearForm(){
            form.reset();
        }

    </script>
</body>
</html>
