<template>
    <div class="demos">
        <div class="demo" @click="toggleActiveA" :class="computedActivatedA">CLICK!</div>
        <div class="demo" @click="toggleActiveB" :class="computedActivatedB">CLICK!</div>
    </div>
</template>

<script>
export default {
    name: 'CssDinamicB',
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
        toggleActiveA() {
            this.classActivated.c1 = !this.classActivated.c1;
        },
        toggleActiveB() {
            this.classActivated.c2 = !this.classActivated.c2;
        },
    },
    computed: {
        computedActivatedA() {
            return {
                c1: !this.classActivated.c1,
            };
        },
        computedActivatedB() {
            return {
                c2: !this.classActivated.c2,
            };
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
