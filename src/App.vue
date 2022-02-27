<template>
    <div>
        <CssDimaicA />
        <hr />
        <CssDimaicB />
        <hr />
        <CssDimaicC />
    </div>
</template>

<script>
import CssDimaicA from './views/CssDinamicA.vue';
import CssDimaicB from './views/CssDinamicB.vue';
import CssDimaicC from './views/CssDinamicC.vue';

export default {
    components: { CssDimaicA, CssDimaicB, CssDimaicC },
    name: 'App',
};
</script>

<style></style>
