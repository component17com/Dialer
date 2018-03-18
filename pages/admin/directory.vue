<template>
  <div class="admin-container">
    <div class="admin__left">
      <div class="admin__left-title">Администрирование <br><span>АвтоЛидер</span></div>
      <div class="left__models">
        <nuxt-link to="" class="left__model" v-for="item in 7" :key="item">Автосалоны</nuxt-link>
        <nuxt-link to="" class="left__model">Сотрудники</nuxt-link>
        <nuxt-link to="" class="left__model">Справочник атомобилей</nuxt-link>
      </div>
    </div>
    <div class="admin__right">
      <div class="right__header-top">
        <div class="rheader__top-name">Перов Иван (админитстратор)</div>
        <el-button class="button-icon rheader__top-button"><i class="mdi mdi-settings"></i></el-button>
        <el-button class="button-icon rheader__top-exit"><i class="mdi mdi-exit-to-app"></i></el-button>
      </div>
      <div class="right__header-buttons">
        <div class="right__header-title">Справочник автомобилей</div>
      </div>
      <div class="adminContent">
        <div class="directory-row">
          <div class="directory directory__marka">
            <div class="directory__titles">
              <div class="directory__titles-title">Марка</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">AC</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">Acura</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__model">
            <div class="directory__titles">
              <div class="directory__titles-title">Модель</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">1 SERIES</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">4 SERIES GRAN COUPE</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__pokolenie">
            <div class="directory__titles">
              <div class="directory__titles-title">Поколение</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">E30 [1982 - 1987]</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">E90/E91/E92/E93 [рестайлинг] [2008 - 2013]</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__series">
            <div class="directory__titles">
              <div class="directory__titles-title">Серия</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">Compact хетчбэк</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">Touring универсал</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__modify">
            <div class="directory__titles">
              <div class="directory__titles-title">Модификация</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">316i AT (102 л.с.)</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">316i MT (102 л.с.)</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__complect">
            <div class="directory__titles">
              <div class="directory__titles-title">Комплектация</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">Нет данных</div>
                </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {

  }
</script>

<style lang="scss">
  .directory-row{
    display: flex;
    flex-grow: 2;
  }
  .directory{
    flex-basis: 16.6666666%;
    display: flex;
    flex-direction: column;
    border-radius: 4px;
    border: solid 1px #cccccc;
    overflow: hidden;
  }
  .directory:not(:last-child){
    border-right: none;
  }
  .directory__titles{
    padding: 10px 5px;
    background-color: #ebeef5;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    min-height: 76px;
  }
  .directory__titles-title{
    font-size: 14px;
    font-weight: 600;
    color: #303133;
    text-transform: uppercase;
  }
  .directory__titles-button{
    margin-left: auto;
    padding: 0;
    background-color: transparent;
    border: none;
    color: #303133;
    font-size: 16px;
  }
  .directory__titles-search{
    flex-basis: 100%;
    margin-top: 5px;
    input{
      width: 100%;
    }
  }
  .directory__column{
    flex-grow: 2;
    overflow-y: auto;
    padding: 10px 5px;
    display: flex;
    flex-direction: column;
    &::-webkit-scrollbar {
      width: 4px;
    }

    &::-webkit-scrollbar-thumb {
      background: #888888;
    }

    &::-webkit-scrollbar-track {
      background: #cccccc;
      cursor: pointer;
    }
  }
  .directory__column-item{
    width: 100%;
    display: flex;
    align-items: center;
    transition: 0.3s ease;
    padding: 5px;
    min-height: 24px;
    .column__item-title{
      font-size: 12px;
      font-weight: normal;
      color: #888888;
    }
    .column__item-button{
      margin-left: auto;
    }
    button{
      padding: 0;
      border: none;
      background-color: transparent;
      i{
        color: white;
      }
    }
    &:hover{
      background-color: #ebeef5;
      .column__item-title{
        color: #409eff;
      }
      button{
        i{
          color: #888888;
        }
      }
    }
  }
  .directory__pokolenie{
    .directory__column-item {
      min-height: 40px;
    }
  }
</style>
