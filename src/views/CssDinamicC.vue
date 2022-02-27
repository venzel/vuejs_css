<template>
    <div class="box">
        <div class="demo" :class="['rotate', cssClassName, { restartRotate: cssRestartRotate }]">a</div>
        <input type="text" v-model="cssClassName" />
    </div>
</template>

<script>
export default {
    name: 'CssDinamicC',
    data() {
        return {
            cssClassName: 'c1',
            cssRestartRotate: false,
        };
    },
    methods: {},
};
</script>

<style>
* {
    font-family: arial;
}
.box {
    display: block;
}
.demo {
    display: flex;
    width: 100px;
    height: 100px;
    background-color: #eee;
}
.rotate {
    transform: rotate(45deg);
}
.restartRotate {
    transform: rotate(0deg);
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
