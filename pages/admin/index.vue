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

</style>
