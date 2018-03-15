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
        <div class="right__header-title">Новый сотрудник</div>
      </div>
      <div class="adminContent">
        <div class="adminContent-back">
          <nuxt-link to="/"><i class="mdi mdi-arrow-left"></i>Назад</nuxt-link>
        </div>
        <el-form>
          <div class="adminContent-info">
            <div class="contentInfo contentInfo-row">
              <div class="contentInfo__credit">
                <div class="contentInfo-title"><i class="mdi mdi-currency-rub"></i>Данные сотрудника</div>
                <div class="contentInfo__inputs">
                  <el-form-item>
                    <div class="contentInfo__input contentInfo__input-mail">
                      <div class="contentInfo__input-title">Фамилия</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="Введите фамилию сотрудника" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <div class="contentInfo__input">
                      <div class="contentInfo__input-title">Имя</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="Введите имя сотрудника" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <div class="contentInfo__input">
                      <div class="contentInfo__input-title">Отчество</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="Введите отчество сотрудника" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                </div>
              </div>
              <div class="contentInfo__credit">
                <div class="contentInfo-title"><i class="mdi mdi-currency-rub"></i>Контакты</div>
                <div class="contentInfo__inputs">
                  <el-form-item>
                    <div class="contentInfo__input contentInfo__input-mail">
                      <div class="contentInfo__input-title">Контактный телефон</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="+7 ( ___ ) ___ __ __" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <div class="contentInfo__input">
                      <div class="contentInfo__input-title">E-mail</div>
                      <div class="contentInfo__input-input">
                        <el-input placeholder="Введите e-mail" size="small"></el-input>
                      </div>
                    </div>
                  </el-form-item>
                  <el-form-item>
                    <div class="contentInfo__input">
                      <div class="contentInfo__input-title">Салон</div>
                      <div class="contentInfo__input-input">
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
                    </div>
                  </el-form-item>
                </div>
              </div>
            </div>
            <div class="contentInfo contentInfo-salon">
              <div class="contentInfo-title"><i class="mdi mdi-domain"></i>Данные для входа в систему</div>
              <div class="collapse__model-select">
                <el-form-item>
                  <div class="model__select-title">Пароль</div>
                  <el-input size="small" placeholder="Введите пароль для доступа к системе"></el-input>
                </el-form-item>
                <div class="model__select-text">Для доступа к системе сотруднику необходимо ввести указанные e-mail и
                  пароль
                </div>
                <el-form-item>
                  <el-button type="primary" style="margin-bottom: 10px" @click="dialogVisible = true">Отправить данные
                    для входа на указанный e-mail
                  </el-button>
                </el-form-item>
              </div>
            </div>
            <div class="contentInfo contentInfo-salon">
              <div class="contentInfo-title"><i class="mdi mdi-domain"></i>права доступа</div>

              <div class="contentInfo__rights">
                <div class="contentInfo__rights-title">Публикация</div>
                <div class="contentInfo__rights-group">
                  <el-checkbox-group>
                    <el-checkbox label="Option A"></el-checkbox>
                    <el-checkbox label="Option B"></el-checkbox>
                    <el-checkbox label="Option C"></el-checkbox>
                    <el-checkbox label="Option C"></el-checkbox>
                  </el-checkbox-group>
                </div>
              </div>
              <div class="contentInfo__rights">
                <div class="contentInfo__rights-title">Публикация</div>
                <div class="contentInfo__rights-group">
                  <el-checkbox-group>
                    <el-checkbox label="Option A"></el-checkbox>
                    <el-checkbox label="Option B"></el-checkbox>
                    <el-checkbox label="Option C"></el-checkbox>
                    <el-checkbox label="Option C"></el-checkbox>
                  </el-checkbox-group>
                </div>
              </div>
              <div class="contentInfo__rights">
                <div class="contentInfo__rights-title">Публикация</div>
                <div class="contentInfo__rights-group">
                  <el-checkbox-group>
                    <el-checkbox label="Option A"></el-checkbox>
                    <el-checkbox label="Option B"></el-checkbox>
                    <el-checkbox label="Option C"></el-checkbox>
                    <el-checkbox label="Option C"></el-checkbox>
                  </el-checkbox-group>
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
    <el-dialog
      title="Отправка данных учетной записи"
      :visible.sync="dialogVisible"
      width="70%">
      <div class="dialogSendInfo-control">
        Проверьте данные для отправки на адрес <span>example@companyname.com</span></div>
      <div class="dialogSendInfo-wrapper">
        <div class="dialogSendInfo__data">
          <div class="dialogSendInfo__data-title">Имя сотрудника:</div>
          <div class="dialogSendInfo__data-value">Александров Александр Александрович</div>
        </div>
        <div class="dialogSendInfo__data">
          <div class="dialogSendInfo__data-title">E-mail для входа в систему:</div>
          <div class="dialogSendInfo__data-value">example@companyname.com</div>
        </div>
        <div class="dialogSendInfo__data">
          <div class="dialogSendInfo__data-title">Пароль для входа в систему:</div>
          <div class="dialogSendInfo__data-value">254_Df4_7</div>
        </div>
      </div>
      <div scope-slot="footer">
        <div class="newConfPop__buttons">
          <el-button type="primary">Отправить</el-button>
          <el-button type="button">Отмена</el-button>
        </div>
      </div>
    </el-dialog>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        dialogVisible: false
      };
    },
  }
</script>

<style scoped lang="scss">

</style>
