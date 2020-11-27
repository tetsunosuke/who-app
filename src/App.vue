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

<div class="container">
  <div class="row justify-content-md-center">
    <div class="col-md-6">
        <Colors :colors="colors" />
    </div>
    <div class="col-md-6">
        <Dice :colors="colors" />
    </div>
  </div>
</div>
<div class="container">
  <Themes @selectTheme="selectTheme" :themes="themes" :selectedThemes="selectedThemes"/>
  <!-- この画面で変更した mode だけを表に渡す -->
  <div class="container">
  <div class="row justify-content-md-center">
    <div class="col-md-12">
      <WhoTable :mode="mode" :selectedThemes="selectedThemes" />
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
            "mode": "NORMAL",
            "selectedThemes": [],
        }
    },
    methods: {
        // emitされたイベントを受け取って起動する
        selectTheme(e) {
            if (this.selectedThemes.indexOf(e.target.innerText) === -1) {
                // 未選択テーマであればテーマに追加
                // そうでなければモードごとの最大まで追加
                if (this.selectedThemes.length < (this.mode === "NORMAL" ? 3: 6)) {
                    this.selectedThemes.push(e.target.innerText);
                }
            } else {
                // 選択済みオブジェクトなので選択済みテーマから削除
                this.selectedThemes = this.selectedThemes.filter(v => v !== e.target.innerText);
            }
        },
        changeMode(mode) {
            this.selectedThemes = [];
            this.mode = mode;
        },
        start() {
            // リスタート
            console.info("start");
        }
    }
}
</script>
