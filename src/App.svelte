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
  let minutes = 0;
  let milliseconds = 0;
  let interval;
  let clockActive = false;
  let color = "#ffdd57"; // Default color for initial state

	//Functions:---------
	const stopClock = function(){
    //Will stop the clock time without resetting.
    clearInterval(interval);
    clockActive = false;
    color = "#ffdd57"

	}

	const startClock = function(){
    //Will start the clock time
    if (clockActive === false){
      clockActive = true;
      color = "#4edbc4";

       // Update every 10 milliseconds
      interval = setInterval(() => {
          milliseconds += 10;

      if (milliseconds >= 1000) {
        milliseconds = 0;
        seconds++;
      }

      if (seconds >= 60) {
        seconds = 0;
        minutes++;
      }
      }, 10); // Runs every 10 ms for precise updates
	 }
}

	const resetClock = function(){
    //Will reset the clock time.
    clearInterval(interval);
    milliseconds = 0;
    minutes = 0;
    seconds = 0;
    clockActive = false;
    color = "#ff3860";
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
        <p class="title / has-text-weight-bold " style="
         border: 5px solid {color};  box-shadow: 0 0 20px {color}, inset 0 0 20px rgba(0, 0, 0, 0.2); color: {color}">
          <span class="minutes">{minutes < 10 ? `0${minutes}` : minutes}:</span>
          <span class="seconds">{seconds < 10 ? `0${seconds}` : seconds}:</span>
          <span class="milliseconds">
            {milliseconds < 10 ? `00${milliseconds}` : milliseconds < 100 ? `0${milliseconds}` : milliseconds}
          </span>
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
  
  margin-bottom: 5%;
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

    background-color: #172220;
  
    border-radius: 50%; /* Makes the div a circle */

    text-align: center;
    overflow: hidden;

    font-size: clamp(1.5rem, 2vw + 1rem, 5rem);
}
</style>