<template>
  <a-form
    :form="form"
    class="login-form"
    @submit="handleSubmit"
  >
    <h1>Авторизация</h1>
    <a-form-item
    >
      <a-input

        v-decorator="[
          'login',
          { rules: [{ required: true, message: 'Введите логин' }] },
        ]"
        placeholder="Login"
      >
        <a-icon slot="prefix" type="user" style="color: rgba(0,0,0,.25)" />
      </a-input>
    </a-form-item>
    <a-form-item>
      <a-input
        v-decorator="[
          'password',
          { rules: [{ required: true, message: 'Введите пароль' }] },
        ]"
        type="password"
        placeholder="Password"
      >
        <a-icon slot="prefix" type="lock" style="color: rgba(0,0,0,.25)" />
      </a-input>
    </a-form-item>
    <a-form-item>
      <a-button type="primary" html-type="submit" class="login-form-button">
        Войти
      </a-button>
    </a-form-item>
  </a-form>
</template>

<script>
export default {
  name: 'auth-component',
  data: () => ({

  }),
  beforeCreate() {
    this.form = this.$form.createForm(this, { name: 'normal_login' });
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault();

      this.form.validateFields((err, values) => {
        if (!err) {
          this.form.setFields({
            ['login']: {
              value: values.login,
              errors: [Error]
            },
            ['password']: {
              value: values.password,
              errors: [Error]
            }
          })
          this.$message.error('Неверный логин или пароль');
          console.log('Received values of form: ', values);
        }
      });
    },
  },
};
</script>
<style>
.login-form {

  max-width: 300px;
}
.login-form-button {
  width: 100%;
}
</style>
