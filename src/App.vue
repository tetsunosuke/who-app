<template>
<Navigation @changeMode="changeMode" />
<div class="container">
  <div class="row justify-content-md-center">
    <div class="col-md-6">
        <Colors :colors="colors" />
    </div>
    <div class="col-md-6">
        <Dice :colors="colors" :selectedThemes="selectedThemes" :mode="mode" />
    </div>
  </div>
</div>
<div class="container">
  <Themes @selectTheme="selectTheme" @selectRandomTheme="selectRandomTheme" :themes="themes" :selectedThemes="selectedThemes"/>
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
import Navigation from './components/Navigation.vue'
import Config from './config.js'

// 状態に関するデータなどはすべてここで持つようにする
const shuffle = ([...array]) => {
    for (let i = array.length - 1; i >= 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
    }
    return array;
}

export default {
    name: 'App',
    components: {
        Themes,
        WhoTable,
        Colors,
        Dice,
        Modal,
        Navigation
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
        selectRandomTheme() {
            const count = (this.mode === "NORMAL" ? 3 : 6);
            this.selectedThemes = shuffle(this.themes).slice(0, count);
        },
        changeMode(mode) {
            this.selectedThemes = [];
            this.mode = mode;
        }
    }
}
</script>
