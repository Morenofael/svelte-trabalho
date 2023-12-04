<script>
	let name = 'Jefferson'; //alterar para demonstrar uso de variavel
	
	import { tweened } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';
	import { fade } from 'svelte/transition';

	const progress = tweened(0, {
		duration: 400,
		easing: cubicOut
	});

	let visivel = true;
</script>

<h1>Olá, {name}!</h1>
<p>O Svelte pode ser usado para facilmente criar componentes visuais para deixar sua aplicação mais <em>bonita</em>. Segue alguns exemplos:</p>
<br>
<progress value={$progress} /><br>
<button on:click={() => progress.set(0)}> 0% </button>
<button on:click={() => progress.set(1)}> 100% </button>
<br><br>

<label>
	<input type="checkbox" bind:checked={visivel} />
	visivel
</label>

{#if visivel}
	<p transition:fade><a href="/reacao">To aparecendo</a></p>
{/if}
<style>
	progress {
		display: block;
		width: 100%;
	}
	em {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
		font-size: 1.5em;
	}
</style>
