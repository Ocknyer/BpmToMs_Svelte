<script>
  export let tempo;
  export let increase;
  export let decrease;
  export let editTempo;

  $: {
    console.log(tempo, typeof tempo);
  }
</script>

<div>
  <button on:click={increase}>up</button>
  <input type="number" bind:value={tempo} on:keyup={editTempo} />
  <button on:click={decrease}>down</button>
</div>

<style>
  div {
    margin: 30px 0;
  }

  input {
    text-align: right;
  }
</style>
