<script>
	import Quiz from "./components/Quiz.svelte";
	import Setup from "./components/Setup.svelte";
	import Results from "./components/Results.svelte";
	import { hasQuizBegun, isQuizDone } from "./data/store.js";
</script>

<style>
	:global(body) {
    	background-image: url(https://quo.mx/wp-content/uploads/2023/08/porque-es-importante-conocer-la-historia-de-nuestro-pais.webp);
		background-repeat: no-repeat;
		background-attachment: fixed;
		background-position: center;
		background-size: cover;
		color: #FFFFFF;
		font-family: "Poppins", sans-serif;
	}
	:global(label:hover) {
		background: #AEE2FF;
	}
	:global(button) {
		box-sizing: border-box;
		margin: 1em 0;
		background: #e5e0ff;
		color: black;
		cursor: pointer;
		border: 3px solid dodgerblue;
		padding: 1em 0;
		font-size: 0.9em;
		transition: 0.2s all;
		width: 100%;
		border-radius: 25px;
	}
	:global(button:hover, button:focus) {
		transform: scale(1.05);
		background: #AEE2FF;
    	color: darkblue;
	}
	:global(button:active) {
		background: #FFFFFF;
		color:  rgb(39,116,174);
		transform: scale(1);
	}
	main {
		font-size: 30px;
		margin: 0 auto;
		max-width: 600px;
		text-align: center;
		padding: 5px 20px;
		background: #e5e0ff;
		opacity: 0.8;
		border-radius: 30px;
	}
	@media only screen and (max-width: 600px) {
		main {
			font-size: 24px;
		}
	}
</style>

<main>
	{#if $hasQuizBegun}
		<Quiz />
	{:else if $isQuizDone}
		<Results />
	{:else}
		<Setup />
	{/if}
</main>
