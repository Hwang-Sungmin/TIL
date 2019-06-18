~~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
<style></style>
<script>
	function login(f) {

		var id = f.id.value;
		var pwd1 = f.pwd1.value;
		var pwd2 = f.pwd2.value;
		
		var cid = document.getElementById('cid');
		cid.style.color = 'red';
		
		var cpwd = document.getElementById('cpwd');
		cpwd.style.color = 'red';

		if (id == '' || id == null) {
			cid.innerHTML ='ID is Mandatory';

			f.id.focus();
			return;
		}
		if (pwd2 == '' || pwd2 == null) {
			cpwd.innerHTML = "PWD is Mandatory";
			f.pwd2.focus();
			return;
		}
		
		if(pwd1 != pwd2 ){
			cpwd.innerHTML = "PWD is Not equal";
			f.pwd1.focus();
			f.pwd2.focus();
			return;
		}
		else {
			cpwd.innerHTML = "PWD is equal";
			f.pwd1.focus();
			f.pwd2.focus();
			f.submit();
			return;
	}	
};
	/* function show(){
		
		var 
	}
	 */	
</script>
</head>

<!-- span 블럭에 끼어넣는 명령어 -->
<body>
	<form action="Login" method="get"> 
		ID<input type="text" id="id"><span id = cid></span><br>
		PWD<input type="password" id="pwd1"><br> 
		PWD<input type="password" id="pwd2"><span id =cpwd></span><br>
		HINT<select name="HINT">
			<option value="">고향은?</option>
			<option value="">생일은?</option>
		</select><br> 
		HOBBY<input type="radio" name="h" value="">
		TRAIN<input type="radio" name="t" value="">
		STUDY<input type="radio"name="s" value="">
		MUSIC<input type="radio" name="m" value=""><br>
		AGE<input type="number" id="age"><br>
		<input onclick="login(this.form);"
			type="button" value="Login"> 
	</form>
</body>
</html>
~~~~

여러가지 form

~~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
</head>
<body>
	<form>
	<fieldset>ho
	<legend>Employee Register</legend>
	<h1>From List</h1>
	<input type ="hidden" name="geo" value="ffff">
	TEXT <input type="text" name="tx"><br>
	PASSWORD <input type="password" name="pwd"><br>
	
	<label for="male">Male</label>
	<input id ="male" type="radio" name="g" value="m">
	
    Female <input type="radio" name="g" value="f">
	Aje <input type="radio" name="g" value="a">
	<hr>
	
	Apple <input type="checkbox" name="f" value="a">
	Grape <input type="checkbox" name="f" value="g">
	Orange <input type="checkbox" name="f" value="o">
	Melon <input type="checkbox" name="f" value="m">
	<hr>
	
	<select name ="car">
		<option value ="h">Hyndai</option>
		<option value ="k">Kia</option>
		<option value ="s">SSang</option>
		<option value ="c">Chev</option>
		<hr>
		
		File <input type ="file" name="ff">
		<hr>
		
		<input type = "button" value ="Button">
		<hr>

		<input type = "submit" value ="SUBMIT">	
		<hr>
				
		
	</select>
	</fieldset>
	</form>
</body>
</html>
~~~~

dffd