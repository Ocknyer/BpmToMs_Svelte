<script>
  import Input from './components/Input.svelte';
  import Table from './components/Table.svelte';

  let tempo = 100;

  const increase = () => {
    tempo = tempo + 1;
  };

  const decrease = () => {
    tempo = tempo - 1;
  };

  const strokeEnter = (e) => {
    if (e.keyCode === 13) {
      tempo = e.target.value;
    }
  };

  $: minim = Math.ceil(tempo) * 2 + 'ms';
  $: quarter = Math.ceil(tempo) + 'ms';
  $: eighthNote = Math.ceil(tempo / 2) + 'ms';
  $: eightDotted = Math.ceil(tempo / 3) + 'ms';
  $: semiQuaver = Math.ceil(tempo / 4) + 'ms';
  $: demiSemiQuaver = Math.ceil(tempo / 8) + 'ms';
  $: hemidemiSemiQuaver = Math.ceil(tempo / 16) + 'ms';
  $: oneHundredTwentyEight = Math.ceil(tempo / 32) + 'ms';
</script>

<div id="app">
  <h1 class="title">BPM to MS</h1>
  <Input {tempo} {increase} {decrease} {strokeEnter} />
  <Table
    {tempo}
    {minim}
    {quarter}
    {eighthNote}
    {eightDotted}
    {semiQuaver}
    {demiSemiQuaver}
    {hemidemiSemiQuaver}
    {oneHundredTwentyEight}
  />
</div>

<style>
  #app {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 800px;
    height: 300px;
    margin: 100px auto;
    border: 1px solid black;
  }

  .title {
    font-size: 42px;
    font-weight: 700;
  }
</style>
