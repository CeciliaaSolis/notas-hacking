

## Descripción

*How about trying to match a regular expression additional details will be available after launching your challenge instance.*

*How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:56428/)*

## Pistas

*Access the webpage and try to match the regular expression associated with the text field*


## Solución

*HTML y regexr.com*
```
# Inspeccionamos código
<!DOCTYPE html>
<html>

<head>
	<!-- <link rel="stylesheet" href="./index.css" /> -->
	<style>
		.heading {
			width: 100%;
			height: 40px;
			background-color: coral;
			padding-left: 10px;
			font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		}

		.normal-form {
			text-align: center;
			margin-top: 5%;
		}

		#submit-but {
			border-radius: 0;
			width: 250px;
			height: 25px;

		}

		#name {
			width: 250px;
			height: 25px;
			background-color: rgb(241, 226, 206);
		}

		#sub-heading {
			color: brown;
		}
	</style>
</head>

<body>

	<h1 class="heading">PicoCTF</h1>
	<p></p>

	<div class="normal-form">
		<h2 id="sub-heading">Valid Input</h2>
		<form action="#" onsubmit="return send_request()">
			<input type="text" id="name" name="input" placeholder="Input text">
			<br>
			<br>
			<button id="submit-but" type="submit" id="submit-button">SUBMIT</button>
		</form>
	</div>
</body>
<script>
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}

</script>

</html>
# Extraemos donde se encuentra el script ^p.....F!?
#Donde se valida la expresión regular y con ayuda de https://regexr.com/
buscamos posibles valores que coincida con esa entrada donde puede ser lo siguiente. empieza en p, tiene f al final y numeros:
es p12345F!
```

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_35844447}

## Notas Adicionales 

Expresión regular: patrones de busqueda de texto regex

*Despues de tener la respuesta de alguna expresion regular, la insertamos en el campo de la pagina y nos dice submit, nos muestra la bandera.*
*Si queremos evitarnos usar regexr.com,podemos usar chatgpt para que nos diga posibles expresiones regulares.*
## Referencias 

http://saturn.picoctf.net:56428/
https://regexr.com/
