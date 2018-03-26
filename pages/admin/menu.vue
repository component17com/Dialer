<template>
  <div class="admin-container">
    <div :class="menuClass">
      <div class="admin__left-menu">
        <div class="admin__left-buttons">
          <div class="admin__left-name">Перов Иван (админитстратор)</div>
          <el-button class="admin__left-setting">Настройки</el-button>
          <el-button class="admin__left-exit">Выйти</el-button>
        </div>
        <div class="admin__left-title">Администрирование<br><span>АвтоЛидер</span></div>
      <div class="left__models">
        <nuxt-link to="" class="left__model" v-for="item in 70" :key="item">Автосалоны</nuxt-link>
        <nuxt-link to="" class="left__model">Сотрудники</nuxt-link>
        <nuxt-link to="" class="left__model">Справочник атомобилей</nuxt-link>
      </div>
      </div>
    </div>

    <div class="admin__right">
      <div class="right__header-top">
        <div class="rheader__top-name">Перов Иван (админитстратор)</div>
        <el-button class="button-icon rheader__top-button"><i class="mdi mdi-settings"></i></el-button>
        <el-button class="button-icon rheader__top-exit"><i class="mdi mdi-exit-to-app"></i></el-button>
      </div>
      <div class="right__header-buttons">
        <div class="admin__left-button">
          <el-button @click="adminChange()"><i class="mdi mdi-menu"></i></el-button>
        </div>
        <div class="right__header-title">Автосалоны</div>
        <el-button class="rheader__buttons-new" size="small"><i class="mdi mdi-plus"></i>Добавить автосалон</el-button>
      </div>
      <div class="adminContent">
        22
      </div>

    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        menuClass: 'admin__left',
        adminLeftOpen: false,
      }
    },
    methods: {
      adminChange(){
        const TIMEOUT = 400;

        if(this.adminLeftOpen){
          this.menuClass = 'admin__left adminLeftClose'
          this.adminLeftOpen = false;

        }else{
          this.menuClass = 'admin__left adminLeftOpen'
          setTimeout(() => {
            this.menuClass = 'admin__left adminLeftOpen adminLeftOver'
            this.adminLeftOpen = true;
          }, TIMEOUT);
        }
      }
    }
  }
</script>

<style lang="scss">
  @keyframes openLeft {
    from {height: 0}
    to {height: calc(100% - 50px);}
  }
  @keyframes closeLeft {
    from {height: calc(100% - 50px);}
    to {height: 0px;}
  }
  .admin__left-button{
    display: none;
  }
  .admin__left-buttons{
    display: none;
  }
  @media screen and (min-width: 768px) and (max-width: 991px){
    .admin-container{
      .admin__left {
        position: absolute;
        top: 50px;
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 0;
        min-width: 0;
        max-width: 100%;
        background-color: #303133;
        overflow: hidden;
        .left__models{
          overflow-x: hidden;
        }
        .admin__left-buttons{
          display: flex;
          align-items: center;
          padding:5px 15px;
        }
      }
      .adminLeftClose{
        animation: closeLeft  0.3s linear;
        animation-fill-mode: forwards;
      }
      .adminLeftOpen{
        animation: openLeft  0.3s linear;
        animation-fill-mode: forwards;
        &::-webkit-scrollbar {
          width: 4px;
        }

        &::-webkit-scrollbar-thumb {
          background: #cccccc;
        }

        &::-webkit-scrollbar-track {
          background: #888888;
          cursor: pointer;
        }
      }
      .adminLeftOver{
        overflow-y: auto;
      }
      .admin__left-button{
        display: block;
        button{
          display: flex;
          align-items: center;
          justify-content: center;
          border: none;
          padding: 0;
          background-color: transparent;
          width: 50px;
          height: 50px;
          font-size: 30px;
          color: white;
        }
      }
      .right__header-top{
        display: none;
      }
      .right__header-buttons {
        padding: 7px 15px 8px 0;
      }
      .left__model {
        white-space: nowrap;
        text-overflow: ellipsis;
        overflow: hidden;
      }
    }
  }
</style>
