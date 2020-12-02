<template>
<table v-if="mode == 'NORMAL'" class="table table-hover table-borderd">
  <thead class="thead-dark">
    <tr><th>テーマ</th><th>サイコロ1</th><th>サイコロ2</th></tr>
  </thead>

  <tbody>
    <tr> <th>テーマ1</th> <td>1</td> <td>2</td></tr>
    <tr> <th>テーマ2</th> <td>3</td> <td>4</td></tr>
    <tr> <th>テーマ3</th> <td>5</td> <td>6</td> </tr>
  </tbody>
</table>
<table v-else class="table table-hover table-bordered">
  <thead class="thead-dark">
    <tr> <th>テーマ</th> <th>サイコロ</th></tr>
  </thead>

  <tbody>
    <tr> <th>テーマ1</th> <td>1</td></tr>
    <tr> <th>テーマ2</th> <td>2</td> </tr>
    <tr> <th>テーマ3</th> <td>3</td> </tr>
    <tr> <th>テーマ4</th> <td>4</td> </tr>
    <tr> <th>テーマ5</th> <td>5</td> </tr>
    <tr> <th>テーマ6</th> <td>6</td> </tr>
  </tbody>
</table>

</template>

<script>
export default {
    name: 'WhoTable',
    props: ['value', 'mode'],
    data() {
        console.log(this.mode, this.value);
        return {
        }
    },
}
</script>
