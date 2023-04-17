<script>
  import Input from './components/Input.svelte';
  import Table from './components/Table.svelte';

  let tempo = 100;

  const increase = () => {
    if (tempo < 300) {
      tempo = tempo + 1;
    }
  };

  const decrease = () => {
    if (tempo > 0) {
      tempo = tempo - 1;
    }
  };

  const editTempo = (e) => {
    tempo = parseInt(e.target.value);
  };

  $: baseBPM = 60000 / tempo;

  $: minim = Math.ceil(baseBPM) * 2 + 'ms';
  $: quarter = Math.ceil(baseBPM) + 'ms';
  $: eighthNote = Math.ceil(baseBPM / 2) + 'ms';
  $: eightDotted = Math.ceil(baseBPM / 3) + 'ms';
  $: semiQuaver = Math.ceil(baseBPM / 4) + 'ms';
  $: demiSemiQuaver = Math.ceil(baseBPM / 8) + 'ms';
  $: hemidemiSemiQuaver = Math.ceil(baseBPM / 16) + 'ms';
  $: oneHundredTwentyEight = Math.ceil(baseBPM / 32) + 'ms';
</script>

<div id="app">
  <h1 class="title">BPM to MS</h1>
  <Input {tempo} {increase} {decrease} {editTempo} />
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
