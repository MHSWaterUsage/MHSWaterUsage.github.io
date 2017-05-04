# Water Usage Calculator
Here's a nifty tool to let you figure out how much water you use in a day:
<hr>
<form>
	How long do you generally shower for? <input type="number" name="shower"> Minutes<br>
	Do you leave the water on while you brush your teeth?
	<select name="brush">
	<option value="y">Yes</option>
	<option value="n">No</option>
	</select><br>
	<button type="submit">Calculate!</button>
</form>
<hr>
<p>
You use <span id="showerResult">--</span> gallons of water while you shower and <span id="brushResult">--</span> gallons while you brush your teeth. This uses <span id="daily">--</span> gallons of water per day, or <span id="yearly">--</span> thousand gallons per year.
</p>
<script>
	var form = document.querySelector("form");
	
	var showerResult = document.getElementById("showerResult");
	var brushResult = document.getElementById("brushResult");
	var daily = document.getElementById("daily");
	var yearly = document.getElementById("yearly");
	form.addEventListener("submit", function(event) {
		var showerGallons = form.elements.shower.value * 2.1;
		var brushGallons = 0;
		if(form.elements.brush.value == "y") {
			brushGallons = 2.5;
		}
		
		showerResult.textContent = showerGallons;
		brushResult.textContent = showerGallons;
		
		var dailyGallons = showerGallons + brushGallons;
		var yearlyGallons = Math.round(36.5 * dailyGallons)*0.01;
		
		daily.textContent = dailyGallons;
		yearly.textContent = yearlyGallons;
		
		event.preventDefault();
	});
</script>
