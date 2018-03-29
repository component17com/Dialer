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
          <div class="crmRight__title-text">Новое объявление</div>
          <el-button class="crmRight__title-clear"><i class="mdi mdi-refresh"></i> Очистить форму</el-button>
        </div>
        <el-form>
          <el-form-item class="item__check">
            <div class="crmRight__check">
              <el-checkbox-group>
                <el-checkbox>На сайте</el-checkbox>
                <el-checkbox>Auto.ru</el-checkbox>
                <el-checkbox>Avito.ru</el-checkbox>
                <el-checkbox>Drom.ru</el-checkbox>
                <el-checkbox>Нет в наличии</el-checkbox>
              </el-checkbox-group>
            </div>
          </el-form-item>
          <div class="crmRight__collapse">
            <el-collapse>
              <el-collapse-item name="1">
                <template slot="title">
                  <i class="mdi mdi-car"></i>Марка и модель
                </template>

                <div class="crmRight__collapse-model">
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Марка автомобиля</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Модель</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Тип кузова</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Поколение</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Год выпуска</div>
                      <el-input size="small" placeholder="Введите год"></el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Год выпуска (Auto.ru)</div>
                      <el-input size="small" placeholder="Введите год"></el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Год выпуска (Avito.ru)</div>
                      <el-input size="small" placeholder="Введите год"></el-input>
                    </el-form-item>
                  </div>
                </div>
              </el-collapse-item>
            </el-collapse>
          </div>
          <div class="crmRight__collapse">
            <el-collapse>
              <el-collapse-item name="2">
                <template slot="title">
                  <i class="mdi mdi-wrench"></i>Технические характеристики
                </template>

                <div class="crmRight__collapse-model">
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Двигатель</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Модификация</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Мощность</div>
                      <el-input size="small" placeholder="Введите значение">
                        <template slot="append">л.с</template>
                      </el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Объем</div>
                      <el-input size="small" placeholder="Введите значение">
                        <template slot="append">л</template>
                      </el-input>
                    </el-form-item>
                  </div>
                </div>
                <div class="crmRight__collapse-model">
                  <div class="collapse__model-radio">
                    <el-form-item>
                      <div class="model__select-title">Коробка передач</div>
                      <el-radio-group size="small">
                        <el-radio-button label="Механика"></el-radio-button>
                        <el-radio-button label="Автомат"></el-radio-button>
                        <el-radio-button label="Вариатор"></el-radio-button>
                        <el-radio-button label="Робот"></el-radio-button>
                      </el-radio-group>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-radio">
                    <el-form-item>
                      <div class="model__select-title">Привод</div>
                      <el-radio-group size="small">
                        <el-radio-button label="Передний"></el-radio-button>
                        <el-radio-button label="Задний"></el-radio-button>
                        <el-radio-button label="Полный"></el-radio-button>
                      </el-radio-group>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-radio">
                    <el-form-item>
                      <div class="model__select-title">Руль</div>
                      <el-radio-group size="small">
                        <el-radio-button label="Левый"></el-radio-button>
                        <el-radio-button label="Правый"></el-radio-button>
                      </el-radio-group>
                    </el-form-item>
                  </div>
                </div>
              </el-collapse-item>
            </el-collapse>

          </div>
          <div class="crmRight__collapse">
            <el-collapse>
              <el-collapse-item name="3">
                <template slot="title">
                  <i class="mdi mdi-palette"></i>Внешний вид
                </template>
                <div class="crmRight__collapse-model">
                  <div class="collapse__model-color">
                    <el-form-item>
                      <div class="model__select-title">Цвет</div>
                      <div class="model-colors">
                        <div class="model-color model-color-active"
                             style="background-color: #ffed0b; border-color:#ffed0b; ">
                        </div><!--Активный цвет кроме белого-->
                        <div class="model-color model-white-active"></div> <!--Активный цвет белого-->
                        <div class="model-color"></div>
                        <div class="model-color"></div>
                        <div class="model-color"></div>
                        <el-checkbox>Металлик</el-checkbox>
                      </div>
                    </el-form-item>
                  </div>
                </div>
                <div class="crmRight__collapse-image">
                  <div class="collapse__image-title">Фотографии автомобиля
                    <el-tooltip content="Top center" placement="top" open-delay="500">
                      <i class="mdi mdi-help-circle"></i>
                    </el-tooltip>
                  </div>
                  <div class="collapse__image-text">
                    Вы можете добавить еще <span>8</span> фотографий
                  </div>
                  <div class="collapse__image-upload">
                    <el-upload class="image-uploader">
                      <i class="el-icon-plus avatar-uploader-icon"></i>
                    </el-upload>
                  </div>
                  <div class="collapse__image-title">Видео</div>
                  <div class="collapse__image-text">
                    Вы можете добавить ссылку на видео для привлечения большего числа покупателей
                  </div>
                  <div class="collapse__image-video">
                    <el-input placeholder="Ссылка на видео" size="small"></el-input>
                  </div>
                </div>
              </el-collapse-item>
            </el-collapse>

          </div>
          <div class="crmRight__collapse collapse__sost">
            <el-collapse>
              <el-collapse-item name="4">
                <template slot="title">
                  <i class="mdi mdi-information"></i>Состояние
                </template>
                <div class="crmRight__collapse-state">
                  <div class="collapse__model-mili">
                    <el-form-item>
                      <div class="model__select-title">Пробег</div>
                      <el-input size="small" placeholder="Введите значение">
                        <template slot="append">км</template>
                      </el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-garanti">
                    <el-form-item>
                      <div class="model__select-title">Гарантия</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-tex">
                    <el-form-item>
                      <div class="model__select-title">Тех. осмотр</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-choky">
                    <el-form-item>
                      <el-checkbox>Не растаможен</el-checkbox>
                    </el-form-item>
                  </div>
                </div>
                <div class="crmRight__collapse-model">
                  <div class="collapse__model-radio">
                    <el-form-item>
                      <div class="model__select-title">ПТС</div>
                      <el-radio-group size="small">
                        <el-radio-button label="Оригинал"></el-radio-button>
                        <el-radio-button label="Дубликат"></el-radio-button>
                      </el-radio-group>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-radio">
                    <el-form-item>
                      <div class="model__select-title">Владельцев по ПТС</div>
                      <el-radio-group size="small">
                        <el-radio-button label="0"></el-radio-button>
                        <el-radio-button label="1"></el-radio-button>
                        <el-radio-button label="2"></el-radio-button>
                        <el-radio-button label="3+"></el-radio-button>
                      </el-radio-group>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-radio">
                    <el-form-item>
                      <div class="model__select-title">Состояние</div>
                      <el-radio-group size="small">
                        <el-radio-button label="Отличное"></el-radio-button>
                        <el-radio-button label="Хорошее"></el-radio-button>
                        <el-radio-button label="Среднее"></el-radio-button>
                        <el-radio-button label="Требует ремонта"></el-radio-button>
                      </el-radio-group>
                    </el-form-item>
                  </div>
                </div>
                <div class="model__text">Номера VIN и СТС не показываются в объявлении!
                  <el-tooltip content="Top center" placement="top" open-delay="500">
                    <i class="mdi mdi-help-circle"></i>
                  </el-tooltip>
                </div>
                <div class="crmRight__collapse-model">
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">VIN</div>
                      <el-input size="small" placeholder="VIN"></el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">VIN 2 (Avito.ru)</div>
                      <el-input size="small" placeholder="VIN"></el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">VIN 3 (Auto.ru)</div>
                      <el-input size="small" placeholder="VIN"></el-input>
                    </el-form-item>
                  </div>
                </div>
                <div class="crmRight__collapse-model crmRight__collapse-model-border">
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">СТС</div>
                      <el-input size="small" placeholder="СТС"></el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">СТС 2 (Avito.ru)</div>
                      <el-input size="small" placeholder="СТС"></el-input>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">СТС 3 (Auto.ru)</div>
                      <el-input size="small" placeholder="СТС"></el-input>
                    </el-form-item>
                  </div>
                </div>
              </el-collapse-item>
            </el-collapse>
          </div>
          <div class="crmRight__price">
            <div class="crmRight__price-title">Цена</div>
            <div class="collapse__price-obmen">
              <el-form-item>
                <el-checkbox>Возможен обмен</el-checkbox>
              </el-form-item>
            </div>
            <div class="collapse__price-select">
              <el-form-item>
                <div class="model__select-title">Первоначальная цена</div>
                <el-input size="small" placeholder="Введите сумму">
                  <template slot="append">руб.</template>
                </el-input>
              </el-form-item>
            </div>
            <div class="collapse__price-select">
              <el-form-item>
                <div class="model__select-title">Цена со скидкой</div>
                <el-input size="small" placeholder="Введите сумму">
                  <template slot="append">руб.</template>
                </el-input>
              </el-form-item>
            </div>
          </div>
          <div class="crmRight__options">
            <el-collapse>
              <el-collapse-item name="6">
                <template slot="title">
                  <i class="mdi mdi-file-document"></i>Опции и описание
                </template>
                <div class="optionLeft">
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Безопасность</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <div class="optionLeft-safety">
                      <el-form-item>
                        <el-checkbox-group>
                          <el-checkbox label="Антиблокировочная система (ABS)"></el-checkbox>
                          <el-checkbox label="Антипробуксовочная система"></el-checkbox>
                          <el-checkbox label="Центральный замок"></el-checkbox>
                          <el-checkbox label="Система курсовой устойчивости"></el-checkbox>
                          <el-checkbox label="Парктроник"></el-checkbox>
                        </el-checkbox-group>
                      </el-form-item>
                    </div>
                  </div>
                  <div class="optionLeft-alarm">
                    <div class="model__select-title">Сигнализация</div>
                    <el-form-item>
                      <el-checkbox-group>
                        <el-checkbox label="Штатная"></el-checkbox>
                        <el-checkbox label="Иммобилайзер"></el-checkbox>
                        <el-checkbox label="Обратная связь"></el-checkbox>
                        <el-checkbox label="Дистанционный запуск двигателя"></el-checkbox>
                      </el-checkbox-group>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Экстерьер</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <div class="optionLeft-exterier">
                      <el-form-item>
                        <el-checkbox-group>
                          <el-checkbox label="Люк на крыше"></el-checkbox>
                          <el-checkbox label="Тонированные стёкла"></el-checkbox>
                          <el-checkbox label="Ксеноновые фары"></el-checkbox>
                        </el-checkbox-group>
                      </el-form-item>
                    </div>
                  </div>
                </div>
                <div class="optionCenter">
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Регулировки</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <el-form-item>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <el-form-item>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <el-form-item>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <el-form-item>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <el-form-item>
                      <el-checkbox label="Электропривод зеркал"></el-checkbox>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Салон</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                  </div>
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Мультимедиа</div>
                      <el-checkbox-group>
                        <el-checkbox label="Бортовой компьютер"></el-checkbox>
                        <el-checkbox label="Навигационная система"></el-checkbox>
                        <el-checkbox label="CD"></el-checkbox>
                        <el-checkbox label="TV"></el-checkbox>
                        <el-checkbox label="Кассетник"></el-checkbox>
                      </el-checkbox-group>
                    </el-form-item>
                  </div>
                </div>
                <div class="optionRight">
                  <div class="collapse__model-select">
                    <el-form-item>
                      <div class="model__select-title">Оборудование</div>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <el-form-item>
                      <el-select size="small" filterable placeholder="Select">
                        <el-option
                          v-for="(item, index) in 10"
                          :key="index"
                          :label="index"
                          :value="index">
                        </el-option>
                      </el-select>
                    </el-form-item>
                    <el-form-item>
                      <el-checkbox-group>
                        <el-checkbox label="Датчик дождя"></el-checkbox>
                        <el-checkbox label="Датчик света"></el-checkbox>
                        <el-checkbox label="Круиз-контроль"></el-checkbox>
                        <el-checkbox label="Газобаллон. оборудование (ГБО)"></el-checkbox>
                        <el-checkbox label="Обогрев сидений"></el-checkbox>
                        <el-checkbox label="Обогрев зеркал"></el-checkbox>
                        <el-checkbox label="Омыватель фар"></el-checkbox>
                      </el-checkbox-group>
                    </el-form-item>
                  </div>
                </div>
              </el-collapse-item>
            </el-collapse>

          </div>
          <div class="crmRight__info">
            <div class="Right__info-title">Дополнительная информация</div>
            <div class="Right__info-alert">В этом поле запрещено указывать год выпуска автомобиля!</div>
            <div class="crmRight__info-input">
              <el-input type="textarea"></el-input>
            </div>
            <div class="crmRight__info-info">
              Расскажите об особенностях вашего автомобиля:
              <ul>
                <li>–регулярность технического обслуживания;</li>
                <li>–особенности состояния автомобиля и салона;</li>
                <li>–есть ли дополнительный комплект резины;</li>
                <li>–наличие тюнинга или дополнительных опций.</li>
              </ul>
            </div>
          </div>
          <div class="crmRight__dopi">
            <el-collapse>
              <el-collapse-item name="4">
                <template slot="title">
                  <i class="mdi mdi-thumb-up"></i>Дополнительные услуги
                </template>
                <div class="crmRight__dopi-title">Auto.ru</div>
                <div class="crmRight__dopi-bittons">
                  <el-button>Поднять в ТОП
                    <el-tooltip content="Top center" placement="top" open-delay="500">
                      <i class="mdi mdi-help-circle"></i>
                    </el-tooltip>
                  </el-button>
                  <el-button class="crmRight__dopi-bitton-prem">Premium
                    <el-tooltip content="Top center" placement="top" open-delay="500">
                      <i class="mdi mdi-help-circle"></i>
                    </el-tooltip>
                  </el-button>
                  <el-button>Premium Promo
                    <el-tooltip content="Top center" placement="top" open-delay="500">
                      <i class="mdi mdi-help-circle"></i>
                    </el-tooltip>
                  </el-button>
                </div>
              </el-collapse-item>
            </el-collapse>

          </div>
        </el-form>
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
        startTime: '',
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
  }
</script>

<style lang="scss">

</style>
