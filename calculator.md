# Water Usage Calculator
Here's a nifty tool to let you figure out how much water you use in a day:
<hr>
<form>
	How long do you generally shower for? <input type="number" name="shower"><br>
	Do you leave the water on while you brush your teeth?
	<select name="brush">
	<option value="y">Yes</option>
	<option value="n">No</option>
	</select><br>
	<button type="submit">Calculate!</button>
</form>
<hr>
You <span>do</span> leave the water on while you shower.
<script>
	var form = document.querySelector("form");
	var span = document.querySelector("span");
	form.addEventListener("submit", function(event) {
		span.value = form.elements.brush.value;
		event.preventDefault();
	});
</script>
