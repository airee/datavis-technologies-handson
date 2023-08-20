<script>
	import B from './Exercise_child.svelte'
  	let myCountingVariable = 42;
</script>


<p> The answer to life, the Universe, and everything, is </p>
<B count={myCountingVariable} />
