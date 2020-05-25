<template>
  <div>
    <img :src="url" alt="img">
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['url']
}
</script>

<style scoped>

</style>
