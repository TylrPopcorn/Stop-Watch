<!-- DEPENDENCIES -->
<!-- npm i degit -->
<!-- npm install -->


<!-- How to create a new svelte project: -->
<!-- degit sveltejs/template [project-name]-->

<!-- alternative way -->
<!-- npx degit sveltejs/template [project-name] -->
<!---------------------------------------------->

<!-- HOW TO START SERVER: -->
<!-- npm run build -->
<!-- npm run dev -->


<!-- JAVASCRIPT -->
<script>
	//Imports:------
	import Header from "./Components/Header.svelte";
  import Footer from "./Components/Footer.svelte";


	//Variables:----
	let seconds = 0;
  let tens = 0;
  let milliseconds = 0;
  let interval;
  let clockActive = false;

	//Functions:---------
	const stopClock = function(){
    clockActive = false;
	}

	const startClock = function(){
    if (clockActive === false){
      clockActive = true;

      milliseconds += 10;

      if (milliseconds >= 1000) {
        milliseconds = 0;
        tens++;
      }
      if (tens > 99) {
        tens = 0;
        seconds++;
      }
      if (seconds > 59) {
        seconds = 0;
      }
      updateDisplay();
    }
	}

	const resetClock = function(){

	}
</script>

<!-- HTML -->
<svelte:head>
  <!-- Bulma CSS Import -->
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/bulma.min.css"
  />
</svelte:head>
<Header />
<main>
  <section class="section / has-text-centered">
    <div class="container">
      <div class="stopwatch-wrapper">
        <p class="subtitle / is-size-1 / has-text-weight-bold / has-text-warning">
          <span class="seconds">{seconds == 0 ? "00": seconds}:</span>
          <span class="tens">{tens == 0 ? "00" : tens}:</span>
          <span class="milliseconds">{milliseconds == 0 ? "00" : milliseconds}</span>
        </p> 
        <br>
      </div>
      <div class="buttons / is-centered">
        <button class="button / is-primary" on:click={startClock}>Start</button>
        <button class="button / is-warning" on:click={stopClock}>Stop</button>
        <button class="button / is-danger" on:click={resetClock}>Reset</button>
      </div>
    </div>
  </section>
</main>
<Footer />
 
<!-- CSS -->
<style>
 .stopwatch-wrapper{
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 2%;
}

.stopwatch-wrapper p{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 20vw; /* Size scales based on viewport width */
    height: 20vw;
    min-width: 200px; /* Minimum size */
    min-height: 200px;
    max-width: 800px; /* Doubled the max width from 400px to 800px */
    max-height: 800px; /* Doubled the max height from 400px to 800px */
    background-color: #171722;
    border-radius: 50%; /* Makes the div a circle */
    border: 5px solid #d19900; /* Neon border */
    box-shadow: 
      0 0 20px rgba(209, 125, 0, 0.8),    
      inset 0 0 20px rgba(0, 0, 0, 0.2); 

    text-align: center;
    overflow: hidden;
}


</style>