<script>
	import Box from './Exercise_child.svelte'
	let p = 'MyName'
	$: nameUpper = p.toUpperCase()
</script>

<Box bind:person={p} />

<p>Reactive value in the parent component: {nameUpper}</p>

<hr />


<!-- 
<script>
    import "./Exercise_child.svelte"
</script>

-->
