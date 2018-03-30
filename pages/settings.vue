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
          <div class="crmRight__title-text" style="margin-bottom: 15px">Настройки</div>
          <el-button class="crmRight__title-close" type="primary"><i class="mdi mdi-close"></i></el-button>
        </div>
        <div class="crmRight__settings">
          <div class="crmRight__setting crmRight__setting-limints">
            <div class="crmRight__setting-title">Лимиты</div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Лимит объявлений на странице</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Лимит похожих объявлений</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Лимит последних объявлений</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Лимит отзывов</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Лимит отзывов (на главной)</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Лимит новостей</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Лимит новостей (на главной)</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">Специальные предложения</div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-number">
                <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" size="small"></el-input-number>
              </div>
              <div class="setting__item-title">ТОП</div>
            </div>
          </div>
          <div class="crmRight__setting crmRight__setting-other">
            <div class="crmRight__setting-title">Остальное</div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">При выборе поднять марку вверх</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Показать объявления без фотографий</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Код проверки в отзывах и кредите</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Filter in Credit</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Главная страница сайта:</div>
              <div class="setting__item-select">
                <el-select v-model="value8" filterable placeholder="Select" size="small">
                  <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value">
                  </el-option>
                </el-select>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Обновить Auto.ru</div>
              <div class="setting__item-button">
                <el-button size="small" icon="el-icon-refresh" type="info" plain></el-button>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Цены</div>
              <div class="setting__item-button">
                <el-button size="small" icon="el-icon-refresh" type="info" plain></el-button>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Avito XML</div>
              <div class="setting__item-button">
                <el-button size="small" icon="el-icon-refresh" type="info" plain></el-button>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Auto XML</div>
              <div class="setting__item-button">
                <el-button size="small" icon="el-icon-refresh" type="info" plain></el-button>
              </div>
            </div>
          </div>
          <div class="crmRight__setting crmRight__setting-sale">
            <div class="crmRight__setting-title">Дни скидок</div>
            <div class="crmRight__setting-item">
              <el-checkbox-group>
                <el-checkbox label="Понедельник"></el-checkbox>
                <el-checkbox label="Вторник"></el-checkbox>
                <el-checkbox label="Среда"></el-checkbox>
                <el-checkbox label="Четверг"></el-checkbox>
                <el-checkbox label="Пятница"></el-checkbox>
                <el-checkbox label="Суббота"></el-checkbox>
                <el-checkbox label="Воскресенье"></el-checkbox>
              </el-checkbox-group>
            </div>
            <el-input placeholder="Введите скидку в процентах" size="small">
              <template slot="append">%</template>
            </el-input>
          </div>
          <div class="crmRight__setting crmRight__setting-foto">
            <div class="crmRight__setting-title">Менять фото</div>
            <div class="crmRight__setting-item">
              <el-checkbox-group>
                <el-checkbox label="Понедельник"></el-checkbox>
                <el-checkbox label="Вторник"></el-checkbox>
                <el-checkbox label="Среда"></el-checkbox>
                <el-checkbox label="Четверг"></el-checkbox>
                <el-checkbox label="Пятница"></el-checkbox>
                <el-checkbox label="Суббота"></el-checkbox>
                <el-checkbox label="Воскресенье"></el-checkbox>
              </el-checkbox-group>
            </div>
          </div>
          <div class="crmRight__setting crmRight__setting-panel">
            <div class="crmRight__setting-title">Остальное</div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Поднять  в списке всех объявлений</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Объявления без фото в начало списка</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Сменить пользователя</div>
              <div class="setting__item-button">
                <el-button size="small" icon="el-icon-refresh" type="info" plain></el-button>
              </div>
            </div>
          </div>
          <div class="crmRight__setting crmRight__setting-publick">
            <div class="crmRight__setting-title">Настройки публикации</div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">При выборе поднять марку вверх</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Показать объявления без фотографий</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Показать объявления без фотографий</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
            <div class="crmRight__setting-item">
              <div class="setting__item-title">Показать объявления без фотографий</div>
              <div class="setting__item-switch">
                <el-switch
                  v-model="value2"
                  active-color="#13ce66"
                  inactive-color="#ff4949">
                </el-switch>
              </div>
            </div>
          </div>
        </div>

      </div>
      <!--Подвал правой колонки-->
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
        num1: 1,
        value2: true,
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
        value8: '',startTime: '',
        endTime: '',
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
    }
  };
</script>

<style scoped lang="scss">

</style>
