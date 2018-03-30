<template>
  <div class="crm-container">

    <!--Левая колонка-->
    <div :class="menuClass">
      <div class="admin__left-buttons">
        <div class="admin__left-name">АвтоЛидер Варшавка</div>
        <el-button type="text" class="admin__left-button">Настройки</el-button>
        |
        <el-button type="text" class="admin__left-exit">Выйти</el-button>
      </div>
      <div class="crm__left-title">Система управления <span>АвтоЛидер Варшавка</span></div>
      <div class="left__adverts">
        <div class="left__adverts-all">Все обьявления
          <el-badge class="crm-tag" :value="999"/>
        </div>
        <div class="left__adverts-search">
          <el-input placeholder="Поиск по марке" prefix-icon="el-icon-search" size="small"></el-input>
        </div>
      </div>
      <div class="left__models">
        <nuxt-link to="" class="left__model" v-for="item in 70" :key="item">Audi
          <el-badge class="crm-tag" :value="4"/>
        </nuxt-link>
        <nuxt-link to="" class="left__model">Bmw
          <el-badge class="crm-tag" :value="4"/>
        </nuxt-link>
        <nuxt-link to="" class="left__model">Chery
          <el-badge class="crm-tag" :value="4"/>
        </nuxt-link>
      </div>
    </div>
    <!--Правая колонка-->
    <div class="crm__right">
      <!--Шапка правой колонки-->
      <div class="right__header">
        <div class="right__header-top">
          <div class="rheader__top-message">Не весь <span>лимит поднятий в ТОП</span> использован!</div>
          <div class="rheader__top-name">АвтоЛидер Варшавка</div>
          <el-button class="button-icon rheader__top-button"><i class="mdi mdi-settings"></i></el-button>
          <el-button class="button-icon rheader__top-exit"><i class="mdi mdi-exit-to-app"></i></el-button>
        </div>
        <div class="right__header-buttons">
          <div class="admin__left-button">
            <el-button @click="adminChange()"><i class="mdi mdi-menu"></i></el-button>
          </div>
          <el-button class="rheader__button rheader__buttons-archive" title="Архив (кол-во)">
            <i class="mdi mdi-delete"></i>
            <div class="rheader__button-text">Архив</div>
            <el-badge class="crm-tag" :value="4"/>
          </el-button>
          <el-button class="rheader__button rheader__buttons-print" title="Распечатать прайс">
            <i class="mdi mdi-printer"></i>
            <div class="rheader__button-text">Распечатать прайс</div>
          </el-button>
          <!--Сайты-->
          <el-dropdown class="application__management" placement="bottom-start">
      <span class="el-dropdown-link">
          <el-button class="rheader__button rheader__buttons-sites" title="Cайты">
            <i class="mdi mdi-laptop-chromebook"></i><div class="rheader__button-text">Cайты</div>
          </el-button>
      </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>
                <nuxt-link to="">Auto.ru</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to="">Avito</nuxt-link>
              </el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <!--Управление заявками-->
          <el-dropdown class="application__management" placement="bottom-start">
      <span class="el-dropdown-link">
        <el-button class="rheader__button rheader__buttons-control" title="Управление заявками">
          <i class="mdi mdi-file-find"></i><div class="rheader__button-text">Управление заявками</div>
        </el-button>
      </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-currency-usd"></i>Кредит</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-wallet"></i>Выкуп</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-file"></i>Заявки авто</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-phone"></i>Перезвонить</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-message-reply-text"></i>Отзывы</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-headset"></i>Консультант</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-clipboard-text"></i>Новости</nuxt-link>
              </el-dropdown-item>
              <el-dropdown-item>
                <nuxt-link to=""><i class="mdi mdi-help-circle"></i>Обратная связь</nuxt-link>
              </el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-input class="rheader__buttons-search" placeholder="Номер объявления" prefix-icon="el-icon-search"
                    size="small"></el-input>
          <el-button class="rheader__buttons-new" size="small"><i class="mdi mdi-plus"></i>Новое объявление
          </el-button>
        </div>
      </div>
      <!--Контент правой колонки-->
      <div class="crmRight">
        <div class="crmRight__title">
          <div class="crmRight__title-text">Архив объявлений</div>
        </div>
        <div class="crmRight__selects">
          <div class="crmRight__selects-marks">
            <div class="marks-title">Выберите марку</div>
            <div class="marks-select">
              <el-select v-model="value" size="small" multiple placeholder="Select">
                <el-option
                  v-for="item in options"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
              </el-select>
            </div>
          </div>
          <div class="crmRight__selects-models">
            <div class="models-title">Выберите модель {сюда марку из селекта}</div>
            <div class="models-select">
              <el-select v-model="value" placeholder="Выберите модель" size="small" disabled>
                <el-option
                  v-for="item in options"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
              </el-select>
            </div>
          </div>
        </div>
        <div class="crmRight__tables">
          <el-table
            :data="tableData"
            border
            class="crmRight__table"
            stripe>
            <el-table-column
              label="#"
              width="90px"
              align="center">
              <template slot-scope="scope">
                <div class="crmTable__id">{{ scope.row.id}}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Фото"
              width="160px">
              <template slot-scope="scope">
                <div class="crmTable__foto">
                  <img :src="scope.row.photo" class="crmTable__foto-img" :title="scope.row.model">
                </div>
              </template>
            </el-table-column>
            <el-table-column
              label="Марка / Модель"
            min-width="250px">
              <template slot-scope="scope">
                <div class="crmTable-model">{{ scope.row.model}} <span>{{ scope.row.year}}</span></div>
                <div class="crmTable-modelInfo">{{ scope.row.modelInfo}}</div>
                <div class="crmTable-modelKm">{{ scope.row.modelKm}} ,<span>{{ scope.row.modelBody}}</span></div>
                <div class="crmTable-modelColor">
                  <div class="crmTable-modelColorHEX"
                       :style="`background-color: ${scope.row.modelColor}; border-color: ${scope.row.modelColor}`"></div>
                  <span>{{ scope.row.modelColorName}}</span>
                </div>
              </template>
            </el-table-column>
            <el-table-column
              label="Цена"
              width="160px"
              align="center">
              <template slot-scope="scope">
                <div class="crmTable__salePrice">{{ scope.row.salePrice}}</div>
                <div class="crmTable__price">{{ scope.row.price}}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Добавлено"
              align="center"
              width="150px">
              <template slot-scope="scope">
                <div class="crmTable-date">{{ scope.row.date}}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Удалено"
              align="center"
              width="150px">
              <template slot-scope="scope">
                <div class="crmTable-refresh">{{ scope.row.dateDelete}}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Восстановить"
              align="center"
              width="120px">
              <template slot-scope="scope">
                <div class="crmTable-buttons">
                  <el-button
                    size="small"
                    type="success"
                    icon="mdi mdi-refresh">
                  </el-button>
                </div>

              </template>
            </el-table-column>
          </el-table>
        </div>
      </div>
      <!--Подвал правой колонки-->
      <div class="crmRight__footer">
        <div class="footer__pagination">
          <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :current-page.sync="currentPage4"
            :page-sizes="[100, 200, 300, 400]"
            :page-size="100"
            layout="slot, sizes, prev, pager, next"
            :total="400">
            <template slot>Показать по</template>
          </el-pagination>
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
        tableData: [{
          id: '999999',
          photo: './img/scoda.jpg',
          price: '11 332 000 руб.',
          salePrice: '332 000 руб.',
          model: 'Skoda Octavia',
          modelInfo: 'III(C6) Рестайлинг 1,6 AT (110 л.с.)',
          modelKm: '999 999 км',
          modelBody: 'Седан',
          modelColor: '#409eff',
          modelColorName: 'Синий',
          phone: '+7 (999) 999-9999',
          date: '09.12.2017',
          dateDelete:'09.01.2018',
          year: '2016',
        }, {
          id: '999999',
          photo: './img/scoda.jpg',
          price: '11 332 000 руб.',
          salePrice: '332 000 руб.',
          model: 'Skoda Octavia',
          modelInfo: 'III(C6) Рестайлинг 1,6 AT (110 л.с.)',
          modelKm: '999 999 км',
          modelBody: 'седан',
          modelColor: '#ff3315',
          modelColorName: 'Красный',
          phone: '+7 (999) 999-9999',
          date: '09.12.2017',
          dateDelete:'09.01.2018',
          year: '2016',
        }],
        options: [{
          value: 'Option1',
          label: 'Option1'
        }, {
          value: 'Option2',
          label: 'Option2'
        }, {
          value: 'Option3',
          label: 'Option3'
        }, {
          value: 'Option4',
          label: 'Option4'
        }, {
          value: 'Option5',
          label: 'Option5'
        }],
        value: '',
        menuClass: 'crm__left',
        adminLeftOpen: false,
        isCollapse: true,
      };
    },
    methods: {
      adminChange(){
        const TIMEOUT = 400;

        if(this.adminLeftOpen){
          this.menuClass = 'crm__left adminLeftClose'
          this.adminLeftOpen = false;

        }else{
          this.menuClass = 'crm__left adminLeftOpen'
          setTimeout(() => {
            this.menuClass = 'crm__left adminLeftOpen adminLeftOver'
            this.adminLeftOpen = true;
          }, TIMEOUT);
        }
      }
    },
    mounted() {
      let text = 'Привет';
      let str1 = text + ' Мир ' + text;

      let str2 = `${text} Мир ${text}`;

      console.log(str2)
    }
  };
</script>

<style lang="scss">

</style>
