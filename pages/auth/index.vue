<template>
  <div class='auth-page'>
    <div class='auth-bg' />
    <div class='auth-container'>
      <auth-component />
    </div>
  </div>
</template>

<script>
import AuthComponent from '~/components/auth'
export default {
  name: 'auth',
  components: { AuthComponent },
  created() {
    // console.log(this)
  }
}
</script>

<style lang='scss' scoped>
.auth-page{
  display: grid;
  grid-template-columns: 1fr 600px;
  height: 100%;
  min-height: 100vh;
  .auth-container{
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .auth-bg{
    background-image: url("/arch-auth-bg.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }

  @media screen and (max-width: 768px) {
    grid-template-columns: 1fr;
    .auth-bg{
      display: none;
    }
  }
}
</style>
