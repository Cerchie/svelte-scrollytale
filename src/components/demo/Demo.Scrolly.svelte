<script>
	import Scrolly from "$components/helpers/Scrolly.svelte";
	import DemoSelect from "$components/demo/Demo.Select.svelte";
	import FirstGraph from "$components/demo/Demo.FirstGraph.svelte"
	import SecondGraph from "$components/demo/Demo.SecondGraph.svelte"

	let value;
	let arrayOfImgs = [FirstGraph, SecondGraph]

</script>

<section id="scrolly">

	<h2> <span>{value ? value : "The problem" }</span></h2>
	<div class="spacer" />
	<Scrolly bind:value>

		{#each [0,1,2] as text, i}
			{@const active = value === text}
			<div class="step" class:active>

					{#if i == 0}	
						<FirstGraph/>
							{/if}

					{#if i == 1}
                        <SecondGraph/>
                    {/if}

					{#if i == 2}
					<DemoSelect/>
                    {/if}

			</div>
		{/each}
	</Scrolly>
	<div class="spacer" />
</section>

<style>
	h2 {
		position: sticky;
		top: 4em;
		margin-top: 16rem;
		color: var(--color-blue);
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

	.step p {
		padding: 1rem;
	}
</style>
