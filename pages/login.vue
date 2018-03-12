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
  .login-container{
    font-family: 'Open Sans', sans-serif;
    height: 100vh;
    background-color: #ebeef5;
    display: flex;
    align-items: center;
    justify-content: center;
    .login{
      width: 500px;
      height: 500px;
      background-color: #ffffff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 50px;
    }
    .login-title{
      font-size: 22px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #161a24;
      margin-bottom: 15px;
    }
    .login-text{
      font-size: 14px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #161a24;
      margin-bottom: 10px;
    }
    .el-form{
      width: 100%;
      .login__input-title{
        font-size: 13px;
        text-align: left;
        color: #606266;
        height: 30px;
      }
      input{
        width: 100%;
        font-family: 'Open Sans', sans-serif;
      }
    }
    .login-button{
      width: 100%;
      margin-bottom: 20px;
      button{
        font-size: 14px;
        font-weight: 600;
        color: #ffffff;
        border-radius: 4px;
        background-color: #409eff;
        width: 100%;
      }
    }
    .login-forgot{
      a{
        font-size: 13px;
        color: #c0c4cc;
        text-decoration: none;
        transition: 0.3s ease;
        &:hover{
          text-decoration: underline;
        }
      }
    }
  }
</style>
