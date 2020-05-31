<script>
  import Tasks from './Tasks.svelte'
  import Output from './Output.svelte'
  export let name;
  let heading = ""
  
</script>

<main>
	<h1>Hello {name}!</h1>
  <h2>You've got a job here: </h2>
  <Tasks />

	<!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
  <hr>
  <h3>I've got the solution! </h3>
  <input type="text" bind:value={heading} >
  <Output {heading}  />

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>