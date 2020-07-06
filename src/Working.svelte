<script>
  export let size = "0.5em";
  export let colors = ["blue", "red", "orange", "green"];
  const margin = "1px";

  let css_var = `
		--size: ${size};
		--num: ${colors.length}; 
		--margin: ${margin};
	`;

  let ball_styles = [];
  let i = 1;
  colors.forEach((c) => ball_styles.push({ c: c, d: `${i++ * 0.07}s` }));
</script>

<style>
  @keyframes sync {
    0% {
      transform: translateY(0);
    }
    33% {
      transform: translateY(calc(var(--size) * 0.6));
    }
    66% {
      transform: translateY(calc(var(--size) * -0.6));
    }
    100% {
      transform: translateY(0);
    }
  }
  .balls {
    height: var(--size);
    width: var(--size);
    margin: var(--margin);
    display: inline-block;
    border-radius: 100%;
    background-color: gray;
    animation: sync 0.7s ease-in-out 0s infinite normal both running;
  }
  .wrapper {
    height: calc(var(--size) * 2);
    width: calc((var(--size) + var(--margin) * 2) * var(--num));
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>

<div class="wrapper" style={css_var}>
  {#each ball_styles as s}
    <div
      class="balls"
      style="animation-delay: {s.d}; background-color: {s.c}" />
  {/each}
</div>
