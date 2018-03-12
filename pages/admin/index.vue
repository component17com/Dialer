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
        <div class="right__header-title">Автосалоны</div>
        <el-button class="rheader__buttons-new" size="small"><i class="mdi mdi-plus"></i>Добавить автосалон</el-button>
      </div>
      <div class="adminContent">
        <el-table
          :data="tableData"
          border
          class="adminTable"
          stripe>
          <el-table-column
            label="Название автосалона">
            <template slot-scope="scope">
              <div class="adminTable__name">{{ scope.row.name }}</div>
            </template>
          </el-table-column>
          <el-table-column
            label="Адрес">
            <template slot-scope="scope">
              <div class="adminTable__adress">{{ scope.row.address }}</div>
            </template>
          </el-table-column>
          <el-table-column
            label="Контакты">
            <template slot-scope="scope">
              <div class="adminTable__contacts">{{ scope.row.contact }}</div>
              <div class="adminTable__contacts">{{ scope.row.contact }}</div>
            </template>
          </el-table-column>
          <el-table-column
            label="Действия"
            align="center">
            <template slot-scope="scope">
              <el-button
                size="mini"
                type="primary"
                icon="mdi mdi-information">
              </el-button>
              <el-button
                size="mini"
                type="danger"
                icon="mdi mdi-delete">
              </el-button>
            </template>
          </el-table-column>
        </el-table>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        tableData: [{
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          contact: '2222'
        }, {
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          contact: '2222'
        }, {
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          contact: '2222'
        }, {
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles',
          contact: '2222'
        }]
      }
    }
  }
</script>

<style lang="scss">
  *{
    font-family: 'Open Sans', sans-serif;
  }
  .admin-container{
    display: flex;
    height: 100vh;
    overflow: hidden;
    .admin__left {
      overflow-y: auto;
      display: flex;
      flex-direction: column;
      width: 240px;
      min-width: 240px;
      background-color: #303133;
    }
    .admin__left-title {
      font-size: 14px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.93;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      background-color: #409eff;
      padding: 13px;
      span {
        font-size: 16px;
        font-weight: 600;
        line-height: 1.69;
      }
    }
    .left__models {
      display: flex;
      flex-direction: column;
      flex-grow: 2;
      overflow-y: auto;
      padding: 0 15px 15px 15px;
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
    .left__model {
      min-height: 50px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: solid 1px #f2f6fc;
      font-size: 14px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      text-decoration: none;
    }
    .admin__right {
      flex-grow: 2;
      display: flex;
      flex-direction: column;
    }
    .right__header-top {
      display: flex;
      background-color: #161a24;
      padding: 5px 15px 5px 15px;
      align-items: center;
    }
    .rheader__top-name {
      margin-left: auto;
      font-size: 12px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      color: #ffffff;
    }
    .button-icon {
      margin-left: 15px;
      border: none;
      background-color: transparent;
      color: #ffffff;
      width: 20px;
      height: 20px;
      min-height: 10px;
      min-width: 10px;
      padding: 0;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .right__header-buttons {
      padding: 7px 15px 8px 15px;
      display: flex;
      align-items: center;
      background-color: #303133;
    }
    .rheader__buttons-new {
      margin-left: auto;
      border-radius: 3px;
      background-color: #409eff;
      border: none;
      font-size: 12px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.5;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      .mdi {
        margin-right: 10px;
      }
    }
    .right__header-title{
      font-size: 22px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.09;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
    }
    .adminContent {
      display: flex;
      flex-direction: column;
      flex-grow: 2;
      overflow-y: auto;
      padding: 15px;
      &::-webkit-scrollbar {
        width: 8px;
      }

      &::-webkit-scrollbar-thumb {
        background: #888888;
      }

      &::-webkit-scrollbar-track {
        background: #cccccc;
        cursor: pointer;
      }
    }
    .adminTable{
      font-size: 14px;
      text-align: left;
      color: #303133;
      .has-gutter{
        tr{
          th{
            padding: 0;
            font-size: 12px;
            color: #606266;
            font-weight: normal;
          }
        }
      }
      button{
        padding: 0;
        width: 30px;
        height: 30px;
      }
    }
  }
</style>
