<template>
  <h2>プレーヤー</h2>
  <ul id="colors">
    <li v-for="style in styles" v-bind:style="style">
        <svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-person-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" d="M3 14s-1 0-1-1 1-4 6-4 6 3 6 4-1 1-1 1H3zm5-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6z"/>
        </svg>
    </li>
  </ul>
</template>

<script>
export default {
    name: 'Colors',
    props: {
        "colors": { type : Array, default: [] }
    },
    data() {
        return {
            styles : this.colors.map( (c) => { return {"color": c };})
        }
    }
}
</script>
