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
        <div class="right__header-title">Добавить автосалон</div>
      </div>
      <div class="adminContent">
        <div class="adminContent-back">
          <nuxt-link to="/"><i class="mdi mdi-arrow-left"></i>Назад</nuxt-link>
        </div>
        <div class="adminContent-info">
          <el-form>
            <div class="contentInfo contentInfo-salon">
              <div class="contentInfo-title"><i class="mdi mdi-domain"></i>Автосалон</div>
              <div class="contentInfo__inputs">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Название автосалона</div>
                    <div class="contentInfo__input-input">
                      <el-input placeholder="Введите название автосалона" size="small"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Адрес салона</div>
                    <div class="contentInfo__input-input">
                      <el-input placeholder="Введите адрес" size="small"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Близжайшее метро</div>
                    <div class="contentInfo__input-select">
                      <el-select size="small" filterable placeholder="- выберите станцию">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Основной телефон</div>
                    <div class="contentInfo__input-input">
                      <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">E-mail</div>
                    <div class="contentInfo__input-input">
                      <el-input placeholder="example@mail.com" size="small"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <div class="contentInfo__time">
                  <el-form-item>
                    <div class="contentInfo__time">
                      <div class="contentInfo__time-title">Начало рабочего дня</div>
                      <el-time-select
                        v-model="startTime"
                        :picker-options="{
                       start: '08:30',
                       step: '00:15',
                       end: '18:30'
                     }"
                        size="small">
                      </el-time-select>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <div class="contentInfo__time">
                      <div class="contentInfo__time-title">Начало рабочего дня</div>
                      <el-time-select
                        v-model="endTime"
                        :picker-options="{
                      start: '08:30',
                      step: '00:15',
                      end: '18:30',
                      minTime: startTime
                    }"
                        size="small">
                      </el-time-select>
                    </div>
                  </el-form-item>
                </div>
                <div class="contentInfo__dopInfo">
                  <el-form-item>
                    <div class="contentInfo__input">
                      <div class="contentInfo__input-title">Дополнительная информация</div>
                      <div class="contentInfo__input-input">
                        <el-input type="textarea" placeholder="Введите текст" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                </div>
              </div>
            </div>
          </el-form>

          <el-form>
            <div class="contentInfo contentInfo__newDepartment">
              <div class="contentInfo-title"><i class="mdi mdi-domain"></i>Отделы</div>
              <div class="contentInfo__newDepartment-button">
                <el-button><i class="mdi mdi-plus"></i>Добавить отдел</el-button>
              </div>
            </div>
          </el-form>

          <el-form>
            <div class="contentInfo__newDepartment-form">
              <div class="newDepartment__form-name">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Название отдела</div>
                    <div class="contentInfo__input-input">
                      <el-input placeholder="Введите название отдела" size="small"></el-input>
                    </div>
                  </div>
                </el-form-item>
              </div>
              <div class="newDepartment__form-check">
                <el-form-item>
                  <div class="contentInfo__check">
                    <div class="contentInfo__check-title">Время работы</div>
                    <div class="contentInfo__check-group">
                      <el-checkbox-group v-model="checkList">
                        <el-checkbox label="Option A"></el-checkbox>
                        <el-checkbox label="Option B"></el-checkbox>
                        <el-checkbox label="Option C"></el-checkbox>
                      </el-checkbox-group>
                    </div>
                  </div>
                </el-form-item>
              </div>
              <div class="newDepartment__form-time">
                <el-form-item>
                  <div class="contentInfo__time">
                    <div class="contentInfo__time-title">Начало рабочего дня</div>
                    <el-time-select
                      v-model="startTime"
                      :picker-options="{
                       start: '08:30',
                       step: '00:15',
                       end: '18:30'
                     }"
                      size="small">
                    </el-time-select>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__time">
                    <div class="contentInfo__time-title">Начало рабочего дня</div>
                    <el-time-select
                      v-model="endTime"
                      :picker-options="{
                      start: '08:30',
                      step: '00:15',
                      end: '18:30',
                      minTime: startTime
                    }"
                      size="small">
                    </el-time-select>
                  </div>
                </el-form-item>
              </div>
              <div class="newDepartment__form-tel">
                <el-form-item>
                  <div class="form__tel-titles">
                    <div class="form__tel-title">Контактные телефоны</div>
                    <el-button class="form__tel-new"><i class="mdi mdi-plus"></i>Добавить телефон</el-button>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="form__tel-inputs">
                    <el-input class="form__tel-input" size="small" placeholder="+7 ( ___ ) ___ __ __"></el-input>
                    <el-input class="form__tel-input" size="small" placeholder="Заголовок"></el-input>
                  </div>
                </el-form-item>
              </div>
              <div class="newDepartment__form-mail">
                <el-form-item>
                  <div class="form__tel-titles">
                    <div class="form__tel-title">Электронная почта</div>
                    <el-button class="form__tel-new"><i class="mdi mdi-plus"></i>Добавить e-mail</el-button>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="form__tel-inputs">
                    <el-input class="form__tel-input" size="small" placeholder="example@mail.com"></el-input>
                    <el-input class="form__tel-input" size="small" placeholder="Заголовок"></el-input>
                  </div>
                </el-form-item>
              </div>
              <div class="newDepartment__form-buttons">
                <el-button class="form__buttons-new" type="primary">Добавить</el-button>
                <el-button class="form__buttons-cancel">Отмена</el-button>
              </div>

            </div>
          </el-form>

          <el-form>
            <div class="contentInfo__department">
              <div class="contentInfo__department-titles">
              <el-form-item>
                  <div class="department__title">Кредитный отдел</div>
                  <el-button><i class="mdi mdi-pencil"></i></el-button>
              </el-form-item>
              </div>
              <div class="contentInfo__department-check">
                <el-form-item>
                  <el-checkbox-group>
                    <el-checkbox label="Пн" disabled></el-checkbox>
                    <el-checkbox label="Вт" disabled></el-checkbox>
                    <el-checkbox label="Ср" disabled></el-checkbox>
                    <el-checkbox label="Чт" disabled></el-checkbox>
                    <el-checkbox label="Пт" disabled></el-checkbox>
                    <el-checkbox label="Сб" disabled></el-checkbox>
                    <el-checkbox label="Вс" disabled></el-checkbox>
                  </el-checkbox-group>
                </el-form-item>
              </div>
              <div class="department__time">
                <el-form-item>
                  <div class="contentInfo__time">
                    <div class="contentInfo__time-title">Начало рабочего дня</div>
                    <el-time-select
                      v-model="startTime"
                      :picker-options="{
                       start: '08:30',
                       step: '00:15',
                       end: '18:30'
                     }"
                      size="small">
                    </el-time-select>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__time">
                    <div class="contentInfo__time-title">Начало рабочего дня</div>
                    <el-time-select
                      v-model="endTime"
                      :picker-options="{
                      start: '08:30',
                      step: '00:15',
                      end: '18:30',
                      minTime: startTime
                    }"
                      size="small">
                    </el-time-select>
                  </div>
                </el-form-item>
              </div>
              <div class="department__form-tel">
                <el-form-item>
                  <div class="form__tel-titles">
                    <div class="form__tel-title">Контактные телефоны</div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="form__tel-inputs">
                    <el-input class="form__tel-input" size="small" placeholder="Заголовок"></el-input>
                    <el-input class="form__tel-input" size="small" placeholder="+7 ( ___ ) ___ __ __"></el-input>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="form__tel-inputs">
                    <el-input class="form__tel-input" size="small" placeholder="Заголовок"></el-input>
                    <el-input class="form__tel-input" size="small" placeholder="+7 ( ___ ) ___ __ __"></el-input>
                  </div>
                </el-form-item>
              </div>
              <div class="department__form-mail">
                <el-form-item>
                  <div class="form__tel-titles">
                    <div class="form__tel-title">Электронная почта</div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="form__tel-inputs">
                    <el-input class="form__tel-input" size="small" placeholder="Заголовок"></el-input>
                    <el-input class="form__tel-input" size="small" placeholder="example@mail.com"></el-input>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="form__tel-inputs">
                    <el-input class="form__tel-input" size="small" placeholder="Заголовок"></el-input>
                    <el-input class="form__tel-input" size="small" placeholder="example@mail.com"></el-input>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="form__tel-inputs">
                    <el-input class="form__tel-input" size="small" placeholder="Заголовок"></el-input>
                    <el-input class="form__tel-input" size="small" placeholder="example@mail.com"></el-input>
                  </div>
                </el-form-item>
              </div>
            </div>
          </el-form>

          <el-form>
            <div class="contentInfo contentInfo__newDepartment">
              <div class="contentInfo-title"><i class="mdi mdi-domain"></i>Настройки сайтов</div>
              <div class="contentInfo__newDepartment-button">
                <el-button><i class="mdi mdi-plus"></i>Добавить сайт</el-button>
              </div>
            </div>
          </el-form>

          <el-form>
            <div class="contentInfo__newSite-form">
              <div class="newSite__form-select">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Выберите сайт</div>
                    <div class="contentInfo__input-input">
                      <el-select v-model="value" placeholder="Select">
                        <el-option>
                        </el-option>
                      </el-select>
                    </div>
                  </div>
                </el-form-item>
              </div>
              <div class="newSite__form-info">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Контактный телефон</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" placeholder="+7 ( ___ ) ___ __ __"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">E-mail</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" placeholder="example@mail.com"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__check">
                    <div class="contentInfo__input-title">Персональные поля</div>
                    <div class="contentInfo__input-check">
                      <el-checkbox-group v-model="checkList">
                        <el-checkbox label="Option A"></el-checkbox>
                        <el-checkbox label="Option B"></el-checkbox>
                        <el-checkbox label="Option C"></el-checkbox>
                      </el-checkbox-group>
                    </div>
                  </div>
                </el-form-item>
              </div>
              <div class="newSite__form-textarea">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Дополнительная информация</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" type="textarea" placeholder="Введите текст"></el-input>
                    </div>
                  </div>
                </el-form-item>
              </div>
              <div class="newSite__form-buttons">
                <el-button class="form__buttons-new" type="primary">Добавить</el-button>
                <el-button class="form__buttons-cancel">Отмена</el-button>
              </div>

            </div>
          </el-form>

          <el-form>
            <div class="contentInfo__site-form">
              <div class="site__titles">
                <div class="site__titles-title">Auto.ru</div>
                <div class="site__titles-button">
                  <el-button><i class="mdi mdi-pencil"></i></el-button>
                </div>
              </div>
              <div class="newSite__form-info">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Контактный телефон</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" placeholder="+7 ( ___ ) ___ __ __"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">E-mail</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" placeholder="example@mail.com"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__check">
                    <div class="contentInfo__input-title">Персональные поля</div>
                    <div class="contentInfo__input-check">
                      <el-checkbox-group v-model="checkList">
                        <el-checkbox label="Option A"></el-checkbox>
                        <el-checkbox label="Option B"></el-checkbox>
                        <el-checkbox label="Option C"></el-checkbox>
                      </el-checkbox-group>
                    </div>
                  </div>
                </el-form-item>
              </div>
              <div class="newSite__form-textarea">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Дополнительная информация</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" type="textarea" placeholder="Введите текст"></el-input>
                    </div>
                  </div>
                </el-form-item>
              </div>
            </div>
          </el-form>

          <el-form>
            <div class="contentInfo__site-form">
              <div class="site__titles">
                <div class="site__titles-title">Auto.ru</div>
                <div class="site__titles-button">
                  <el-button><i class="mdi mdi-pencil"></i></el-button>
                </div>
              </div>
              <div class="newSite__form-info">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Контактный телефон</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" placeholder="+7 ( ___ ) ___ __ __"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">E-mail</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" placeholder="example@mail.com"></el-input>
                    </div>
                  </div>
                </el-form-item>
                <el-form-item>
                  <div class="contentInfo__check">
                    <div class="contentInfo__input-title">Персональные поля</div>
                    <div class="contentInfo__input-check">
                      <el-checkbox-group v-model="checkList">
                        <el-checkbox label="Option A"></el-checkbox>
                        <el-checkbox label="Option B"></el-checkbox>
                        <el-checkbox label="Option C"></el-checkbox>
                      </el-checkbox-group>
                    </div>
                  </div>
                </el-form-item>
              </div>
              <div class="newSite__form-textarea">
                <el-form-item>
                  <div class="contentInfo__input">
                    <div class="contentInfo__input-title">Дополнительная информация</div>
                    <div class="contentInfo__input-input">
                      <el-input size="small" type="textarea" placeholder="Введите текст"></el-input>
                    </div>
                  </div>
                </el-form-item>
              </div>
            </div>
          </el-form>


        </div>
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
        startTime: '',
        endTime: '',
        menuClass: 'admin__left',
        adminLeftOpen: false,
        isCollapse: true,
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

<style lang="scss">
  /*---scoped----*/
  .contentInfo__input-title, .contentInfo__check-title, .contentInfo__time-title, .form__tel-title{
    line-height: 1.5;
    font-size: 13px;
    color: #606266;
  }
  .el-checkbox-group{
    height: 32px;
    display: flex;
    align-items: center;
  }
</style>
