<script>
	import Scrolly from "$components/helpers/Scrolly.svelte";

	// https://blog.hubspot.com/website/css-animate-on-scroll
	let value;

	let steps = [
    `The Language Server Protocol reduces complexity by diminishing the need for each language to cater to each editor.
	`,
    `step 2`,
  ];
</script>

<section id="scrolly" >

	<div class="spacer" />

	<Scrolly bind:value>
		<figure>
			<div style={{width: '100%', overflow: 'auto'}}>
				<img src='assets/demo/1stgraphwhitebg.svg' alt="imageofgraph" />
			</div>	
			<p>PLACEHOLDER</p>
		</figure>

		<figure class='sticky'>
			<div style={{width: '100%', overflow: 'auto'}} class="img-container">
				<img class="image image-1" src="assets/demo/1stgraphwhitebg.svg" alt="1">
			</div>	
		</figure>
<!-- need to fade this one into 2nd image  -->

		{#each steps as text, i}
		<div class="step" class:active={value === i}>
		  <div class="step-content">{@html text}</div>
		</div>
	  {/each}

	  <p class="step">TRYING SOMETHING</p>
	</Scrolly>
	<div class="spacer" />
</section>

<style>


.img-container {
	background-image: url('assets/demo/2ndgraphwhitebg.svg');
	background-size: contain;
}


.image.image-1 {
    animation: fadeOut 3s ease-in-out forwards;
    animation-delay: 0.5s;
}

/* figure.sticky {
  position: -webkit-sticky;
  position: sticky;
  top: 0;
}
  /* animation: fadeOut 5s; */
 /* styles for parallaz scroll */

	.spacer {
		height: 25vh;
	}

	.step {
		height: 80vh;
		width: 100vw;
		background: var(--color-white);
		text-align: center;
	}

	.step div {
		padding: 1rem;
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
