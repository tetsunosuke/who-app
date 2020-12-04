<template>
<nav class="navbar navbar-expand-md navbar-dark bg-dark">
<div class="container">
<a class="navbar-brand">Who? like</a>
<ul class="navbar-nav mr-auto">
<li class="nav-item">
<a class="nav-link" @click="$emit('changeMode', 'NORMAL')">NORMAL</a>
</li>
<li class="nav-item">
<a class="nav-link" @click="$emit('changeMode', 'HARD')">HARD</a>
</li>
</ul>
<ul class="navbar-nav">
<li class="nav-item">
<Modal />
</li>
</ul>
</div>
</nav>
</template>

<script>
import Modal from './Modal.vue'

export default {
    name: 'Navigation',
    components: {
        Modal
    },
    props: {
    },
    data() {
        return {
        }
    },
    emits: ["changeMode"]
}
</script>
