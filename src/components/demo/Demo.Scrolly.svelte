<script>
	import Scrolly from "$components/helpers/Scrolly.svelte";

	let value;

	let scrollPosition = 0;

	function handleScroll() {
	scrollPosition = window.scrollY;
	}

	let steps = [
    `step 1
	`,
    `step 2`,
  ];
</script>

<section id="scrolly" >

	<div class="spacer" />

	<Scrolly bind:value>


		<figure class='sticky'>
			<div style={{width: '100%', overflow: 'auto'}} class="img-container">
				<img src='assets/demo/firstgraph.svg' alt="imageofgraph" class="fixed-image"/>
			</div>	
		</figure>

		{#each steps as text, i}
		<div class="step" class:active={value === i}>
		  <div class="step-content">{@html text}</div>
		</div>
	  {/each}
	</Scrolly>
	<div class="spacer" />
</section>

<style>

figure.sticky {
  position: -webkit-sticky;
  position: sticky;
  top: 0;
}
	.spacer {
		height: 75vh;
	}

	.step {
		height: 80vh;
		width: 100vw;
		background: var(--color-white);
		text-align: center;
	}

	.step div {
		padding: 1rem;
		animation: fadeIn 7s;
	}

	@keyframes fadeIn {
	0% { opacity: 0; }
	100% { opacity: 1; }
	}

	@keyframes fadeOut {
	0% { opacity: 1; }
	100% { opacity: 0; }
	}
</style>
