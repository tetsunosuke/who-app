<template>
<!-- navの部分は別コンポーネントにしたい -->
<nav class="navbar navbar-expand-md navbar-dark bg-dark">
<div class="container">
<a class="navbar-brand">Who? like</a>
<ul class="navbar-nav mr-auto">
<li class="nav-item">
<a class="nav-link" @click="changeMode('NORMAL')">NORMAL</a>
</li>
<li class="nav-item">
<a class="nav-link" @click="changeMode('HARD')">HARD</a>
</li>
</ul>
<ul class="navbar-nav">
<li class="nav-item">
<Modal />
</li>
</ul>
</div>
</nav>

<!-- <p>selected: {{mode}}</p> -->
<div class="container">
  <!-- TODO; センター寄せ -->
  <Colors :colors="colors" />
  <!-- この画面で変更した mode だけを表に渡す -->
  <div class="container">
  <div class="row justify-content-md-center">
    <div class="col col-md-2">
  <Themes :themes="themes" />
    </div>
    <div class="col-md-8">
        <WhoTable :mode="mode" />
    </div>
    <div class="col col-md-2">
        <Dice :colors="colors" />
    </div>
  </div>
</div>

</div>
</template>

<script>
import WhoTable from './components/Table.vue'
import Colors  from './components/Colors.vue'
import Dice from './components/Dice.vue'
import Themes from './components/Themes.vue'
import Modal from './components/Modal.vue'
import Config from './config.js'

// 状態に関するデータなどはすべてここで持つようにする

export default {
  name: 'App',
  components: {
    Themes,
    WhoTable,
    Colors,
    Dice,
    Modal
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
      changeMode(mode) {
          this.mode = mode;
      },
      start() {
          // リスタート
          console.info("start");
      }
  }
}
</script>
