# Water Usage Calculator
Here's a nifty tool to let you figure out how much water you use in a day:
<hr>
<form id="calc" method="post">
	How long do you generally shower for? <input type="number" name="shower"> Minutes<br>
	Do you leave the water on while you brush your teeth?
	<select name="brush">
		<option value="y">Yes</option>
		<option value="n">No</option>
	</select><br>
	How many times do you flush the toilet each day? <input type="number" name="flush"><br>
	Did you buy a new toilet in the last 5 years?
	<select name="toiletAge">
		<option value="y">Yes</option>
		<option value="n">No</option>
	</select><br>
	<button type="submit">Calculate!</button>
</form>
<hr>
<p>
You use <span id="showerResult">--</span> gallons of water while you shower and <span id="brushResult">--</span> gallons while you brush your teeth. You also use <span id="flushResult">--</span> gallons flushing the toilet each day. This uses <span id="daily">--</span> gallons of water per day, or <span id="yearly">--</span> thousand gallons per year.
</p>
<p>
The above calculations are for what is called domestic water use. This may seem like a large number, but your actual water footprint is roughly ten times larger, or <span id="adjustedYearly">--</span> thousand gallons per year. This increase is due to the large water consumption of agriculture and industry that make the pruducts you use every day. This figure should be taken as an estimate, as many of the figures related to "invisible water" are difficult to calculate, but you can find out more under 'Further Readings'. If everyone on earth used as much water as you did, we would need about <span id="worldsNeeded">--</span> earths to sustain us all.
</p>
<script>
var form = document.getElementById("calc");
var debug = true;

var showerResult = document.getElementById("showerResult");
var brushResult = document.getElementById("brushResult");
var flushResult = document.getElementById("flushResult");
var daily = document.getElementById("daily");
var yearly = document.getElementById("yearly");
var adjustedYearly = document.getElementById("adjustedYearly");
var worldsNeeded = document.getElementById("worldsNeeded");
function handleForm(e) {
	if(debug) {
		alert("submitted!");
	}
	var showerGallons = form.elements.shower.value * 2.1;
	var brushGallons = 0;
	if(form.elements.brush.value == "y") {
		brushGallons = 2.5;
	}
	var galPerFlush = 3.5;
	if(form.elements.toiletAge.value == "y") {
		galPerFlush = 1.6;
	}
	var flushGallons = galPerFlush * form.elements.flush.value;
	
	showerResult.textContent = showerGallons;
	brushResult.textContent = brushGallons;
	flushResult.textContent = flushGallons;
	
	var dailyGallons = showerGallons + brushGallons + flushGallons;
	var yearlyGallons = Math.round(36.5 * dailyGallons)*0.01;
	var yearlyAjdusted = Math.round(365 * dailyGallons)*0.01;
	var earths = Math.round(yearlyAdjusted * 7 / 23.8) * 0.1;
	
	daily.textContent = dailyGallons;
	yearly.textContent = yearlyGallons;
	adjustedYearly.textContent = yearlyAdjusted;
	earthsNeeded.textContent = earths;
	
	e.preventDefault();
	if(debug && e.isDefaultPrevented()) {
		alert("sucess");
	}
	return false;
}
form.addEventListener("submit", handleForm(event));
</script>


<hr>
[Home](index.html)
