<template>
  <div class='layout-default'>
    <menu-component />
    <Nuxt />
  </div>
</template>
<script>
import MenuComponent from '~/components/layouts/menu'
export default {
  components: { MenuComponent }
}
</script>
<style lang='scss'>
.layout-default{
  display: grid;
  grid-template-columns: 250px 1fr;
}
</style>
