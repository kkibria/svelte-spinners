# svelte-spinners
pure svelte spinners with css variables


## Install
```bash
npm i https://github.com/kkibria/svelte-spinner.git
```

## How to use in svelte source,
```html
<script>
    import Working from "kkibria-svelte-spinner/src/Working.svelte";
    let colors = ['blue', 'purple', 'red'];
</script>

<h1>Pure svelte spinners</h1>
<h2>Framework agnostic</h2>
<h3>Uses css animation and css variables</h3>
<Working {colors}/>
```