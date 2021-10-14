<template>
  <div>
    <a-menu
      :default-selected-keys="[routeBaseName]"
      mode="inline"
      theme="light"
      :inline-collapsed="false"
    >
      <a-menu-item key="work-place">
        <nuxt-link to='/work-place'>
          <a-icon type="desktop" />
          <span>Рабочий</span>
        </nuxt-link>
      </a-menu-item>
      <a-menu-item key="users">
        <nuxt-link to='/users'>
          <a-icon type="user" />
          <span>Пользователи</span>
        </nuxt-link>
      </a-menu-item>
      <a-menu-item key="3">
        <a-icon type="inbox" />
        <span>Документы</span>
      </a-menu-item>
      <a-menu-item key="4">
        <a-icon type="inbox" />
        <span>Архив</span>
      </a-menu-item>
<!--      <a-sub-menu key="sub1">-->
<!--        <span slot="title"-->
<!--          ><a-icon type="mail" /><span>Navigation One</span></span-->
<!--        >-->
<!--        <a-menu-item key="5"> Option 5 </a-menu-item>-->
<!--        <a-menu-item key="6"> Option 6 </a-menu-item>-->
<!--        <a-menu-item key="7"> Option 7 </a-menu-item>-->
<!--        <a-menu-item key="8"> Option 8 </a-menu-item>-->
<!--      </a-sub-menu>-->
    </a-menu>
  </div>
</template>

<script>
export default {
  name: 'menu-component',
  computed: {
    routeBaseName() {
      return this.$route.name
    }
  }
}
</script>

<style scoped></style>
