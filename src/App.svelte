<script>
  import Working from "./Working.svelte";
  import Barloader from "./Barloader.svelte";

  let colors = ["blue", "purple", "red"];
</script>

<h1>Pure svelte spinners</h1>
<h2>Framework agnostic</h2>
<h3>Uses css animation and css variables</h3>
<Working {colors} />
<p />
<Barloader />