JavaScript는 리턴 타입이 var 다 똑같아서.. 리턴 type가 따로 없다.

~~~~html
<!DOCTYPE html>
<html>

<head>
	<meta charset="EUC-KR">
	<title>Insert title here</title>
	<style></style>
	<script>
		/*Object Using capital*/
		var Car = {
			name: 'k1',
			size: 1000,
			go: function () {
				return this.name + ' Go';
			},
			stop: function () {
				return this.name + ' Stop';
			}
		};
		var result = Car.go();
		//alert(result)
		//var d = new Data();
		// JavaScript Class
		function Person(name, age) {
			this.name = name;
			this.age = age;
		};
		Person.prototype.print = function () {
			alert(this.name + ' ' + this.age);
		};
		var p1 = new Person('James', 30);
		var p2 = new Person('Tom', 20);
		//p1.print();

		var person = [
			{ id: "id01", name: "kim" },
			{ id: "id02", name: "lee" },
			{ id: "id03", name: "jung" },
			{ id: "id04", name: "hwang" },
			{ id: "id05", name: "oh" }
		];

		function getdata() {
			for (var i in person) {
				person[i].print = function () {
					return '<h2>' + this.id + ' ' + this.name + '</h2>';
				};
			}
			var div = document.getElementById('div');
			var result = '';
			for (var i in person) {
				result += person[i].print();
			}
			div.innerHTML = result;
		};

	</script>
</head>

<body>
	<h1 onclick="getdata();">Click</h1>
	<div id="div"></div>
</body>

</html>
~~~~



###  계산기

~~~~html
<!DOCTYPE html>
<html>

<head>
	<meta charset="UTF-8">
	<title>Insert title here</title>
	<style>

	</style>
	<script>
		var disp = '';
		var put = function(data) {

			var display = document.getElementById('display');
			var result = disp + data;
			disp = result;

			display.value = disp;
		};
		var del = function () {
			disp = '';
			display.value = disp;
		};
		var sol = function () {
			var display = document.getElementById('display');

			try {
				var result = eval(display.value);
			}
			catch (error) {
				msg = "error" + error.message;
				alert(msg);
				disp = '';
			}
			disp = '';

			display.value = result;
		};
	</script>
</head>

<body>
	<table border="1">
		<tr>
			<td colspan="4">
				<input readonly="readonly" type="text" id="display">
			</td>
		</tr>
		<tr>
			<td colspan="4" onclick="del();">C</td>
		</tr>
		<tr>
			<td onclick="put('+');">+</td>
			<td onclick="put('-');">-</td>
			<td onclick="put('*');">x</td>
			<td onclick="put('/');">/</td>
		</tr>
		<tr>
			<td onclick="put(1);">1</td>
			<td onclick="put(2);">2</td>
			<td onclick="put(3);">3</td>
			<td onclick="put(0);">0</td>
		</tr>
		<tr>
			<td onclick="put(4);">4</td>
			<td onclick="put(5);">5</td>
			<td onclick="put(6);">6</td>
			<td rowspan="2" onclick="sol();">=</td>
		</tr>
		<tr>
			<td onclick="put(7);">7</td>
			<td onclick="put(8);">8</td>
			<td onclick="put(9);">9</td>
		</tr>
	</table>
</body>

</html>
~~~~



###  체크박스 선택값 가져오기

~~~~html
<script>
		function add() {
			//var id = document.myform.id.value;
			var id = document.myform.hobby;
			for (var i in id) {
				if (id[i].checked) {
					alert(id[i].value);
				}
			}
		};
	</script>
</head>

<!-- Show Checkbox elements to add() -->

<body>
	<form name="myform">
		ID<input type="text" name="id"><br>
		STUDY
		<input type="checkbox" name="hobby" value="s">
		MUSIC
		<input type="checkbox" name="hobby" value="m">
		TRAINING
		<input type="checkbox" name="hobby" value="t"><br>

		<input type="button" value="ADD" onclick="add();">
	</form>

</body>

</html>
~~~~



###  자판기

~~~~html
<script>
    function add(){
        var display=document.myform.display.value;
        var display2=document.myform.display2.value;
 
        var temp=document.getElementsByName('drink');
        var test ='';
        var count=0;
        for(var i=0; i<temp.length; i++){
            if(temp[i].checked == true){
                count++;
                if(count==1){
                test=document.getElementsByName('drink')[i].value;
                }else{
                    test=test+','+document.getElementsByName('drink')[i].value;
                }
            }
        }
        count=0;
          var target = document.getElementById('pay');
 
         document.myform.display2.value=target.options[target.selectedIndex].value; 
        document.myform.display.value=test
 
    };
</script>
 
 
</head>
<body>
    <form name="myform">
        
        포카리<input type="checkbox" name="drink" id="cb1" value="포카리"> <label for="cb1"></label>
        게토레이<input type="checkbox" name="drink" id="cb2" value="게토레이"><label for="cb2"></label>
        2%<input type="checkbox" name="drink" id="cb3" value="2%"><label for="cb3"></label><br>
        지불방법<select id="pay">
            <option value="카드">카드</option>
            <option value="현금">현금</option>
            <option value="카드/현금" selected disabled hidden>카드/현금</option>
            </select><br>
        <input type="button" value="선택" id="bt" onclick="add();"><br>
        <input readonly="readonly" type="text" id="display"><br>
        <input readonly="readonly" type="text" id="display2">
    </form>
</body>
~~~~

