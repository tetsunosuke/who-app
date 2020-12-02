<template>
  <h2>テーマ</h2>
  <ul id="themes">
    <!-- これらを選択したら右側の欄に入るようにする -->
    <li v-for="value in passedThemes">
      <button @click="$emit('selectTheme', $event)" class="btn" v-bind:class="passedSelectedThemes.includes(value)? 'btn-dark' : 'btn-outline-dark'">
      <!-- ここは toggle とかに書き換える必要があるはず -->
      {{value}}
      </button>
    </li>
    <!-- TOOD: ここに自分で好きなテーマを追加できるようにする。リストじゃないほうが良いかも -->
    <li v-if="newTheme"><button @click="apply" class="btn btn-outline-dark">{{newTheme}}</button></li>
  </ul>
  <input v-model="newTheme" />
  <!-- TODO :ランダムで選ぶオプションを作る -->
  <p class="alert alert-warning">テーマの選択・追加は未実装です</p>
</template>

<script>
export default {
  name: 'Themes',
  props: {
      "themes": {
          type : Array, 
          default: []
      },
      "selectedThemes": {
          type : Array, 
          default: []
      }
  },
  data() {
    return {
      passedThemes: this.themes,
      newTheme: "",
      passedSelectedThemes: this.selectedThemes,
    }
  },
  emits: ["selectTheme"],
  methods: {
      // TODO: 入力された値をvaluesへ追加するような処理を書く
      update() {
          console.log(newvalue);
      },
  }
}
</script>
