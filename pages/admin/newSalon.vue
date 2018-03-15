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
        <div class="right__header-title">Добавить автосалон</div>
      </div>
      <div class="adminContent">
        <div class="adminContent-back">
          <nuxt-link to="/"><i class="mdi mdi-arrow-left"></i>Назад</nuxt-link>
        </div>
        <el-form>
          <div class="adminContent-info">
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
                    <div class="contentInfo__input-title">Название отдела</div>
                    <div class="contentInfo__input-input">
                      <el-input placeholder="Введите название отдела" size="small"></el-input>
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
                    <div class="contentInfo__input-title">Адрес салона</div>
                    <div class="contentInfo__input-input">
                      <el-input placeholder="Введите адрес" size="small"></el-input>
                    </div>
                  </div>
                </el-form-item>
              </div>
            </div>

            <div class="contentInfo contentInfo-row">
              <div class="contentInfo__contacts">
                <div class="contentInfo-title"><i class="mdi mdi-phone"></i>Контакты</div>
                <div class="contacts__inputs">
                  <div class="contacts__input contacts__input-time">
                    <div class="contacts__input-title">Время работы</div>
                    <div class="contacts__input-row">
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-time-select
                            placeholder="Начало рабочего дня"
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
                        <div class="contacts__input-input">
                          <el-time-select
                            placeholder="Конец рабочего дня"
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
                    </div>
                  </div>
                  <div class="contacts__input contacts__input-phones">
                    <div class="contacts__input-title">Контактые телефоны</div>
                    <!--Одна пара инпутов-->
                    <div class="contacts__input-row">
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input disabled placeholder="Основной" size="small"></el-input>
                        </div>
                      </el-form-item>
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                        </div>
                      </el-form-item>
                    </div>
                    <div class="contacts__input-row">
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input disabled placeholder="Основной" size="small"></el-input>
                        </div>
                      </el-form-item>
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                        </div>
                      </el-form-item>
                    </div>
                    <div class="contacts__input-row">
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input disabled placeholder="Основной" size="small"></el-input>
                        </div>
                      </el-form-item>
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                        </div>
                      </el-form-item>
                    </div>
                    <div class="contacts__input-row">
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input disabled placeholder="Основной" size="small"></el-input>
                        </div>
                      </el-form-item>
                      <el-form-item>
                        <div class="contacts__input-input">
                          <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                        </div>
                      </el-form-item>
                    </div>

                    <!--<div class="contacts__input-button">-->
                      <!--<el-button><i class="mdi mdi-plus"></i>Добавить телефон</el-button>-->
                    <!--</div>-->
                  </div>
                </div>
              </div>
              <div class="contentInfo__credit">
                <div class="contentInfo-title"><i class="mdi mdi-currency-rub"></i>Кредитный отдел</div>
                <div class="contentInfo__inputs">
                  <el-form-item>
                    <div class="contentInfo__input contentInfo__input-mail">
                      <div class="contentInfo__input-title">Адрес электронной почты</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="Введите название отдела" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <div class="contentInfo__input">
                      <div class="contentInfo__input-title">Номер телефона</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <div class="contentInfo__input">
                      <div class="contentInfo__input-title">Технический номер</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                </div>
              </div>
            </div>
            <div class="contentInfo contentInfo-row">
              <div class="contentInfo__contacts">
                <div class="contentInfo-title"><i class="mdi mdi-phone"></i>Дополнительная информация</div>
                <div class="dop__inputs">
                  <el-form-item>
                    <el-input type="textarea"></el-input>
                  </el-form-item>
                </div>
              </div>
              <div class="contentInfo__credit">
                <div class="contentInfo-title"><i class="mdi mdi-currency-rub"></i>Дополнительная информация (auto.ru)</div>
                <div class="dop__inputs">
                  <el-form-item>
                    <el-input type="textarea"></el-input>
                  </el-form-item>
                </div>
              </div>
            </div>
          </div>
        </el-form>
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
  export default {}
</script>

<style lang="scss">


</style>
