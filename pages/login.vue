<template>
  <div class="login-container">
    <div class="login">
      <div class="login-title">Вход в систему</div>
      <div class="login-text">Для работы в системе введите свой логин и пароль</div>
      <el-form>
        <el-form-item>
          <div class="login__input">
            <div class="login__input-title">Логин</div>
            <div class="login__input-input">
              <el-input size="small" placeholder="Введите адрес электронной почты"></el-input>
            </div>
          </div>
        </el-form-item>
        <el-form-item>
          <div class="login__input">
            <div class="login__input-title">Пароль</div>
            <div class="login__input-input">
              <el-input size="small" placeholder="Введите пароль"></el-input>
            </div>
          </div>
        </el-form-item>
      </el-form>
      <div class="login-button">
        <el-button>Авторизироваться</el-button>
      </div>
      <div class="login-forgot">
        <nuxt-link to="">Забыли пароль?</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
  export default {

  }
</script>

<style scoped lang="scss">
</style>
