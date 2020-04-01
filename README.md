<!DOCTYPE html>
<html lang="en">

<head>
    <title>Open Hand Sanitizer</title>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"></script>
</head>

<body>

    <div class="container">
        <h1 align='center'>Open Hand Sanitizer</h1>
        <p class="table">
		<tr>
                    <td>Enter Quantity Of Hand Sanitizer You Want To Make (in ml)</td>
					<td>
                        <input type="number" id="amount" value='1'></td>
                    <td></td>
                </tr>
		</p>
        <table class="table table-bordered">
		
            <thead>
                <tr>
                    <th>Ingredients</th>
                    <th>Strength</th>
                    <th>How Much To Use</th>
                </tr>
            </thead>
            <tbody>
                
                <tr>
                    <td>Isopropyl Alcohol</td>
                    <td><select id="list">
                            <option value="0">
                                select
                            </option>
							<option value=".75">
                                99
                            </option>
                            <option value=".83">
                                91
                            </option>
							<option value="55">
                                70
                            </option>
							<option value="55">
                                60
                            </option>
                        </select></td>
                    <td><span id="ans"></span></td>
                </tr>
                <tr>
                    <td>Hydrogen Peroxide</td>
                    <td><select id="list2">
                           <option value="0">
                                Select
                            </option>
						   <option value=".04">
                                3
                            </option>
                            <option value=".02">
                                6
                            </option>
                            
                        </select></td>
                    <td><span id="ans2"></span></td>
                </tr>
                <tr>
                    <td>Glycerine</td>
                    <td></td>
                    <td><span id="ans3"></span></td>
                </tr>
                <tr>
                    <td>Water (to make it total)</td>
                    <td></td>
                    <td><span id="ans4"></span></td>
                </tr>
            </tbody>
        </table>
    </div>

</body>

</html>

<script>
    function op1() {
        a = parseFloat($("#list").val());
        c = parseFloat($("#amount").val());
		
		if (a==.75){
		ans1 = a * c;}
		else if(a==.83){
		ans1 = a * c;}
		else if(a==55){
		ans1 = c - a;}
		else if(a==55){
		ans1 = c - a;}
		
		
        //ans1 = a * c;
        $("#ans").html(ans1)
        TOTAL();
    }

    function op2() {
        a = parseFloat($("#list2").val());
        c = parseFloat($("#amount").val());
        ans2 = a * c;
        $("#ans2").html(ans2)
        TOTAL();
    }

    function op3() {
        a = parseFloat($("#amount").val());
        c = 0.015

        ans3 = a * c;
        $("#ans3").html(ans3)
        op1();
        op2();

        TOTAL();
    }

    function TOTAL() {
        an = parseFloat($("#amount").val()) - ans1 - ans2 - ans3;
        $("#ans4").html(an)
    }
    $(document).ready(function() {
        $("#list").on("change", function() {
            op1();
        });
        $("#list2").on("change", function() {
            op2();
        });
        $("#amount").on("input", function() {
            op3();
        });
    });

</script>


<!--Label10.Text = a * .015-->
