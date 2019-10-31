<template>
  <div>
  </div>
</template>

<script>
export default {
  name: 'scroll360',
  props: {
    msg: String
  },
  created:function(){
    /* eslint-disable no-console */
    console.log(this.$slots.default[0]);
  }
}
</script>
<style scoped>
</style>
