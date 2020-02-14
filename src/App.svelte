<script>
let red = 0;
let green = 0;
let blue = 0;

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
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 60vh;
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

	.author {
		position: relative;
		text-align: center;
	}

	.author a {
		color: #000;
	}

	svg {
		width: 42px;
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

@media (max-width: 1366px) {

	.logo img {
		width: 100px;
	}

	.color-tab {
		height: 50vh;
	}
}

@media (max-width: 767px) {
	.params {
		height: 50vh;
	}
	.logo img {
		margin-top: -5px;
		width: 70px;
	}
}

@media (max-width: 360px) {
	h1 {
		font-size: 26px;
	}
	.author {
		font-size: 14px;
	}
	.logo img {
		width: 50px;
	}
	
}
	
</style>
<main>
<div class="wrapper">
	<div class="color-box" style="background-color: rgb({red},0,0);"><span>RED</span></div>
	<div class="color-box" style="background-color: rgb(0,{green},0;"><span>GREEN</span></div>
	<div class="color-box" style="background-color: rgb(0,0,{blue};"><span>BLUE</span></div>
</div>
<div class="color-tab" style="background-color: rgb({red}, {green}, {blue});">
	<div class="params {red < 180 && green < 180 && blue < 180 ? 'light' : 'dark'} ">
		<p>{hex(red, green, blue)}</p>
		<p>rgb({red === undefined ? 0 : red},{green === undefined ? 0 : green},{blue === undefined ? 0 : blue})</p>
		{#if hex(red, green, blue) === '#FFFFFF'}
			<div class="author">
		<h4>Created:<br>Tamas Majoros</h4>
		<h4>Web:<br><a href="https://smartbeeweb.hu" target="_blnk" rel="noreferrer">SmartBee</a></h4>
		<a href="https://github.com/Maja0426/color-picker" target="_blank" rel="noreferrer"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><title>https://github.com/Maja0426/color-picker</title><g id="Github_2" data-name="Github 2"><g id="_Group_" data-name="&lt;Group&gt;"><path id="_Compound_Path_" data-name="&lt;Compound Path&gt;" d="M12,10.72H12c-3,0-5.6-.83-7.15.74a4.54,4.54,0,0,0-1.32,3.3c0,5.11,3.71,5.74,8.46,5.74H12c4.76,0,8.46-.63,8.46-5.74a4.54,4.54,0,0,0-1.32-3.3C17.63,9.89,15,10.72,12,10.72ZM14.17,22.5H9.83C8,22.5.5,22.34.5,12.67A7.61,7.61,0,0,1,2.37,7.46a12.82,12.82,0,0,1,.79-6s2.26.27,5.69,2.8A12.59,12.59,0,0,1,12,4a12.58,12.58,0,0,1,3.15.32c3.43-2.53,5.69-2.8,5.69-2.8a12.82,12.82,0,0,1,.79,6,7.61,7.61,0,0,1,1.87,5.21C23.5,22.34,16,22.5,14.17,22.5Zm3.33-7c0,1.66-.67,3-1.5,3s-1.5-1.34-1.5-3,.67-3,1.5-3S17.5,13.84,17.5,15.5Zm-8,0c0,1.66-.67,3-1.5,3s-1.5-1.34-1.5-3,.67-3,1.5-3S9.5,13.84,9.5,15.5Z" style="fill:303c42;stroke:#303c42;stroke-linecap:round;stroke-linejoin:round"/></g></g>
	<metadata>
		<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#" xmlns:dc="http://purl.org/dc/elements/1.1/">
			<rdf:Description about="https://iconscout.com/legal#licenses" dc:title="social; media; social media; logo; github; 2" dc:description="social; media; social media; logo; github; 2" dc:publisher="Iconscout" dc:date="2017-02-21" dc:format="image/svg+xml" dc:language="en">
				<dc:creator>
					<rdf:Bag>
						<rdf:li>Alpár - Etele Méder</rdf:li>
					</rdf:Bag>
				</dc:creator>
			</rdf:Description>
		</rdf:RDF>
    </metadata></svg></a>
	</div>
		{/if}
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
</form>
<div class="logo">
	<a href="." on:click|preventDefault={reset} title="reset"><img src="/img/svelte_logo.png" alt="svelte logo"></a>
</div>
</main>


