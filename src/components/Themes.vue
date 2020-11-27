<template>
  <h2>テーマ</h2>
  <ul id="themes">
    <!-- これらを選択したら右側の欄に入るようにする -->
    <li v-for="value in values">{{value}}</li>
    <!-- TOOD: ここに自分で好きなテーマを追加できるようにする。リストじゃないほうが良いかも -->
    <li v-if="newTheme">{{newTheme}}</li>
  </ul>
  <input v-model="newTheme" />
  <!-- TODO :ランダムで選ぶオプションを作る -->
</template>

<script>
export default {
  name: 'Themes',
  props: {
      "themes": {
          type : Array, 
          default: []
      },
  },
  data() {
    return {
      values : this.themes,
      newTheme: ""
    }
  },
  methods: {
      // TODO: 入力された値をvaluesへ追加するような処理を書く
      update() {
          console.log(newvalue);
      }
  }
}
</script>
