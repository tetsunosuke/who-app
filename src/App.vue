<template>
<nav class="navbar navbar-expand-lg navbar-light bg-light">
<h1 class="navvar-brand">Who? like</h1>

<div class="collapse navbar-collapse">
<ul class="navbar-nav mr-auto">
<li class="nav-item active">
<input type="radio" id="normal" value="NORMAL" v-model="mode" /><label for="normal">NORMAL</label>
</li>
<li class="nav-item"><input type="radio" id="hard" value="HARD" v-model="mode" /><label for="hard">HARD</label>
</li>
</ul>
</div>
<div class="navbar-nav">
<p class="nav-item" id="start" @click="start">START</p>
</div>
</nav>

<!-- <p>selected: {{mode}}</p> -->
<div class="container">
  <Colors :colors="colors" />
  <!-- TODO; センター寄せ -->
  <!-- この画面で変更した mode だけを表に渡す -->
  <div class="container">
  <div class="row justify-content-md-center">
    <div class="col col-lg-4">
  <Themes :themes="themes" />
    </div>
    <div class="col-md-auto">
        <WhoTable :mode="mode" />
    </div>
    <div class="col col-lg-4">
        <Dice :colors="colors" />
    </div>
  </div>
</div>

  <!--
  -->
</div>
</template>

<script>
import WhoTable from './components/Table.vue'
import Colors  from './components/Colors.vue'
import Dice from './components/Dice.vue'
import Themes from './components/Themes.vue'
import Config from './config.js'

// 状態に関するデータなどはすべてここで持つようにする

export default {
  name: 'App',
  components: {
    Themes,
    WhoTable,
    Colors,
    Dice,
  },
  data () {
      const config = new Config();
      return {
          "colors": config.getColors(),
          "themes": config.getThemes(),
          "mode": "NORMAL"
      }
  },
  methods: {
      start() {
          // リスタート
          console.info("start");
      }
  }
}
</script>
