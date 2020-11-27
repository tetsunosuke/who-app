<template>
<table v-if="mode == 'NORMAL'" class="table table-hover table-borderd">
  <thead class="thead-dark">
    <tr><th>テーマ</th><th>サイコロ1</th><th>サイコロ2</th></tr>
  </thead>

  <tbody>
    <tr v-for="i in [1,2,3]">
        <th>{{passedSelectedThemes[i-1] === undefined ? "-" : passedSelectedThemes[i-1]}}</th>
        <td>{{i * 2 -1}}</td> <td>{{i*2}}</td>
    </tr>
  </tbody>
</table>
<table v-else class="table table-hover table-bordered">
  <thead class="thead-dark">
    <tr> <th>テーマ</th> <th>サイコロ</th></tr>
  </thead>
  <tbody>
    <tr v-for="i in [1,2,3,4,5,6]">
        <th>{{passedSelectedThemes[i-1] === undefined ? "-" : passedSelectedThemes[i-1]}}</th>
        <td>{{i}}</td>
    </tr> 
  </tbody>
</table>
</template>

<script>
export default {
    name: 'WhoTable',
    props: {
        'mode': {type:String, default: 'NORMAL'},
        "selectedThemes": { type : Array, default: [] }
    },
    computed: {
        passedSelectedThemes: {
            get() {
                return this.selectedThemes;
            }
        }
    },
    data() {
        return {
        }
    },
}
</script>
