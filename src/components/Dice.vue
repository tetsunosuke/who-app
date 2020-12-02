<template>
<button class="btn btn-primary" type="button" @click="cast">サイコロを振る</button>
<div v-if="num">
<ul id="dices">
<li id="dice1" v-bind:style="color">■</li>
<!-- TODO: ここはサイコロの画像 1.pngとかにする-画像の大きさが問題になりそう -->
<li id="dice2">{{num}}</li>
</ul>
</div>
</template>

<script>
export default {
    name: 'Dice',
    props: {
        "colors": { type : Array, default: [] },
        "themes": { type : Array, default: [] },
    },
    data() {
        return {
            num: "",
            color: {color: "white"},
        };
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
