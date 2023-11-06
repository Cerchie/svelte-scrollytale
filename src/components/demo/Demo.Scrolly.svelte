<script>
	import Scrolly from "$components/helpers/Scrolly.svelte";
	import {onMount} from 'svelte'
	import anime from 'animejs';
	// https://blog.hubspot.com/website/css-animate-on-scroll

	let value;
	let steps = [
    `The Language Server Protocol reduces complexity by diminishing the need for each language to cater to each editor.
	`,
    `step 2`,
  ];

  onMount(() => {
		
			var animation = anime({
			targets:  '.requestBox',
			keyframes: [
				{translateX: 270},
				{rotateY: 180},
				{translateX: -27},
			],	
			delay: function(el, i) { return i * 300; },
			direction: 'normal',
			loop: false,
			autoplay: false,
			easing: 'easeInOutSine',
			duration: 4000
		});
		
	document.querySelector('.request-controls .play').onclick = animation.play;
	document.querySelector('.request-controls .pause').onclick = animation.pause;
	

});



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
		<!-- TODO-- fade in ON SCROLL -->
<!-- can't move the above ^ into steps because need the CSS classes to be accessible from styles -->
		{#each steps as text, i}
		<div class="step" class:active={value === i}>
		  <div class="step-content">{@html text}</div>
		</div>
	  {/each}

	  <p class="step">TRYING SOMETHING</p>
	  <div class="animation-request-container">
	  <div class="request-container">
			<div class="client">Client</div>
		<div class="request-path">
			<div class="requestBox"></div>
		</div>
		</div>
		<div class="server">Server</div>
		<div class="request-container">
			<div class="client">Client</div>
		<div class="request-path">
			<div class="requestBox"></div>
		</div>
		</div>

		<div class="request-controls">
			<button class="play"> Send client requests</button>
			<button class="pause"> Pause</button>
		</div>
	</div>
	
	</Scrolly>

	<div class="spacer" />
</section>

<style>

.server {
	margin-left: 30em;
	background-color: aqua;
	width: 6em;
	height: 4em;
}
.animation-request-container {
	margin: auto;
}

.request-container {
	margin-left: 10em;

}
.request-path	{
	height: 20px;
	width: 270px;
	background-color: var(--color-gray-200);
	margin: .5em;
}

.requestBox {

	width: 0;
  height: 0;
  border-top: 20px solid transparent;
  border-bottom: 20px solid transparent;
  border-left: 30px solid blue;
  display: inline-block;
  padding: 3px;
  
}
.play {
    background-color: white; /* Background color */
    color: var(--color-purple); /* Text color */
    border: 3px solid var(--color-purple);
    padding: 10px 20px;
    border-radius: 10px; 
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: Playfair Display;
	font-size: x-large;
}

.play:hover {
    background-color: var(--color-purple); /* Change background color on hover */
    color: white; /* Text color */
    border: 3px solid var(--color-purple);
}

.pause {
    background-color: white; /* Background color */
    color: var(--color-purple); /* Text color */
    border: 3px solid var(--color-purple);
    padding: 10px 20px;
    border-radius: 10px; 
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: Playfair Display;
	font-size: x-large;
}

.pause:hover {
    background-color: var(--color-purple); /* Change background color on hover */
    color: white; /* Text color */
    border: 3px solid var(--color-purple);
}

.img-container {
	background-image: url('assets/demo/2ndgraphwhitebg.svg');
	background-size: contain;
	background-repeat: no-repeat;
}


.image.image-1 {
    animation: fadeOut 3s ease-in-out forwards;
    animation-delay: 0.5s;
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
		padding: 1em;
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
