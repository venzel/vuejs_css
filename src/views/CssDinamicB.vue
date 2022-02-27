<template>
    <div class="demos">
        <div class="demo" @click="activeA" :class="activatedA">CLICK!</div>
        <div class="demo" @click="activeB" :class="activatedB">CLICK!</div>
    </div>
</template>

<script>
export default {
    name: 'Css',
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
        activeA() {
            this.classActivated.c1 = !this.classActivated.c1;
        },
        activeB() {
            this.classActivated.c2 = !this.classActivated.c2;
        },
    },
    computed: {
        activatedA() {
            return {
                c1: !this.classActivated.c1,
            };
        },
        activatedB() {
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
