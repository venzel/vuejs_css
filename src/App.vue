<template>
    <div>
        <CssDimaicA />
        <hr />
        <CssDimaicB />
        <hr />
        <CssDimaicC />
        <hr />
        <CssDimaicD />
    </div>
</template>

<script>
import CssDimaicA from './views/CssDinamicA.vue';
import CssDimaicB from './views/CssDinamicB.vue';
import CssDimaicC from './views/CssDinamicC.vue';
import CssDimaicD from './views/CssDinamicD.vue';

export default {
    components: { CssDimaicA, CssDimaicB, CssDimaicC, CssDimaicD },
    name: 'App',
};
</script>

<style></style>
