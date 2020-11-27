<template>
  <h2>Colors</h2>
  <ul id="colors">
    <!-- TODO: bootstrapのいい感じのやつを使う --> 
    <li v-for="style in styles" v-bind:style="style">■</li>
  </ul>
</template>

<script>
export default {
  name: 'Colors',
  props: {
      "colors": {
          type : Array, 
          default: []
      }, 
  },
  data() {
    return {
      styles : this.colors.map( (c) => { return {"color": c };})
    }
  }
}
</script>
