<script>
  export let tempo;
  export let minim;
  export let quarter;
  export let eighthNote;
  export let eightDotted;
  export let semiQuaver;
  export let demiSemiQuaver;
  export let hemidemiSemiQuaver;
  export let oneHundredTwentyEight;
</script>

<table class="table">
  <tr>
    <th>BPM</th>
    <th>1/2</th>
    <th>1/4</th>
    <th>1/8</th>
    <th>1/8T</th>
    <th>1/16</th>
    <th>1/32</th>
    <th>1/64</th>
    <th>1/128</th>
  </tr>
  <tr>
    <td>{tempo}</td>
    <td>{minim}</td>
    <td>{quarter}</td>
    <td>{eighthNote}</td>
    <td>{eightDotted}</td>
    <td>{semiQuaver}</td>
    <td>{demiSemiQuaver}</td>
    <td>{hemidemiSemiQuaver}</td>
    <td>{oneHundredTwentyEight}</td>
  </tr>
</table>

<style>
  table {
    width: 700px;
    text-align: center;
  }

  td {
    padding: 10px;
  }
</style>
