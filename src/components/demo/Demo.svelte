<script>
	import DemoLink from "$components/demo/Demo.Link.svelte";
	import DemoImg from "$components/demo/Demo.Img.svelte";
	import DemoButtonSet from "$components/demo/Demo.ButtonSet.svelte";
	import DemoRange from "$components/demo/Demo.Range.svelte";
	import DemoSelect from "$components/demo/Demo.Select.svelte";
	import DemoToggle from "$components/demo/Demo.Toggle.svelte";
	import DemoSortTable from "$components/demo/Demo.SortTable.svelte";
	import DemoLayerCake from "$components/demo/Demo.LayerCake.svelte";
	import DemoSvelteElement from "$components/demo/Demo.SvelteElement.svelte";
	import DemoSvelteComponent from "$components/demo/Demo.SvelteComponent.svelte";
	import DemoFigure from "$components/demo/Demo.Figure.svelte";
	import DemoTip from "$components/demo/Demo.Tip.svelte";
	import DemoScrolly from "$components/demo/Demo.Scrolly.svelte";
</script>

<div>
<div id="text-wrapper">
	<h1 id="headline">Language Server Protocols</h1>
	<p id="intro">Code editors these days come with some fancy schmancy features like code completion, syntax <b id="highlight">highlighting</b>, and refactoring routines.</p>

	<p id="p-intro-end">How do language developers support these features? Let's find out.</p>
</div>
	<DemoScrolly />
</div>

<style>

    #text-wrapper {
		position: relative;
    }
	#headline {
		max-width: 40rem;
		margin: auto;
		padding: 2rem;
		color: var(--color-purple);
	}

	#highlight {
		color: var(--category-cyan);
	}


		#p-intro-end {

		max-width: 40rem;
		margin: auto;
		padding: 2rem;
		color: var(--color-purple);
		font-size: var(--24px);
	}

	#intro {
		max-width: 40rem;
		margin: auto;
		padding: 2rem;
		color: var(--color-purple);
		font-size: var(--24px);
	}
</style>