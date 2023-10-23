<script>
	import Scrolly from "$components/helpers/Scrolly.svelte";
	import DemoSelect from "$components/demo/Demo.Select.svelte";
	import DemoTip from "$components/demo/Demo.Tip.svelte";
	import DemoButtonSet from "$components/demo/Demo.ButtonSet.svelte";

	let value;

</script>

<section id="scrolly">

	<h2>Scrolly <span>{value ? value : "ScrollyTitle" }</span></h2>
	<div class="spacer" />
	<Scrolly bind:value>

		{#each [0,1,2] as text, i}
			{@const active = value === i}
			<div class="step" class:active>
			        {#if i == 0}
                        <DemoSelect/>
                    {/if}
					{#if i == 1}
                        <DemoTip/>
	
                    {/if}
					{#if i == 2}
                        <DemoButtonSet/>
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
	}

	.spacer {
		height: 75vh;
	}

	.step {
		height: 80vh;
		background: var(--color-gray-100);
		text-align: center;
	}

	.step p {
		padding: 1rem;
	}
</style>
