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
          <div class="crmRight__title-text">Редактировать отзыв</div>
          <el-button class="crmRight__title-close" type="primary"><i class="mdi mdi-close"></i></el-button>
        </div>
        <div class="crmRight__reviewsEdit">
          <div class="crmRight__reviewsEdit-status">
            <div class="status__verified"><i class="mdi mdi-check-circle"></i>Проверено</div>
            <div class="status__verification"><i class="mdi mdi-check-circle"></i>Статус 2</div>
            <div class="status__fail"><i class="mdi mdi-check-circle"></i>Статус 3</div>
          </div>
          <el-form>
          <div class="crmRight__reviewsEdit-inputs">
              <el-form-item label="Дата публикации">
                <el-input placeholder="29.12.2017, 18:20" size="small"></el-input>
              </el-form-item>
              <el-form-item label="Имя">
                <el-input placeholder="Сергей Валерьевич" size="small"></el-input>
              </el-form-item>
            <el-form-item label="Купленный автомобиль">
              <el-input placeholder="Марка и модель автомобиля" size="small"></el-input>
            </el-form-item>
          </div>
            <div class="crmRight__reviewsEdit-textareas">
              <el-form-item label="Текст отзыва">
                <el-input type="textarea" size="small"></el-input>
              </el-form-item>
              <el-form-item label="Ответ на отзыв">
                <el-input type="textarea" placeholder="Напишите ответ автору отзыва" size="small"></el-input>
              </el-form-item>
            </div>
            <div class="collapse__image-upload">
              <div class="image-uploader-title">Добавить фото</div>
              <el-upload class="image-uploader">
                <i class="el-icon-plus avatar-uploader-icon"></i>
              </el-upload>
            </div>
          </el-form>
        </div>
      </div>
      <!--Подвал правой колонки-->
      <div class="crmRight__footer">
        <div class="footer__saves">
          <el-button type="primary">Сохранить</el-button>
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
  };
</script>

<style lang="scss">
  .crmRight__reviewsEdit-status{
    display: flex;
    align-items: center;
    margin-top: 15px;
    .status__verified{
      border-radius: 3px;
      background-color: #67c23a;
      display: flex;
      align-items: center;
      height: 32px;
      padding-left: 15px;
      padding-right: 15px;
      font-size: 12px;
      font-weight: 600;
      color: #ffffff;
      margin-right: 15px;
      .mdi{
        font-size: 16px;
        margin-right: 10px;
      }
    }
    .status__verification{
      border-radius: 3px;
      background-color: #7f828b;
      display: flex;
      align-items: center;
      height: 32px;
      padding-left: 15px;
      padding-right: 15px;
      font-size: 12px;
      font-weight: 600;
      color: #ffffff;
      margin-right: 15px;
      .mdi{
        font-size: 16px;
        margin-right: 10px;
      }
    }
    .status__fail{
      border-radius: 3px;
      background-color: #f56c6c;
      display: flex;
      align-items: center;
      height: 32px;
      padding-left: 15px;
      padding-right: 15px;
      font-size: 12px;
      font-weight: 600;
      color: #ffffff;
      margin-right: 15px;
      .mdi{
        font-size: 16px;
        margin-right: 10px;
      }
    }
  }
  .crmRight__reviewsEdit-inputs, .crmRight__reviewsEdit-textareas{
    display: flex;
    align-items: center;
    margin-top: 20px;
    .el-form-item{
      flex-grow: 2;
      .el-form-item__label{
        line-height: 2.0;
        font-size: 13px;
        font-weight: normal;
        color: #606266;
      }
      textarea{
        resize: none;
        height: 145px;
        border-radius: 4px;
        background-color: #ffffff;
        border: solid 1px #c0c4cc;
      }
    }
    .el-form-item:not(:last-child){
      margin-right: 30px;
    }
  }
  .collapse__image-upload{
    .image-uploader-title{
      margin-top: 20px;
      font-size: 13px;
      color: #606266;
      margin-bottom: 10px;
    }
  }
</style>
