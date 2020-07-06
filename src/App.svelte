<script>
  import Working from "./Working.svelte";
 	let colors = ['blue', 'purple', 'red'];

	let name = 'world';
</script>

<h1>Hello {name}!</h1>
<Working {colors}/>