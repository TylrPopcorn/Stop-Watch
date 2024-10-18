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
	let secondsElapsed = 0;
	let interval = null;

	//Functions:---------
	const stopClock = function(){

	}

	const startClock = function(){

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
  <section class="section has-text-centered">
    <div class="container">
      <div class="stopwatch-wrapper">
        <h3 id="time" class="subtitle is-size-1 has-text-weight-bold has-text-primary">
          00:00
        </h3>
      </div>
      <div class="buttons is-centered">
        <button class="button is-primary" on:click={startClock}>Start</button>
        <button class="button is-warning" on:click={stopClock}>Stop</button>
        <button class="button is-danger" on:click={resetClock}>Reset</button>
      </div>
    </div>
  </section>
</main>
<Footer />

<!-- CSS -->
<style>
  .stopwatch-wrapper {
    display: inline-block;
    padding: 30px;
    background-color: rgba(0, 0, 0, 0.8); /* Semi-transparent background */
    border-radius: 15px;
    border: 5px solid #00d1b2; /* Neon turquoise border */
    box-shadow: 0 0 20px rgba(0, 209, 178, 0.8); /* Neon glow effect */
  }


</style>