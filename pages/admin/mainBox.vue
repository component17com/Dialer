<template>
  <div class="wrapper">
    <!--Шапка-->
    <div class="header">
      <div class="header__select">
        <el-dropdown trigger="click" placement="bottom-start" size="mini">
          <span class="el-dropdown-link">
            Интернет-магазин одежды и аксессуаров<i class="el-icon-arrow-down el-icon--right"></i>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>Action 1</el-dropdown-item>
            <el-dropdown-item>Action 2</el-dropdown-item>
            <el-dropdown-item>Action 3</el-dropdown-item>
            <el-dropdown-item divided>Action 5</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </div>
      <div class="header__name">
        <i class="mdi mdi-account"></i>
        Имя Пользователя
      </div>
      <div class="header__button">
        <el-button><i class="mdi mdi-settings"></i></el-button>
        <el-button><i class="mdi mdi-bell"></i></el-button>
        <el-button><i class="mdi mdi-exit-to-app"></i></el-button>
      </div>
    </div>
    <!--Список модулей-->
    <div class="menu-wrapper">
      <div class="menu__dashboard">
        <div class="menu__dashboard-icon">
          <i class="mdi mdi-view-dashboard"></i>
        </div>
        <div class="menu__dashboard-title">
          Рабочий стол
        </div>
      </div>
      <div class="menu">
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
        <div class="menu__item">
          <div class="menu__item-icon">
            <i class="mdi mdi-view-dashboard"></i>
          </div>
          <div class="menu__item-title">
            Рабочий стол
          </div>
        </div>
      </div>
      <div class="menu__allModules">
        <div class="menu__allModules-icon">
          <i class="mdi mdi-apps"></i>
        </div>
        <div class="menu__allModules-title">
          Все модули
        </div>
      </div>
    </div>
    <!--табы - контент-->
    <div class="tabs-wrapper">
      <el-tabs type="card" @tab-click="handleClick">
        <el-tab-pane>
          <span slot="label">
            <span class="tabs-text">
              <i class="el-icon-date"></i> Агрегатор почтовых ящиков Агрегатор почтовых ящиков
            </span>
            <el-button><i class="mdi mdi-close"></i></el-button>
          </span>
          <div class="body">
            22
          </div>
        </el-tab-pane>
        <el-tab-pane>
          <span slot="label">
            <i class="el-icon-date"></i> Route
            <el-button><i class="mdi mdi-close"></i></el-button>
          </span>
          <div class="body">
            22
          </div>
        </el-tab-pane>
        <el-tab-pane>
          <span slot="label">
            <i class="el-icon-date"></i> Route
            <el-button><i class="mdi mdi-close"></i></el-button>
          </span>
          <div class="body">
            22
          </div>
        </el-tab-pane>
        <el-tab-pane>
          <span slot="label">
            <i class="el-icon-date"></i> Route
            <el-button><i class="mdi mdi-close"></i></el-button>
          </span>
          <div class="body">
            22
          </div>
        </el-tab-pane>
      </el-tabs>
    </div>
    <!--Уведомления-->
    <div class="notify-wrapper notify-wrapper-active">
      <div class="notify__header">
        <div class="notify__header-title">
          Уведомления
          <el-badge :value="1200" class="item"></el-badge>
        </div>
        <div class="notify__header-close">
          <el-button type="text">Очистить все</el-button>
        </div>
      </div>
      <div class="notify__body">
        <div class="notify notify-new">
          <div class="notify__titles">
            <div class="notify__titles-icon"><i class="mdi mdi-image"></i></div>
            <div class="notify__titles-title">Новое оповещение, короткий текст</div>
            <div class="notify__titles-button">
              <el-button><i class="mdi mdi-close"></i></el-button>
            </div>
          </div>
          <div class="notify__text">Уже прочитанное оповещение</div>
          <div class="notify__time"><i class="mdi mdi-clock"></i>1 день назад</div>
        </div>
        <div class="notify notify-new notify-button">
          <div class="notify__titles">
            <div class="notify__titles-icon"><i class="mdi mdi-image"></i></div>
            <div class="notify__titles-title">Название модуля</div>
            <div class="notify__titles-button">
              <el-button><i class="mdi mdi-close"></i></el-button>
            </div>
          </div>
          <div class="notify__text">Новое оповещение с действиями</div>
          <div class="notify__time"><i class="mdi mdi-clock"></i>1 день назад</div>
          <div class="notify__buttons">
            <el-button size="mini">Default</el-button>
            <el-button size="mini">Default</el-button>
            <el-button size="mini">Default</el-button>
          </div>
        </div>
        <div class="notify notify-err notify-new">
          <div class="notify__titles">
            <div class="notify__titles-icon"><i class="mdi mdi-alert"></i></div>
            <div class="notify__titles-title">Название модуля</div>
            <div class="notify__titles-button">
              <el-button><i class="mdi mdi-close"></i></el-button>
            </div>
          </div>
          <div class="notify__text">Новое оповещение об ошибке</div>
          <div class="notify__time"><i class="mdi mdi-clock"></i>1 день назад</div>
        </div>
        <div class="notify notify-success notify-new">
          <div class="notify__titles">
            <div class="notify__titles-icon"><i class="mdi mdi-checkbox-marked-circle"></i></div>
            <div class="notify__titles-title">Название модуля</div>
            <div class="notify__titles-button">
              <el-button><i class="mdi mdi-close"></i></el-button>
            </div>
          </div>
          <div class="notify__text">Новое оповещение об успешном действии (обновлено до версии 2.0.0)</div>
          <div class="notify__time"><i class="mdi mdi-clock"></i>1 день назад</div>
        </div>
        <div class="notify notify-warning">
          <div class="notify__titles">
            <div class="notify__titles-icon"><i class="mdi mdi-checkbox-marked-circle"></i></div>
            <div class="notify__titles-title">Название модуля</div>
            <div class="notify__titles-button">
              <el-button><i class="mdi mdi-close"></i></el-button>
            </div>
          </div>
          <div class="notify__text">Прочитанное оповещение-предупреждение</div>
          <div class="notify__time"><i class="mdi mdi-clock"></i>1 день назад</div>
        </div>
        <div v-for="item in 70" :key="item" class="notify">
          <div class="notify__titles">
            <div class="notify__titles-icon"><i class="mdi mdi-image"></i></div>
            <div class="notify__titles-title">Название модуля</div>
            <div class="notify__titles-button">
              <el-button><i class="mdi mdi-close"></i></el-button>
            </div>
          </div>
          <div class="notify__text">Уже прочитанное оповещение</div>
          <div class="notify__time"><i class="mdi mdi-clock"></i>1 день назад</div>
        </div>
      </div>
    </div>
    <!--Футер-->
    <div class="footer">
      <div class="footer-title">Доступно новое обновление (2.0.6)</div>
      <div class="footer-refresh">
        <el-button type="text"><i class="mdi mdi-refresh"></i>Обновить</el-button>
      </div>
      <div class="footer-loading">
        <el-button type="text" :loading="true" size="mini">Загрузка обновлений</el-button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {}
