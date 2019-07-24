<script>
import SimpleTagPicker from './SimpleTagPicker.svelte';
import Code from './Code.svelte';
let tags = ['Testing', 'Svelte'];
</script>

<style>
code {
	font-family: "Operator Mono Lig", "Operator Mono", "Fira Code", Menlo, Consolas, "Courier New", monospace;
}
pre {
	background-color: hsl(210, 5%, 80%);
	padding: 1rem;
	border-radius: 0.5rem;
	font-family: "Operator Mono Lig", "Operator Mono", "Fira Code", Menlo, Consolas, "Courier New", monospace;
}
p {
	max-width: 34rem;
	margin-top: 0;
}
</style>
<h1>Renderless Components in Svelte</h1>

<p>
	Below is an example of a component (<code>RenderlessTagPicker</code>) which contains no presentation,
	only renders what is provided to it. Its purpose is to provide behaviour which can be presented as
	appropriate based on the application in question. Inspired by <a href="https://adamwathan.me/renderless-components-in-vuejs/">Renderless Components in Vue.js</a>.
	However, this is yet another area where Svelte seems to shine.
</p>

<SimpleTagPicker bind:tags/>

<pre>
tags === {tags.length > 6 ? JSON.stringify(tags, null, 2) : JSON.stringify(tags)}
</pre>

<Code />