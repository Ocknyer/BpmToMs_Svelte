<script>
  import DataTable, { Head, Row, Body, Cell } from '@smui/data-table';

  export let tempo;
  export let minim;
  export let quarter;
  export let eighthNote;
  export let eightDotted;
  export let semiQuaver;
  export let demiSemiQuaver;
  export let hemidemiSemiQuaver;
  export let oneHundredTwentyEight;

  $: notes = [
    { note: 'BPM', value: tempo },
    { note: '1/2', value: minim },
    { note: '1/4', value: quarter },
    { note: '1/8', value: eighthNote },
    { note: '1/8T', value: eightDotted },
    { note: '1/16', value: semiQuaver },
    { note: '1/32', value: demiSemiQuaver },
    { note: '1/64', value: hemidemiSemiQuaver },
    { note: '1/128', value: oneHundredTwentyEight },
  ];
</script>

<DataTable>
  <Head>
    <Row>
      {#each notes as note}
        <Cell style="vertical-align:middle;">{note.note}</Cell>
      {/each}
    </Row>
  </Head>
  <Body>
    <Row>
      {#each notes as note}
        <Cell style="vertical-align:middle;">{note.value}</Cell>
      {/each}
    </Row>
  </Body>
</DataTable>
