<script>
  import Paper from '@smui/paper';
  import TopAppBar, { Row, Section, Title } from '@smui/top-app-bar';
  import IconButton from '@smui/icon-button';
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

  let dense = true;
</script>

<svelte:head>
  <!-- Fonts -->
  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/icon?family=Material+Icons"
  />

  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,600,700"
  />

  <!-- Material Typography -->
  <link
    rel="stylesheet"
    href="https://unpkg.com/@material/typography@13.0.0/dist/mdc.typography.css"
  />

  <!-- SMUI -->
  <!-- <link
    rel="stylesheet"
    href="https://unpkg.com/svelte-material-ui/bare.css"
  /> -->
</svelte:head>

<div class="top-app-bar-container">
  <TopAppBar variant="static" {dense}>
    <Row>
      <Section>
        <IconButton style="margin-bottom: 0;" class="material-icons"
          >menu</IconButton
        >
        <Title>BPM to MS</Title>
      </Section>
      <Section align="end">
        <IconButton class="material-icons">github</IconButton>
      </Section>
    </Row>
  </TopAppBar>
</div>

<div id="app" class="paper-container">
  <Paper color="primary" variant="outlined" align="center">
    <h1 class="mdc-typography--headline2">BPM to MS</h1>
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
  </Paper>
</div>

<style>
  #app {
    display: flex;
    flex-direction: column;
    /* justify-content: center; */
    align-items: center;
    /* width: 800px; */
    /* height: 300px; */
    margin: 100px auto;
    /* border: 1px solid black; */
  }

  .top-app-bar-container {
    display: inline-block;
    min-width: 480px;
    width: 100%;
    margin: 0 18px 18px 0;
    border: 1px solid
      var(--mdc-theme-text-hint-on-background, rgba(0, 0, 0, 0.1));
  }
</style>
