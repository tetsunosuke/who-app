<template>
<!-- TODO: テーマが選ばれていないときはサイコロが振れないようにする -->
<template v-if="castable">
<button class="btn btn-primary" type="button" @click="cast">サイコロを振る</button>
<div v-if="num">
<ul id="dices">
<li id="dice1" v-bind:style="color">
<svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-person-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M3 14s-1 0-1-1 1-4 6-4 6 3 6 4-1 1-1 1H3zm5-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6z"/>
</svg>
</li>
<li id="dice2"> <DiceIcon :num="num" /> </li>
</ul>
</div>
</template>
</template>

<script>
import DiceIcon from './DiceIcon.vue'
export default {
    name: 'Dice',
    components: {
        DiceIcon,
    },
    props: {
        "colors": { type : Array, default: [] },
        "selectedThemes": { type: Array, default:[]},
        "mode": {type :String, default: "NORMAL"}
    },
    data() {
        return {
            num: "",
            color: {color: "white"},
        };
    },
    computed: {
        castable: {
            get() {
                const num = (this.mode === "NORMAL" ? 3 : 6);
                return num === this.selectedThemes.length;
            }
        }
    },
    methods: {
        cast() {
            // この感じだと偏りがあるかもしれないので乱数生成は検討する
            const num = Math.floor(Math.random() * 6) + 1;
            const index = Math.floor(Math.random() * 6);
            // 指定された色と数字でサイコロを更新する
            this.num = num;
            this.color = {color: this.colors[index]};
        }
    }
}
</script>
