<template>
  <div class="admin-container">
    <div :class="menuClass">
      <div class="admin__left-title">Администрирование <br><span>АвтоЛидер</span></div>
      <div class="admin__left-buttons">
        <div class="admin__left-name">Перов Иван (админитстратор)</div>
        <el-button type="text" class="admin__left-button">Настройки</el-button>
        |
        <el-button type="text" class="admin__left-exit">Выйти</el-button>
      </div>
      <div class="left__models">
        <nuxt-link to="" class="left__model" v-for="item in 70" :key="item">Автосалоны</nuxt-link>
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
        <div class="admin__left-button">
          <el-button @click="adminChange()"><i class="mdi mdi-menu"></i></el-button>
        </div>
        <div class="right__header-title">Сотрудники</div>
        <el-button class="rheader__buttons-new" size="small"><i class="mdi mdi-plus"></i>Добавить сотрудника</el-button>
      </div>
      <div class="adminContent">
        <div class="adminContent__buttons">
          <div class="adminContent__buttons-search">
            <el-input
              placeholder="Поиск по сотрудникам"
              prefix-icon="el-icon-search"
              size="small">
            </el-input>
          </div>
          <div class="adminContent__buttons-actions">
            <el-dropdown trigger="click" size="small">
              <el-button size="small">
                Массовые действия<i class="el-icon-arrow-down el-icon--right" style="margin-left: 10px"></i>
              </el-button>
              <el-dropdown-menu slot="dropdown">
                <el-dropdown-item>Action 1</el-dropdown-item>
                <el-dropdown-item>Action 2</el-dropdown-item>
                <el-dropdown-item>Action 3</el-dropdown-item>
                <el-dropdown-item>Action 4</el-dropdown-item>
                <el-dropdown-item>Action 5</el-dropdown-item>
              </el-dropdown-menu>
            </el-dropdown>
          </div>
        </div>
        <el-table
          :data="tableData"
          stripe
          border
          class="adminTable"
          style="width: 100%">
          <el-table-column
            type="selection"
            width="55"
            align="center">
          </el-table-column>
          <el-table-column
            prop="name"
            label="ФИО сотрудника">
          </el-table-column>
          <el-table-column
            label="Салон">
            <template slot-scope="scope">
              <div class="adminTable__select">
                <el-select v-model="value8" filterable placeholder="Select" size="small">
                  <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
                  </el-option>
                </el-select>
              </div>
            </template>
          </el-table-column>
          <el-table-column
            prop="phone"
            label="Телефон">
          </el-table-column>
          <el-table-column
            prop="mail"
            label="E-mail">
          </el-table-column>
          <el-table-column
            label="Администратор"
            width="115px"
            align="center">
            <template slot-scope="scope">
              <div class="adminTable__check">
                <el-checkbox></el-checkbox>
              </div>
            </template>
          </el-table-column>
          <el-table-column
            label="Действия"
            align="center">
            <template slot-scope="scope">
              <el-button
                size="mini"
                type="success"
                plain
                icon="mdi mdi-pencil">
              </el-button>
              <el-button
                size="mini"
                type="danger"
                plain
                icon="mdi mdi-block-helper">
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
      <div class="crmRight__footer">
        <div class="footer__save">
          <el-button>Сохранить</el-button>
        </div>
        <div class="footer__cancel">
          <el-button>Отмена</el-button>
        </div>
        <div class="footer__up">
          <el-button><i class="mdi mdi-arrow-up"></i></el-button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        value8: '',
        tableData: [{
          name: 'Соловьёв Яков Мечиславович',
          phone:'+7 (800) 550-99-42',
          mail: 'example@mail.ru',
        }, {
          name: 'Яппаров Никита ',
          phone:'+7 (800) 550-99-42',
          mail: 'example@mail.ru',
        }, {
          name: 'Топоркова Зоя Алексеевна ',
          phone:'+7 (800) 550-99-42',
          mail: 'example@mail.ru',
        }, {
          name: 'Болтоногов Лев Игоревич ',
          phone:'+7 (800) 550-99-42',
          mail: 'example@mail.ru',
        }],
        multipleSelection: [],
        startTime: '',
        endTime: '',
        menuClass: 'admin__left',
        adminLeftOpen: false,
        isCollapse: true,
        dialogVisible: false
      };

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

<style scoped lang="scss">


</style>