</script>

<style lang="scss">
  body{
    overflow: hidden;
  }
  @keyframes notify {
    from{
      right: -500px;
    }
    to{
      right: 0;
    }
  }
  *:focus{
    outline: none!important;
  }
  .wrapper {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    overflow: hidden;
  }

  .header {
    display: flex;
    height: 30px;
    background-color: #000000;
    align-items: center;
    min-height: 30px;
    padding: 0 10px;
    .header__name {
      margin-left: auto;
      font-size: 12px;
      font-weight: normal;
      color: #eceff1;
      .mdi {
        margin-right: 5px;
      }
    }
    .header__button {
      button {
        padding: 0;
        border: none;
        background-color: transparent;
        margin-left: 32px;
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
    .header__select {
      cursor: pointer;
      .el-dropdown-link {
        font-size: 12px;
        font-weight: normal;
        color: #eceff1;
      }
    }
  }

  .menu-wrapper {
    padding: 5px 0;
    height: 50px;
    min-height: 50px;
    background-color: #263238;
    overflow: hidden;
    display: flex;
    align-items: center;
    .menu__dashboard {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      width: 100px;
      min-width: 100px;
      height: 100%;
      font-size: 11px;
      font-weight: normal;
      color: #ffffff;
      cursor: pointer;
      transition: 0.3s ease;
      border-radius: 1px;
      border-right: 1px solid #90a4ae;
      .menu__dashboard-icon {
        flex-basis: 100%;
        display: flex;
        justify-content: center;
        font-size: 18px;
        height: 18px;
      }
      &:hover, &:focus {
        background-color: #000000;
      }
    }
    .menu__allModules {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      min-width: 100px;
      width: 100px;
      height: 100%;
      font-size: 11px;
      font-weight: normal;
      color: #ffffff;
      cursor: pointer;
      transition: 0.3s ease;
      border-radius: 1px;
      border-left: 1px solid #90a4ae;
      margin-left: auto;
      .menu__allModules-icon {
        flex-basis: 100%;
        display: flex;
        justify-content: center;
        font-size: 18px;
        height: 18px;
      }
      &:hover, &:focus {
        background-color: #000000;
      }
    }
    .menu {
      display: flex;
      align-items: center;
      height: 100%;
      flex-wrap: wrap;
      flex-grow: 2;
      overflow: hidden;
      .menu__item {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        width: 100px;
        height: 100%;
        font-size: 11px;
        font-weight: normal;
        color: #ffffff;
        cursor: pointer;
        transition: 0.3s ease;
        border-radius: 1px;
        padding-left: 10px;
        padding-right: 10px;
        .menu__item-icon {
          flex-basis: 100%;
          display: flex;
          justify-content: center;
          font-size: 18px;
          height: 18px;
        }
        .menu__item-title {
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
        }
        &:hover, &:focus {
          background-color: #000000;
        }
      }
    }
  }

  .tabs-wrapper {
    height: 25px;
    min-height: 25px;
    .el-tabs__header {
      margin: 0;
    }
    .el-tabs__nav {
      display: flex;
      background-color: #ebebeb;
      width: 100%;
      height: 25px;
      min-height: 25px;
      border: none !important;
      .el-tabs__item {
        padding: 2px 10px !important;
        font-size: 12px;
        font-weight: normal;
        color: #ffffff;
        height: 25px;
        min-height: 25px;
        display: flex;
        align-items: center;
        background-color: #546e7a;
        max-width: 222px;
        flex-grow: 2;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        span {
          width: 100%;
          display: flex;
          align-items: center;
          height: 25px;
          font-size: 12px;
          font-weight: normal;
          color: #ffffff;
          position: relative;
          i {
            margin-right: 10px;
            font-size: 14px;
          }
          button {
            margin-left: auto;
            background-color: transparent;
            padding: 0;
            border: none;
            .mdi {
              color: #cccccc;
              transition: 0.3s ease;
              margin-right: 0;
              font-size: 12px;
            }
            &:hover, &:focus {
              .mdi {
                color: #ffffff;
              }
            }
          }
        }
        .tabs-text{
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
          margin-right: 5px;
        }
        &:focus{
          box-shadow: none;
        }
      }
      .el-tabs__item.is-active {
        border-bottom-color: transparent;
        background-color: #ffffff;
        color: #000000;
        span {
          color: #000000;
          i {
            color: #000000;
          }
          button {
            color: #000000;
            .mdi {
              color: #cccccc;
            }
            &:hover, &:focus {
              .mdi {
                color: #000000;
              }
            }
          }
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

  .tabs-wrapper {
    flex-grow: 2;
    display: flex;
    flex-direction: column;
  }

  .notify-wrapper{
    position: absolute;
    top: 0;
    bottom: 0;
    z-index: 999;
    background-color: #ffffff;
    overflow: hidden;
    width: 300px;
    display: flex;
    flex-direction: column;
    .notify__header{
      height: 30px;
      min-height: 30px;
      display: flex;
      align-items: center;
      padding: 0 10px;
      justify-content: space-between;
      border-bottom: solid 1px #cccccc;
      .notify__header-close{
        display: flex;
      }
      button{
        padding: 0;
        border: none;
        font-size: 12px;
        color: #888888;
        transition: 0.3s ease;
        &:hover{
          color: #161a24;
        }
      }
      .notify__header-title{
        font-size: 12px;
        font-weight: 500;
        color: #37474f;
      }
      .el-badge__content{
        height: 20px;
      }
    }


    .notify__body{
      overflow-y: auto;
      &::-webkit-scrollbar {
        width: 6px;

      }

      &::-webkit-scrollbar-thumb {
        width: 6px;
        background: #cccccc;
        border-radius: 3px;
      }

      &::-webkit-scrollbar-track {
        width: 6px;
        background: #eceff1;
        cursor: pointer;
      }
    }

    .notify{
      position: relative;
      display: flex;
      flex-wrap: wrap;
      padding: 5px 10px;
      transition: 0.3s ease;
      opacity: 0.6;
      cursor: pointer;
      .notify__titles{
        display: flex;
        align-items: center;
        flex-basis: 100%;
      }
      .notify__titles-icon{
        margin-right: 5px;
        color: #37474f;
        font-size: 12px;
      }
      .notify__titles-title{
        font-size: 12px;
        font-weight: 500;
        color: #37474f;
      }
      .notify__titles-button{
        margin-left: auto;
        button{
          color: white;
          padding: 0;
          border: none;
          background-color: transparent;
          .mdi{
            transition: 0.3s ease;
          }
          &:hover{
            .mdi{
              color: black;
            }
          }
        }
      }
      .notify__text{
        flex-basis: 100%;
        font-size: 12px;
        margin-left: 17px;
        color: #37474f;
        padding-right: 15px;
      }
      .notify__time{
        flex-basis: 100%;
        font-size: 11px;
        font-weight: normal;
        color: #888888;
        margin-left: 17px;
        .mdi{
          margin-right: 5px;
        }
      }
      .notify__buttons{
        margin-top: 5px;
        padding-left: 17px;
      }
      &:hover{
        background-color: #eceff1;
        opacity: 1;
        .notify__titles-button{
          .mdi{
            color: #888888;
          }
        }
      }
    }
    .notify-new{
      opacity: 1;
      .notify__titles-button{
        visibility: hidden;
      }
      &:before{
        position: absolute;
        content: "";
        right: 15px;
        top: 15px;
        width: 5px;
        height: 5px;
        background-color: #ff5722;
        border-radius: 50%;
      }
    }

    .notify-err{
      .notify__titles{
        .notify__titles-icon{
          .mdi{
            color: #ff5722;
          }
        }
        .notify__titles-title{
          color: #ff5722;
        }
      }
    }

    .notify-success{
      .notify__titles{
        .notify__titles-icon{
          .mdi{
            color: #67c23a;
          }
        }
        .notify__titles-title{
          color: #67c23a;
        }
      }
    }

    .notify-warning{
      .notify__titles{
        .notify__titles-icon{
          .mdi{
            color: #E6A23C;
          }
        }
        .notify__titles-title{
          color: #E6A23C;
        }
      }
    }
  }

  .notify-wrapper-active{
    animation: notify  0.5s ease-in-out;
    animation-fill-mode: forwards;
  }

  .footer {
    height: 30px;
    background-color: #263238;
    min-height: 30px;
    display: flex;
    padding: 0 10px;
    align-items: center;
    .footer-title{
      font-size: 11px;
      font-weight: normal;
      color: #cccccc;
      margin-right: 10px;
    }
    .footer-refresh{
      display: flex;
      button{
        font-size: 11px;
        font-weight: 500;
        color: #ff5722;
        padding: 0;
        .mdi{
          margin-right: 5px;
        }
      }
    }
    .footer-loading{
      display: flex;
      button{
        font-size: 11px;
        opacity: 1;
        font-weight: 500;
        color: #cccccc;
        padding: 0;
        &:before{
          display: none;
        }
      }
    }
  }
</style>
