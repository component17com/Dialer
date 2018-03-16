<template>
  <div class="crm-container">

    <!--Левая колонка-->
    <div class="crm__left">
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
          <div class="crmRight__title-text">Отзывы и комментарии</div>
        </div>
        <div class="crmRight__date">
          <el-date-picker
            v-model="value7"
            type="daterange"
            unlink-panels
            range-separator="по"
            start-placeholder="Начальная дата"
            end-placeholder="Конечная дата"
            :picker-options="pickerOptions2"
            size="small">
          </el-date-picker>
          <el-button size="small" type="primary">Поиск</el-button>
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
                <div class="crmTable__id">{{ scope.row.id }}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Время"
            width="180px">
              <template slot-scope="scope">
                <div class="crmTable__time">{{ scope.row.time }}</div>
                <div class="crmTable__from">{{ scope.row.from }}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Имя"
            width="180px">
              <template slot-scope="scope">
                <div class="crmTable__name">{{ scope.row.name }}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Текст">
              <template slot-scope="scope">
                <div class="crmTable-auto">Приобретенный автомобиль: {{ scope.row.auto }}</div>
                <div class="crmTable__text">{{ scope.row.text }}</div>
              </template>
            </el-table-column>
            <el-table-column
              label="Публикация"
              align="center"
            width="180px">
              <template slot-scope="scope">

                <template v-if="!publick">
                <el-button
                  size="small"
                  type="primary"
                  style="width: 120px"
                  @click.native="publick = true">
                  Опубликовать
                </el-button>
                </template>
                <template v-else>
                  <div class="crmTable__publick-success">
                    <i class="mdi mdi-checkbox-marked-circle" style="color: #67c23a;"></i>
                    <div class="publick-success-text">Опубликовано</div>
                  </div>
                </template>

              </template>
            </el-table-column>
            <el-table-column
              label="Удалить"
              align="center"
              width="70px">
              <template slot-scope="scope">
                <el-button
                  size="small"
                  type="danger"
                  icon="mdi mdi-delete">
                </el-button>
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
        publick: false,
        currentPage4: 4,
        pickerOptions2: {
          shortcuts: [{
            text: 'Last week',
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 7);
              picker.$emit('pick', [start, end]);
            }
          }, {
            text: 'Last month',
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 30);
              picker.$emit('pick', [start, end]);
            }
          }, {
            text: 'Last 3 months',
            onClick(picker) {
              const end = new Date();
              const start = new Date();
              start.setTime(start.getTime() - 3600 * 1000 * 24 * 90);
              picker.$emit('pick', [start, end]);
            }
          }]
        },
        value6: '',
        value7: '',
        tableData: [{
          id: '999999',
          time:'09.12.2017, 11:28',
          from: '(АвтоЛидер Варшавка)',
          name: 'Сергей Валерьевич',
          auto: 'lancer 10',
          text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
        }, {
          id: '999999',
          time:'09.12.2017, 11:28',
          from: '(АвтоЛидер Варшавка)',
          name: 'Сергей Валерьевич',
          auto: 'lancer 10',
          text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
        }, {
          id: '999999',
          time:'09.12.2017, 11:28',
          from: '(АвтоЛидер Варшавка)',
          name: 'Светлана Николаевна',
          auto: 'не указано',
          text:'Нормальный автосалон, купил тут машину на днях, Киа Сид. Вышел по акции на 630 тысяч, уже с автоматической коробкой и в хорошей',
        }, {
          id: '999999',
          time:'09.12.2017, 11:28',
          from: '(АвтоЛидер Варшавка)',
          name: 'Светлана Николаевна',
          auto: 'lancer 10',
          text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
        }
          , {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'lancer 10',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }
          , {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'не указано',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }
          , {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'не указано',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }, {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'не указано',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }, {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'не указано',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }, {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'не указано',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }, {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'не указано',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }, {
            id: '999999',
            time:'09.12.2017, 11:28',
            from: '(АвтоЛидер Варшавка)',
            name: 'Светлана Николаевна',
            auto: 'не указано',
            text: 'От посещения автосалона у меня остались лишь положительные эмоции. Увидел их салон на авито, там они с 2014 года, и это уже о чем-то говорит.',
          }],

      };
    }
  };
</script>

<style scoped lang="scss">

</style>
