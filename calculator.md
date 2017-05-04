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
You use <span id="showerResult">--</span> gallons of whater while you shower.
<script>
	var form = document.querySelector("form");
	var showerResult = document.getElementById("showerResult");
	form.addEventListener("submit", function(event) {
		showerResult.textContent = form.elements.shower.value * 2.1;
		event.preventDefault();
	});
</script>
