<template>
    <div class="dropContainer">
        <drop-comp />
    </div>
</template>

<script>
import DropComp from './DropComp.vue';
    export default {
        name: 'Dropdown',
        components: {
            DropComp
        },
    }
</script>

<style scoped>
.dropContainer{
    position: relative;
    background:transparent;
}
</style>