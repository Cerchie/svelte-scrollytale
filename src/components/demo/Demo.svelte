<script>
	import DemoScrolly from "$components/demo/Demo.Scrolly.svelte";
</script>

<div>
<div id="text-wrapper">
	<h1 id="headline">Language Server Protocols</h1>
	<p id="intro">Code editors these days come with some fancy schmancy features like code comple<span class="tion">tion</span><span class="bar">|</span>, syntax <b id="highlight">highlighting</b>, and refactoring routines.</p>

	<p id="p-intro-end">How do language developers support these features? Let's find out.</p>
</div>
	<DemoScrolly />
</div>

<style>
	.tion {
		animation: fadeIn 3s;
	}
	.bar {
		animation: blinkIn 1.5s steps(5, start) infinite;
	}

    #text-wrapper {
		position: relative;
    }

	@keyframes fadeIn {
		0% { opacity: 0; }
		100% { opacity: 1; }
		}
	@keyframes blinkIn {
	to {
		visibility: hidden;
	}
	}




	#headline {
		max-width: 40rem;
		margin: auto;
		padding: 2rem;
		color: var(--color-blue);
	}

	#highlight {
		color: var(--category-cyan);
	}

	#p-intro-end {

		max-width: 40rem;
		margin: auto;
		padding: 2rem;
		color: var(--color-blue);
		font-size: var(--24px);
	}

	#intro {
		max-width: 40rem;
		margin: auto;
		padding: 2rem;
		color: var(--color-blue);
		font-size: var(--24px);
	}
</style>