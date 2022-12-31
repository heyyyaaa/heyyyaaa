<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    body{
	margin: 0px;
	padding: 0px;
}
.converter-body{
	width: 400px;
	height: 150px;
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%,-50%);
	box-shadow: 0px 0px 2px 1px #cacaca;
}
.converter-title{
	text-align: center;
	margin: 13px 0px;
	font-size: 40px;
}
input{
	height: 25px;
	text-align: center;
	border: 1px solid black;
}
#input{
	margin-left: 25px;
}
#inputType,#resultType{
	width: 164.66px;
	margin-left: 25px;
	color: red;
	border: 1px solid black;
}
#resultType{
	margin-left: 12.5px;
}
</style>
<body>
    

	<div class="converter-body">
		
		<h1 class="converter-title">Lenght Converter</h1>

		<input type="text" placeholder="Input" id="input">
		<span>=</span>
		<input type="text" placeholder="Result" id="result">


		<select  id="inputType">
			<option value="meter">Meter</option>
			<option value="kilometer">kilometer</option>
			<option value="Centimeter">Centimeter</option>
		</select>

		<select  id="resultType">
			<option value="meter">Meter</option>
			<option value="kilometer">kilometer</option>
			<option value="Centimeter">Centimeter</option>
		</select>



	</div>




</body>

<script>
    var input = document.getElementById('input');
var result = document.getElementById('result');
var inputType = document.getElementById('inputType');
var resultType = document.getElementById('resultType');
var option_from,option_to;

// now add listener
input.addEventListener("keyup",myResult);
inputType.addEventListener("change",myResult);
resultType.addEventListener("change",myResult);

// taking initial value
option_from = inputType.value;
option_to   = resultType.value;


function myResult(){


// when we change the input and output type vale we need to updata the 
// option_from and option_to

	option_from = inputType.value;
	option_to = resultType.value;


// now compare the input and resultType value and add formula

	if(option_from === "meter" && option_to==="kilometer"){
		//this is meter to kilometer formula 
		result.value = Number(input.value) * 0.001;
	}else if(option_from === "meter" && option_to==="Centimeter"){

		//this is meter to Centimeter formula 
		result.value = Number(input.value) * 100;

	}else if(option_from === "meter" && option_to==="meter"){
		//this is meter to meter formula 
		result.value = input.value
	}



	if(option_from === "kilometer" && option_to==="meter"){
		//this is kilometer to meter formula 
		result.value = Number(input.value) * 1000;
	}else if(option_from === "kilometer" && option_to==="Centimeter"){
		//this is kilometer to Centimeter formula 
		result.value = Number(input.value) * 100000;
	}else if(option_from === "kilometer" && option_to==="kilometer"){
		//this is kilometer to kilometer formula 
		result.value = input.value
	}

	if(option_from === "Centimeter" && option_to==="kilometer"){
		//this is Centimeter to kilometer formula 
		result.value = Number(input.value) * 0.00001;
	}else if(option_from === "Centimeter" && option_to==="meter"){
		//this is Centimeter to meter formula 
		result.value = Number(input.value) * 0.01;
	}else if(option_from === "Centimeter" && option_to==="Centimeter"){
		//this is Centimeter to Centimeter formula 
		result.value = input.value
	}
	

}

</script>
</html>
