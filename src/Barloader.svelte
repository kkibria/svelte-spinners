<script>
  import chroma from "chroma-js";
  export let width = "5em";
  export let height = `calc(${width}/15)`;

  export let color = "#FF3E00";

  let bgcolor = chroma(color).alpha(0.2);

  let css_var = `
--width: ${width};
--height: ${height};
--color: ${color};
--bgcolor: ${bgcolor};
`;
</script>

<style>
  @keyframes long {
    0% {
      left: -35%;
      right: 100%;
    }
    60% {
      left: 100%;
      right: -90%;
    }
    100% {
      left: 100%;
      right: -90%;
    }
  }

  @keyframes short {
    0% {
      left: -200%;
      right: 100%;
    }
    60% {
      left: 107%;
      right: -8%;
    }
    100% {
      left: 107%;
      right: -8%;
    }
  }

  .wrapper {
    height: var(--height);
    width: calc(var(--width) * 2);
    background-color: var(--bgcolor);
    position: relative;
    overflow: hidden;
    background-clip: padding-box;
  }

  .lines {
    height: var(--height);
    background-color: var(--color);
    position: absolute;
    overflow: hidden;
    background-clip: padding-box;
    display: block;
    border-radius: 2px;
    will-change: left, right;
    animation-fill-mode: forwards;
  }

  .long {
    animation: long 2.1s ease-in-out 0s infinite normal both running;
  }
  .short {
    animation: short 2.1s ease-in-out 0s infinite normal both running;
    opacity: 0.65;
  }
</style>


<div class="wrapper" style={css_var}>
  <div class="lines long" />
  <div class="lines short" />
</div>
