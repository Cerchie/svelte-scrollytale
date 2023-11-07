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
			<div class="img-container">
				<img class="image image-2" src='assets/demo/1stgraphwhitebg.svg' alt="imageofgraph" />
			</div>	
			<p>PLACEHOLDER</p>
		</figure>

		<figure class='sticky'>
			<div class="img-container-2">
				<img class="image image-1" src="assets/demo/1stgraphwhitebg.svg" alt="1">
	
			</div>	

		</figure>
		<p>placeholder</p>
		<!-- TODO-- fade in ON SCROLL -->
<!-- can't move the above ^ into steps because need the CSS classes to be accessible from styles -->
		<!-- {#each steps as text, i}
		<div class="step" class:active={value === i}>
		  <div class="step-content">{@html text}</div>
		</div>
	  {/each} -->

	  <div class="animation-request-container">
	  <div class="request-container">
		
			<div class="request">Request 1</div>
		<div class="request-path">
			<div class="requestBox"></div>
			<div class="client">Client</div>
		</div>
		</div>
		<div class="server">Server</div>
		<div class="request-container">
			<div class="request">Request 2</div>
		<div class="request-path">
			<div class="requestBox"></div>
		</div>
		</div>

		<div class="request-controls">
			<button class="play"> Send</button>
			<button class="pause"> Pause</button>
		</div>
	</div>

	</Scrolly>

	<div class="editorwindow">
		<div class="exit-btn">X</div>
	<span 
	data-text="goToDefinition" 
	class="tooltip"
  >variableName</span> = newValue;</div>
	<div class="spacer" />
</section>

<style>
.exit-btn {
	border: 2px solid black;
	height: 1.5em;
	width: 1.5em;
	margin-top: .5em;
	margin-left: .5em;
	font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	font-weight: 200;
	border-radius: 2px;
	background-color: white;
}
.editorwindow {
	border: 2px solid black;
	border-radius: 2px;
	width: 50%;
	margin: auto;
	text-align: center;
padding-bottom: 1em;
font-family: 'Courier New', Courier, monospace;
font-weight: 700;
background-color: #edebf5;
}
.tooltip {
  position:relative; /* making the .tooltip span a container for the tooltip text */
  border-bottom:1px dashed #000; /* little indicater to indicate it's hoverable */
}

.tooltip:before {
  content: attr(data-text); /* here's the magic */
  position:absolute;
  
  /* vertically center */
  top:50%;
  transform:translateY(-50%);
  
  /* move to right */
  left:100%;
	margin-left: -2em;
  margin-top: -2em;
  
  /* basic styles */
  width:200px;
  padding:10px;
  border-radius:10px;
  background:#000;
  color: #fff;
  text-align:center;

  display:none; 
  /* hide by default */
}

.tooltip:hover:before {
  display:block;
}

/* source: https://blog.logrocket.com/creating-beautiful-tooltips-with-only-css/ */
	
	.request-controls{
		margin: auto;
		margin-top: 3em;
	}

.server {
	margin-top: 1em;
	margin-left: 30em;
	padding-top: .5em;
	background-color: #fce8d7;
	border: 3px solid  black;
	width: 6em;
	height: 3em;
	border-radius: 20px;
	text-align: center;
	color: black;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.client {
	margin-left: -8em;
	margin-top: 1em;
	padding-top: .5em;
	background-color: #edebf5;
	color: black;
	border: 3px solid  black;
	width: 6em;
	height: 3em;
	border-radius: 20px;
	text-align: center;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
.animation-request-container {
	margin: auto;
	padding: 2em;
}
.request {
	margin-bottom: 1em;
	/* text-decoration: var(--category-cyan)  underline;
	text-decoration-style: solid;
	text-decoration-thickness: .1em; */
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
.request-container {
	margin: auto;
	width: 50%;
	padding: 0;
}

.request-controls{
	padding: 4em;
	margin: auto;
	width: 50%;

}
.request-path	{
	height: 1em;
	width: 270px;
	background-color: white;
	margin: .5em;
	align-content: center;
	border:dashed 4px var(--color-gray-200);
	border-top-left-radius: 255px 120px;
      border-top-right-radius: 120px 225px;
      border-bottom-right-radius: 225px 120px;
      border-bottom-left-radius:120px 255px;
}

.requestBox {

  width: 0;
  height: 0;
  margin-top: -.5em;
  margin-left: -.5em;
  border-top: .75em solid transparent;
  border-bottom: .75em solid transparent;
  border-left: 1.25em solid var(--color-purple);

}
.play {
	margin-right: 1em;
	height: 2em;
    color: white; /* Background color */
    background-color: var(--color-purple); /* Text color */
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
	font-size: large;
}

.play:hover {
    color: var(--color-purple); /* Change background color on hover */
    background-color: white; /* Text color */
    border: 1px solid var(--color-purple);
}

.pause {
	margin-left: 1em;
	height: 2em;
    color: white; /* Background color */
    background-color: var(--color-purple); /* Text color */
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
	font-size: large;
}

.pause:hover {
    color: var(--color-purple); /* Change background color on hover */
    background-color: white; /* Text color */
    border: 1px solid var(--color-purple);
}

.img-container {
	align-content: center;

}

.img-container-2 {
	background-image: url('assets/demo/2ndgraphwhitebg.svg');
	background-size: contain;
	background-repeat: no-repeat;
	align-content: center;

}

.image.image-2 {
	margin: auto;
	width: 70vw;
}

.image.image-1 {
	margin: auto;
    animation: fadeOut 3s ease-in-out forwards;
    animation-delay: 5s;
	width: 70vw;

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
