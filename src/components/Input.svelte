<script>
  import Button, { Label } from '@smui/button';
  import Textfield from '@smui/textfield';

  export let tempo;
  export let increase;
  export let decrease;
  export let editTempo;

  $: {
    console.log(tempo, typeof tempo);
  }
</script>

<div>
  <Button variant="outlined" on:click={increase}
    ><Label>up</Label></Button
  >
  <Textfield
    type="number"
    style="min-width: 200px; margin: 0 10px; height: 36px;"
    bind:value={tempo}
    on:keyup={editTempo}
  />

  <Button variant="outlined" on:click={decrease}>down</Button>
</div>

<style>
  div {
    margin: 30px 0;
  }
</style>
