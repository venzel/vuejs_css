<template>
    <div class="demos">
        <div class="demo" @click="toggleActiveC1" :class="{ c1: classActivated.c1 }">CLICK!</div>
        <div class="demo" @click="toggleActiveC2" :class="{ c2: classActivated.c2 }">CLICK!</div>
        <div class="demo" @click="toggleActiveC3" :class="{ c3: classActivated.c3 }">CLICK!</div>
    </div>
</template>

<script>
export default {
    name: 'CssDinamicA',
    data() {
        return {
            classActivated: {
                c1: false,
                c2: false,
                c3: false,
            },
        };
    },
    methods: {
        toggleActiveC1() {
            this.classActivated.c1 = !this.classActivated.c1;
        },
        toggleActiveC2() {
            this.classActivated.c2 = !this.classActivated.c2;
        },
        toggleActiveC3() {
            this.classActivated.c3 = !this.classActivated.c3;
        },
    },
};
</script>

<style>
* {
    font-family: arial;
}
.demos {
    display: flex;
    justify-content: space-between;
}
.demo {
    display: flex;
    width: 100px;
    height: 100px;
    background-color: #eee;
}
.c1 {
    background-color: red;
}
.c2 {
    background-color: green;
}
.c3 {
    background-color: yellow;
}
</style>
