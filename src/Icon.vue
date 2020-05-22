<template>
  <svg v-if="name" class="icon">
      <use :xlink:href="`#i-${name}`"></use>
  </svg>
</template>
<script>
export default {
  props: ['name']
}
</script>
<style scoped>
  .icon{
      height: 1em;
      width: 1em;
  }
</style>