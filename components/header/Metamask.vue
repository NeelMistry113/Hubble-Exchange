<template>
    <div class="metamask" @click="$emit('connect')">  
        Metamask
    </div>
</template>

<script>
export default {
  name: 'Metamask',
  data () {
    return {
    }
  },
  computed: {
  },
  methods: {
  }
}
</script>

<style scoped>
  .metamask{
    font-size: 22px;
    padding: 16px 28px;
    cursor: pointer;
    color: rgb(183, 171, 171);
  }

  .metamask:hover{
    color: #fff;
  }
</style>