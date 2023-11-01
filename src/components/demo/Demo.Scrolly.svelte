<script>
	import Scrolly from "$components/helpers/Scrolly.svelte";

	// https://blog.hubspot.com/website/css-animate-on-scroll
	let value;

	let steps = [
    `step 1
	`,
    `step 2`,
  ];
</script>

<section id="scrolly" >

	<div class="spacer" />

	<Scrolly bind:value>
		<figure>
			<div style={{width: '100%', overflow: 'auto'}} class="img-container">
				<img src='assets/demo/1stgraphwhitebg.svg' alt="imageofgraph" />
			</div>	
			<p>PLACEHOLDER</p>
		</figure>

		<figure class='sticky'>
			<div style={{width: '100%', overflow: 'auto'}} class="img-container">
				<img src='assets/demo/1stgraphwhitebg.svg' alt="imageofgraph"/>
			</div>	
		</figure>
<!-- need to fade this one into 2nd image  -->

		{#each steps as text, i}
		<div class="step" class:active={value === i}>
		  <div class="step-content">{@html text}</div>
		</div>
	  {/each}
	</Scrolly>
	<div class="spacer" />
</section>

<style>

/* https://stackoverflow.com/questions/17690669/fade-image-at-the-top */


figure.sticky {
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  animation: fadeOut 5s;
}
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
	100% { opacity: .5; }
	}
</style>
