# Water Usage Calculator
Here's a nifty tool to let you figure out how much water you use in a day:
<hr>
<form>
	How long do you generally shower for? <input type="number" name="shower"><br>
	Do you leave the water on while you brush your teeth?
	<select name="brush">
	<option value="y">Yes</option>
	<option value="n">No</option>
	</select>
	
</form>
<script>
	var form = document.querySelector("form");
	form.addEventListener("submit", function(event) {
		console.log("Saving value", form.elements.brush.value);
		event.preventDefault();
	});
</script>
