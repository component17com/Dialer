<template>
  <div class="wrapper">
    <div class="header">
      <el-button class="header__button"><i class="mdi mdi-settings"></i></el-button>
    </div>
    <div class="body">
      <div class="body__top">
        <div class="body__top-back">
          <el-button size="small"><i class="mdi mdi-arrow-left"></i></el-button>
        </div>
        <div class="body__top-title">Установка новой конфигурации</div>
        <div class="body__top-ustore">
          <el-button size="small">Перейти в UStore</el-button>
        </div>
      </div>
      <div class="body__content">
        <div class="body__content-notify">
          <el-alert
            title="Никогда не сообщайте ваш ключ посторонним людям и держите его в секрете! После установки конфигурации рекомендуем сменить ключ в личном кабинете Ustore или уведомить об этой необходимости вашего администратора."
            type="info"
            show-icon
            :closable="false">
          </el-alert>
        </div>
        <div class="body__content-title">
          Для получения новой конфигурации введите ее уникальный token-ключ:
        </div>
        <div class="body__content-input">
          <el-input size="small" placeholder="Введите ключ конфигурации">
            <el-button slot="append" size="small">Получить конфигурацию</el-button>
          </el-input>
        </div>
        <div class="body__content-text">
          <div class="text-title">Что такое конфигурация?</div>
          <div class="text-text">Конфигурация - это набор необходимых модулей для решения вашей задачи, которые имеют
            отдельных пользователей и базу данных. Вы можете установить любое количество конфигураций, которое вам
            необходимо для решения ваших задач.
          </div>
        </div>
        <div class="body__content-text">
          <div class="text-title">Где взять ключ конфигурации?</div>
          <div class="text-text">Данный ключ вы можете запросить у своего системного администратора или установить
            конфигурацию прямо из <nuxt-link to="/">личного кабинета в UStore.</nuxt-link>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">33</div>
  </div>
</template>

<script>
  export default {}
</script>

<style scoped lang="scss">
  .wrapper {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
  }

  .header {
    display: flex;
    height: 30px;
    background-color: #000000;
    align-items: center;
    min-height: 30px;
    padding: 0 10px;
    .header__button {
      margin-left: auto;
      padding: 0;
      border: none;
      background-color: transparent;
      .mdi {
        font-size: 18px;
        color: #eceff1;
        transition: 0.3s ease;
      }
      &:hover, &:focus {
        .mdi {
          color: #ff5722;
        }
      }
    }
  }

  .body__top {
    display: flex;
    align-items: center;
    height: 44px;
    min-height: 44px;
    border-bottom: solid 1px #cccccc;
    padding: 0 10px;
    .body__top-back {
      margin-right: 10px;
    }
    .body__top-title {
      font-size: 16px;
      font-weight: 500;
      color: #000000;
    }
    .body__top-ustore {
      margin-left: auto;
    }
  }

  .body {
    flex-grow: 2;
    display: flex;
    flex-direction: column;
    .body__content {
      padding: 010px;
      .body__content-input{
        margin-bottom: 15px;
      }
      .el-alert__title {
        font-size: 14px;
        font-weight: normal;
        color: #000000;
      }
      .body__content-title {
        font-size: 14px;
        font-weight: normal;
        color: #000000;
        margin-top: 15px;
        margin-bottom: 10px;
      }
      .body__content-text{
        margin-bottom: 10px;
        .text-title{
          font-size: 12px;
          color: #888888;
          font-weight: 500;
        }
        .text-text{
          font-size: 12px;
          font-weight: normal;
          color: #888888;
          a{
            font-size: 12px;
            font-weight: normal;
            color: #888888;
            transition: 0.3s ease;
            &:hover{
              color: #ff5722;
            }
          }
        }
      }
    }
  }

  .footer {
    height: 30px;
    background-color: #263238;
    min-height: 30px;
    display: flex;
    padding: 0 10px;
    align-items: center;
  }
</style>
