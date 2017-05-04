# Water Usage Calculator
Here's a nifty tool to let you figure out how much water you use in a day:
<hr>
<form>
	How long do you generally shower for? <input type="number" name="shower"><br>
	Do you leave the water on while you brush your teeth?
	<select name="brush">
	<option value="do">Yes</option>
	<option value="don't">No</option>
	</select><br>
	<button type="submit">Calculate!</button>
</form>
<hr>
You <span id="brushResult">do</span> leave the water on while you shower.
<script>
	var form = document.querySelector("form");
	var span = document.getElementById("brushResult");
	form.addEventListener("submit", function(event) {
		span.textContent = form.elements.brush.value;
		event.preventDefault();
	});
</script>
