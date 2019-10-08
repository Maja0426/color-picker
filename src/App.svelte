<script>
let red = 0;
let green = 0;
let blue = 0;
let opa = 1;

$: hex = function(r, g, b) {
	 if (g !== undefined)
        return `#${Number(0x1000000 + r*0x10000 + g*0x100 + b).toString(16).substring(1).toUpperCase()}`;
    else
        return `#${Number(0x1000000 + r[0]*0x10000 + r[1]*0x100 + r[2]).toString(16).substring(1).toUpperCase()}`;
}

function reset() {
	red = 0;
	green = 0;
	blue = 0;
}

</script>

<style>
main {
	width: 100%;
	height: 100%;
}
	.color-tab {
		width: 100%;
		height: 60vh;
	}

	h1 {
		text-align: center;
	}

	.params {
		position: relative;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}

	.light {
		color: #fff;
	}

	.dark {
		color: #000;
	}

.params p {
		font-size: 2.2rem;
		text-align: center;
		margin: 0;
		font-weight: 400;
	}

.wrapper {
	display: flex;
	flex-direction: row;
	width: 100%;
}

.color-box {
	width: 33.333%;
	height: 32px;
	color: #fff;
}

.color-box span {
	display: flex;
	justify-content: center;
	align-content: center;
	padding: 8px;
}

form {
	padding: 0 8px;
	max-width: 800px;
	display: flex;
	flex-direction: row;
	margin: 0 auto;
	justify-content: center;
}

label {
	padding: 10px;
}

input {
	display: block;
	width: 100%;
	margin-top: 10px;
}

input[type=number] {
	margin-top: 2.5rem;
}

.slider {
  -webkit-appearance: none;
  width: 100%;
  height: 5px;
  border-radius: 5px;  
  background: #d3d3d3;
  outline: none;
  opacity: 1;
  -webkit-transition: .2s;
  transition: opacity .2s;
}

.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 25px;
  height: 25px;
  border-radius: 50%; 
  background: #ff3e00;
  cursor: pointer;
}

.slider::-moz-range-thumb {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  background: #ff3e00;
  cursor: pointer;
}

input:hover {
	cursor: pointer;
}

.logo  {
	text-align: center;
}

@media (max-width: 1280px) {

	.logo img {
		width: 100px;
	}

	.color-tab {
		height: 50vh;
	}
}

@media (max-width: 767px) {
	.logo img {
		margin-top: -5px;
		width: 70px;
	}
	.color-tab {
		height: 45vh;
	}
}
	
</style>
<main>
<div class="wrapper">
	<div class="color-box" style="background-color: rgb({red},0,0);"><span>RED</span></div>
	<div class="color-box" style="background-color: rgb(0,{green},0;"><span>GREEN</span></div>
	<div class="color-box" style="background-color: rgb(0,0,{blue};"><span>BLUE</span></div>
</div>
<div class="color-tab" style="background-color: rgb({red}, {green}, {blue}); opacity: {opa}">
	<div class="params {red < 180 && green < 180 && blue < 180 ? 'light' : 'dark'} ">
		<p>{hex(red, green, blue)}</p>
		<p>rgb({red === undefined ? 0 : red},{green === undefined ? 0 : green},{blue === undefined ? 0 : blue})</p>
	</div>
</div>

<h1>COLOR PICKER</h1>

<form>
	<label for="red">Red
	<input class="slider" type="range" min="0" max="255" id="red" step="1" bind:value={red}>
	<input type="number" min="0" max="255" id="red" step="1" bind:value={red}>
</label>
<label for="green">Green
	<input class="slider" type="range" id="green" min="0" max="255" step="1" bind:value={green}>
	<input type="number" id="green" min="0" max="255" step="1" bind:value={green}>
</label>
<label for="blue">Blue
	<input class="slider" type="range" id="blue" min="0" max="255" step="1" bind:value={blue}>
	<input type="number" id="blue" min="0" max="255" step="1" bind:value={blue}>
</label>
<!-- <label for="opacity">Opacity
	<input class="slider" type="range" id="opacity" min="0" max="1" step="0.1" bind:value={opa}>
	<input type="number" id="opacity" min="0" max="1" step="0.1" bind:value={opa}>
</label> -->
</form>
<div class="logo">
	<a href="#" on:click={reset} title="reset"><img src="/img/svelte_logo.png" alt="svelte logo"></a>
</div>
</main>


