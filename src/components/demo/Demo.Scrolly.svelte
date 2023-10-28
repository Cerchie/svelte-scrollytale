<script>
	import Scrolly from "$components/helpers/Scrolly.svelte";
	import DemoSelect from "$components/demo/Demo.Select.svelte";
	import DemoTip from "$components/demo/Demo.Tip.svelte";
	import { fade } from "svelte/transition";
	import DemoButtonSet from "$components/demo/Demo.ButtonSet.svelte";
	import DemoFadingGraph from "$components/demo/Demo.FadingGraph.svelte"
	let value;
	let list = [1, 2, 3]

</script>

<section id="scrolly">

	<h2> <span>{value ? value : "The problem" }</span></h2>
	<div class="spacer" />
	<Scrolly bind:value>

		{#each [0,1,2] as text, i}
			{@const active = value === i}
			<div class="step" class:active>
			        {#if i == 0}
					{#key list}
	<div in:fade={{ duration: 1000 }}>
		{#each list as item}
			<div>{item}</div>
		{/each}
	</div>
{/key}
<div>
	<button on:click={() => list = [...list, list.length + 1]}>
		Add Item
	</button>
</div>
                    {/if}
					{#if i == 1}
                        <DemoTip/>
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
