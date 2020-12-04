<template>
  <ul id="themes">
    <li><button class="btn btn-primary" @click="$emit('selectRandomTheme')">ランダムに設定</button></li>
    <li v-for="value in passedThemes">
      <button @click="$emit('selectTheme', $event)" class="btn" v-bind:class="passedSelectedThemes.includes(value)? 'btn-dark' : 'btn-outline-dark'">
      {{value}}
      </button>
    </li>
    <div class="input-group mb-3 flex-nowrap">
        <div class="input-group-prepend">
            <span class="input-group-text" id="basic-addon1">フリーテーマ</span>
        </div>
        <input type="text" @change="addTheme" class="form-control" placeholder="新テーマ" aria-describedby="basic-addon1">
    </div>
  </ul>
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
      },
  },
  data() {
    return {
      passedThemes: this.themes,
    }
  },
  computed: {
      passedSelectedThemes:{
          get() {
              return this.selectedThemes;
          }
      },
  },
  emits: ["selectTheme", "selectRandomTheme"],
  methods: {
      addTheme(e) {
          this.themes.push(e.target.value);
          e.target.value = "";
      }
  }
}
</script>
