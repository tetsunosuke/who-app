<template>
<!-- 1 -->
<svg v-show="passedNum===1" width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-dice-1" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M13 1H3a2 2 0 0 0-2 2v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3a2 2 0 0 0-2-2zM3 0a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V3a3 3 0 0 0-3-3H3z"/>
  <circle cx="8" cy="8" r="1.5"/>
</svg>
<!-- 2 -->
<svg v-show="passedNum===2" width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-dice-2" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M13 1H3a2 2 0 0 0-2 2v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3a2 2 0 0 0-2-2zM3 0a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V3a3 3 0 0 0-3-3H3z"/>
  <circle cx="4" cy="4" r="1.5"/>
  <circle cx="12" cy="12" r="1.5"/>
</svg>

<!-- 3 -->
<svg v-show="passedNum===3" width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-dice-3" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M13 1H3a2 2 0 0 0-2 2v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3a2 2 0 0 0-2-2zM3 0a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V3a3 3 0 0 0-3-3H3z"/>
  <circle cx="4" cy="4" r="1.5"/>
  <circle cx="12" cy="12" r="1.5"/>
  <circle cx="8" cy="8" r="1.5"/>
</svg>

<!-- 4 -->
<svg v-show="passedNum===4" width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-dice-4" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M13 1H3a2 2 0 0 0-2 2v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3a2 2 0 0 0-2-2zM3 0a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V3a3 3 0 0 0-3-3H3z"/>
  <circle cx="4" cy="4" r="1.5"/>
  <circle cx="12" cy="4" r="1.5"/>
  <circle cx="12" cy="12" r="1.5"/>
  <circle cx="4" cy="12" r="1.5"/>
</svg>


<!-- 5 -->
<svg v-show="passedNum===5" width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-dice-5" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M13 1H3a2 2 0 0 0-2 2v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3a2 2 0 0 0-2-2zM3 0a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V3a3 3 0 0 0-3-3H3z"/>
  <circle cx="4" cy="4" r="1.5"/>
  <circle cx="12" cy="4" r="1.5"/>
  <circle cx="12" cy="12" r="1.5"/>
  <circle cx="4" cy="12" r="1.5"/>
  <circle cx="8" cy="8" r="1.5"/>
</svg>

<!-- 6 -->
<svg v-show="passedNum===6" width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-dice-6" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M13 1H3a2 2 0 0 0-2 2v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3a2 2 0 0 0-2-2zM3 0a3 3 0 0 0-3 3v10a3 3 0 0 0 3 3h10a3 3 0 0 0 3-3V3a3 3 0 0 0-3-3H3z"/>
  <circle cx="4" cy="4" r="1.5"/>
  <circle cx="12" cy="4" r="1.5"/>
  <circle cx="12" cy="12" r="1.5"/>
  <circle cx="12" cy="8" r="1.5"/>
  <circle cx="4" cy="12" r="1.5"/>
  <circle cx="4" cy="8" r="1.5"/>
</svg>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        num: { type: Number, default: ""}
    },
    data() {
        return {
        }
    },
    computed: {
        passedNum: {
            get() {
                return this.num;
            }
        }
    }

}
</script>
