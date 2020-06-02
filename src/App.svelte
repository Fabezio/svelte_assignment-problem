<script>
  import Tasks from './Tasks.svelte'
  import Output from './Output.svelte'
  export let name;
	let heading = ""
	let pw =""
	let pwList = []
	let pwlength = "empty"
	// let pwId = 0
	function addPW() {
		// pwId += 1
		if (pw.length < 5) pwlength = "short"
		else if (pw.length > 10) pwlength = "long"
		else {
			pwList = [...pwList, pw]
		} 
	}
	function delPW(index) {
		pwList = pwList.filter((pw, i) => {
			return i !== index

		})
		// if (id === pwList.pwId) {
		// }

	}
  
</script>

<main>
	<!-- <h1>Hello {name}!</h1> -->
	<h1>Assignment</h1>
  <h2>You've got a job here: </h2>

	<p>Solve these tasks.</p>

  <!-- <Tasks /> -->
	<ol>
		<li class="done">Add a password input field and save the user input in a variable.</li>
		<li class="done" >Output "Too short" if the password is shorter than 5 characters and "Too long" if it's longer than 10.</li>
		<li class="done">Output the password in a paragraph tag if it's between these boundaries.</li>
		<li class="done">Add a button and let the user add the passwords to an array.</li>
		<li class="done">Output the array values (= passwords) in a unordered list (ul tag).</li>
		<li class="done">Bonus: If a password is clicked, remove it from the list.</li>
	</ol>


	<!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
  <hr>
  <h3>I've got the solution! </h3>
  <!-- <input type="text" bind:value={heading} > -->
  <!-- <Output {heading}  /> -->
  <input type="password" bind:value={pw} >
	<button on:click={addPW}>add pw</button>
	{#if pwlength === "short"}
	<p class="highlight">password is too short!</p>
	{:else if pwlength === "long"}
	<p class="highlight">password is too long!</p>
	{/if}
	<ul>
	{#each pwList as pw, i}
	<li on:click={delPW.bind(this, i)}>{pw}</li>
	{/each}
	</ul>



</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	li {
		text-align: left;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.highlight {color: red;}
	.done {color: green; text-decoration: line-through;}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>