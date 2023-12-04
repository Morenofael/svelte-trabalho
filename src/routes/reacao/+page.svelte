<script>
	let conta = 0;
	// O sinal $ indica que o código deve ser rodado toda vez que o valor mudar
	$: duplo = conta * 2;
	$: triplo = conta * 3;
	function contarClique() {
		conta += 1;
	}

	$: if (conta == 21) {
		alert(`A conta chegou na idade do professor Jefferson!`);
	}
</script>
<h1>Essa página serve para demonstrar a reatividade do Svelte:</h1>
<button on:click={contarClique}>
	Clicado {conta}
	{conta === 1 ? 'vez' : 'vezes'}
</button>
<p>O número de cliques vezes 2 é {duplo}</p>
<p>O número de cliques vezes 3 é {triplo}</p>
