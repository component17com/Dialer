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
            <div class="collapse__price-obmen">
              <el-form-item>
                <el-checkbox>Возможен обмен</el-checkbox>
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

  export default {}
</script>

<style lang="scss">
  body {
    font-family: 'Open Sans', sans-serif;
  }

  .crm-container {
    display: flex;
    height: 100vh;
    overflow: hidden;
    /*-----Левая колонка----*/
    .crm__left {
      overflow-y: auto;
      display: flex;
      flex-direction: column;
      width: 240px;
      min-width: 240px;
      background-color: #303133;
    }
    .crm__left-title {
      font-size: 14px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.93;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      background-color: #409eff;
      padding: 13px;
      span {
        font-size: 16px;
        font-weight: 600;
        line-height: 1.69;
      }
    }
    .left__adverts {
      padding: 15px 15px 0 15px;
    }
    .left__adverts-all {
      font-size: 14px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      text-transform: uppercase;
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 20px;
    }
    .crm-tag {
      width: 45px;
      height: 22px;
      border-radius: 8px;
      background-color: #4a4a4a;
      display: flex;
      align-items: center;
      justify-content: center;
      .el-badge__content {
        background-color: transparent;
        border: none;
        font-size: 14px;
        font-weight: normal;
        font-style: normal;
        font-stretch: normal;
        letter-spacing: normal;
        color: #ffffff;
      }
    }
    .left__models {
      display: flex;
      flex-direction: column;
      flex-grow: 2;
      overflow-y: auto;
      padding: 0 15px 15px 15px;
      &::-webkit-scrollbar {
        width: 4px;
      }

      &::-webkit-scrollbar-thumb {
        background: #cccccc;
      }

      &::-webkit-scrollbar-track {
        background: #888888;
        cursor: pointer;
      }

    }
    .left__model {
      min-height: 50px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: solid 1px #f2f6fc;
      font-size: 14px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      text-decoration: none;
    }
    /*-----Правая колонка----*/
    .crm__right {
      flex-grow: 2;
      display: flex;
      flex-direction: column;
    }
    .crmRight__check {
      margin-bottom: 10px;
      .el-checkbox-group {
        display: flex;
      }
    }

    .right__header-top {
      display: flex;
      background-color: #161a24;
      padding: 5px 15px 5px 15px;
      align-items: center;
    }
    .rheader__top-message {
      font-size: 12px;
      font-weight: bold;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.5;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      text-transform: uppercase;
      span {
        color: #f56c6c;
      }
    }
    .rheader__top-name {
      margin-left: auto;
      font-size: 12px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      color: #ffffff;
    }
    .button-icon {
      margin-left: 15px;
      border: none;
      background-color: transparent;
      color: #ffffff;
      width: 20px;
      height: 20px;
      min-height: 10px;
      min-width: 10px;
      padding: 0;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .right__header-buttons {
      padding: 0 15px 0 0;
      display: flex;
      align-items: center;
      background-color: #303133;
    }
    .rheader__button {
      background-color: transparent;
      border: none;
      height: 50px;
      min-height: 20px;
      padding: 0;
      font-size: 14px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      padding-left: 15px;
      padding-right: 15px;
      margin-left: 0;
      span {
        display: flex;
        align-items: center;
      }
      .mdi {
        margin-right: 10px;
      }
      .crm-tag {
        margin-left: 5px;
      }
      &:active, &:focus, &:hover {
        background-color: #161a24;
      }
    }
    .rheader__buttons-search {
      width: 263px;
      border-radius: 4px;
      background-color: #ffffff;
      margin-left: auto;
    }
    .rheader__buttons-new {
      margin-left: 15px;
      border-radius: 3px;
      background-color: #409eff;
      border: none;
      font-size: 12px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.5;
      letter-spacing: normal;
      text-align: left;
      color: #ffffff;
      .mdi {
        margin-right: 10px;
      }
    }

    .crmRight {
      display: flex;
      flex-direction: column;
      flex-grow: 2;
      overflow-y: auto;
      padding: 15px;
      &::-webkit-scrollbar {
        width: 8px;
      }

      &::-webkit-scrollbar-thumb {
        background: #888888;
      }

      &::-webkit-scrollbar-track {
        background: #cccccc;
        cursor: pointer;
      }
    }
    .crmRight__collapse-model {
      display: flex;
      flex-wrap: wrap;
    }
    .collapse__model-select {
      margin-right: 30px;
      min-width: 150px;
      width: 270px;
      .el-select {
        width: 100%;
      }
    }
    .collapse__model-radio {
      margin-right: 30px;
    }
    .crmRight__options {
      .el-collapse-item__content {
        display: flex;
        align-items: flex-start;
        justify-content: space-between;
      }
      .optionLeft, .optionCenter, .optionRight {
        display: flex;
        flex-direction: column;
        flex-basis: calc(33.3333% - 15px);
        .collapse__model-select {
          max-width: 100%;
        }
        .el-checkbox-group {
          display: flex;
          flex-direction: column;
          .el-checkbox {
            flex-basis: 100%;
            margin-left: 0;
          }
        }
      }
      .model__select-title {
        font-size: 14px;
        font-weight: 600;
        color: #303133;
        display: flex;
        align-items: center;
      }
      .collapse__model-select{
        margin-bottom: 20px;
      }
      .el-collapse-item__content{
        padding-top: 10px;
      }
    }

    /*----Титл и кнопка очистить----*/
    .crmRight__title {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      font-size: 22px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.09;
      letter-spacing: normal;
      text-align: left;
      color: #161a24;
      min-height: 40px;
      button {
        border: none;
        background-color: transparent;
        min-width: 20px;
        min-height: 5px;
        padding: 0;
        font-size: 13px;
        font-weight: normal;
        font-style: normal;
        font-stretch: normal;
        letter-spacing: normal;
        color: #8c939d;
        .mdi {
          margin-right: 5px;
        }
      }
    }
    /*----checkbox-----*/
    .item__check {
      margin-bottom: 0;
    }
    /*----Заголовок Коллапса----*/
    .el-collapse-item__header {
      border-radius: 4px;
      background-color: #ebeef5;
      height: 40px;
      padding: 0 10px;
      display: flex;
      align-items: center;
      font-size: 14px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #303133;
      position: relative;
      .el-collapse-item__arrow {
        position: absolute;
        right: 15px;
        margin-right: 0;
      }
      .mdi {
        font-size: 16px;
        color: #303133;
        margin-right: 10px;
      }
    }
    .el-collapse-item {
      margin-bottom: 20px;
    }
    .el-collapse-item__content {
      padding-bottom: 0px;
    }
    .el-collapse-item__wrap {
      border: none;
    }
    /*-----TITL коллапса*/
    .model__select-title {
      font-size: 13px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #606266;
      height: 30px;
    }
    /*----Radio кнопки----- */
    .collapse__model-color {
      .el-form-item {
        margin-bottom: 0;
      }
    }
    .model-colors {
      display: flex;
      align-items: center;
      .model-color {
        width: 25px;
        height: 25px;
        border: solid 1px #c0c4cc;
        border-radius: 50%;
        margin-right: 10px;
        cursor: pointer;
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
      }
      .model-color-active {
        &:before {
          position: absolute;
          content: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAgY0hSTQAAeiYAAICEAAD6AAAAgOgAAHUwAADqYAAAOpgAABdwnLpRPAAAAAZiS0dEAAAAAAAA+UO7fwAAAAlwSFlzAAAASAAAAEgARslrPgAAAH9JREFUSMftkr0JgFAMhA9xG5dwCH8K3cNKtHQTR7RQ+GwsgogoLzbyrkzId8kRKSrqjYDsS3gBrMBk64kXXNIsKZW0fLU5wBDh4XCgB6qbfm3g41t4fgyuVyZBcAPpDsAGNKZeumV+Mmld4cZkNHGFxfLgEv9XPF3iu3nUv7QDdzzolivrh8EAAAAldEVYdGRhdGU6Y3JlYXRlADIwMTgtMDMtMTBUMTI6NDQ6MzArMDA6MDAtJLQDAAAAJXRFWHRkYXRlOm1vZGlmeQAyMDE4LTAzLTEwVDEyOjQ0OjMwKzAwOjAwXHkMvwAAACh0RVh0c3ZnOmJhc2UtdXJpAGZpbGU6Ly8vdG1wL21hZ2ljay1IMThvUTJCR1DbteAAAAAASUVORK5CYII=");
          top: -2px;
        }
      }
      .model-white-active {
        &:before {
          position: absolute;
          content: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAgY0hSTQAAeiYAAICEAAD6AAAAgOgAAHUwAADqYAAAOpgAABdwnLpRPAAAAAZiS0dEAAAAAAAA+UO7fwAAAAlwSFlzAAAASAAAAEgARslrPgAAAIJJREFUSMftkLsNgCAURY+fbVzCIfwUuoeVUTs3cQ4LZ7LARBtIaJQo0BhO+V4473IhEHhJ5lNeAAKY9WHsUL4AKbD7Sn4CQ5A7kfdA9bCvNfn4Vp7Lh+LmiJVc0UnBATTavLSp5elI61quGLW6rGsx/eRz8sSw34AIWIHJdfrAT7gA/vctXmUgC/kAAAAldEVYdGRhdGU6Y3JlYXRlADIwMTgtMDMtMTBUMTI6NDg6NTcrMDA6MDA00GOEAAAAJXRFWHRkYXRlOm1vZGlmeQAyMDE4LTAzLTEwVDEyOjQ4OjU3KzAwOjAwRY3bOAAAACh0RVh0c3ZnOmJhc2UtdXJpAGZpbGU6Ly8vdG1wL21hZ2ljay1CazM2aG52Mmq6VBMAAAAASUVORK5CYII=");
          top: -2px;
        }
      }
      .el-checkbox {
        margin-left: 20px;
      }
    }
    .collapse__image-title {
      font-size: 13px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #606266;
      margin-top: 10px;
      .mdi {
        font-size: 16px;
        color: #c0c4cc;
      }
    }
    .collapse__image-text {
      font-size: 13px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #c0c4cc;
    }
    /*----Uploader-----*/
    .collapse__image-upload {
      margin-top: 5px;
      .el-upload {
        width: 148px;
        height: 148px;
        border-radius: 4px;
        background-color: #fbfdff;
        border: dotted 1px #c0c4cc;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
        i {
          font-size: 28px;
          color: #8c939d;
        }
      }
    }
    .collapse__image-video {
      margin-top: 5px;
      input {
        max-width: 570px;
      }
    }
    /*----Состояние и цена-----*/
    .crmRight__collapse-state {
      display: flex;
      align-items: center;
    }
    .collapse__model-mili {
      margin-right: 30px;
      input {
        width: 140px;
      }
    }
    .collapse__model-garanti, .collapse__model-tex {
      margin-right: 20px;
      input {
        width: 140px;
        margin-right: 10px;
      }
      .el-input__suffix {
        right: 15px;
      }
    }
    .collapse__model-choky {
      margin-top: 18px;
      .el-form-item {
        margin-bottom: 0;
        height: 20px;
      }
    }
    .model__text {
      font-size: 14px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      letter-spacing: normal;
      text-align: left;
      color: #303133;
      min-height: 30px;
      margin-top: 10px;
      i {
        font-size: 16px;
        color: #c0c4cc;
      }
    }
    .collapse__sost {
      .el-collapse-item {
        margin-bottom: 0;
      }
      .el-collapse-item__wrap {
        padding-bottom: 15px;
        border-bottom: 1px solid #dddddd;
      }
    }

    /*----PRICE----*/
    .crmRight__price {
      margin-top: 20px;
      display: flex;
      flex-wrap: wrap;
      .collapse__price-select {
        margin-right: 30px;
        width: 370px;
        input {
          width: 100%;
        }
      }
      .el-form-item {
        margin-bottom: 0;
      }
    }
    .crmRight__price-title {
      font-size: 14px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.5;
      letter-spacing: normal;
      text-align: left;
      color: #303133;
      flex-basis: 100%;
    }
    .collapse__price-obmen {
      flex-basis: 100%;
      margin-bottom: 15px;
    }
    /*----INFO-----*/
    .crmRight__info {
      display: flex;
      flex-wrap: wrap;
      margin-bottom: 25px;
    }
    .Right__info-title {
      font-size: 14px;
      font-weight: 600;
      color: #303133;
      flex-basis: 100%;
    }
    .Right__info-alert {
      flex-basis: 100%;
      font-size: 13px;
      color: #f56c6c;
      margin-bottom: 10px;
      margin-top: 5px;
    }
    .crmRight__info-input {
      flex-basis: 50%;
      margin-right: 30px;
      textarea {
        resize: none;
        height: 145px;
      }
    }
    .crmRight__info-info {
      font-size: 13px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.54;
      letter-spacing: normal;
      text-align: left;
      color: #303133;
      ul {
        padding-left: 0;
      }
      li {
        list-style: none;
      }
    }
    /*---DOPI----*/
    .crmRight__dopi-title {
      margin-top: 10px;
      font-size: 14px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.5;
      letter-spacing: normal;
      text-align: left;
      color: #303133;
    }
    .crmRight__dopi-bittons {
      display: flex;
      margin-top: 10px;
      button {
        flex-grow: 2;
        height: 54px;
        text-align: left;
        font-size: 16px;
        font-weight: 600;
        font-style: normal;
        font-stretch: normal;
        line-height: 0.88;
        letter-spacing: normal;
        color: #303133;
        span {
          display: flex;
          justify-content: space-between;
          i {
            color: #c0c4cc;
          }
        }
      }

    }
    /*---Footer----*/
    .crmRight__footer {
      min-height: 61px;
      display: flex;
      border-top: 1px solid #dddddd;
      padding: 10px 15px;
      align-items: center;
      .footer__up {
        margin-left: auto;
        button {
          border: none;
          min-height: 20px;
          min-width: 20px;
          padding: 0;
          border-radius: 3px;
          background-color: #606266;
          width: 40px;
          height: 40px;
          color: white;
          i {
            font-size: 18px;
          }
        }
      }
      .footer__save {
        margin-right: 20px;
        button {
          border-radius: 4px;
          background-color: #409eff;
          font-size: 14px;
          font-weight: 600;
          color: #ffffff;
          border: none;
        }
      }
      .footer__cancel {
        button {
          font-size: 14px;
          font-weight: 600;
          color: #606266;
          border-radius: 4px;
        }
      }
    }
    /*----GLOBAL-----*/
    .el-form-item {
      margin-bottom: 5px;
    }
    .el-radio-button__inner {
      transition: 0.3s ease;
    }
    .el-radio-button__inner:hover {
      background-color: #ebeef5;
      font-size: 12px;
      color: #303133;
    }
    .el-collapse {
      border: none;
    }
    .crmRight__options {
      .collapse__model-select{
        flex-grow: 2;
        width: 100%;

      }
      .el-collapse-item__content {
        border-bottom: 1px solid #dddddd;
      }
    }
    input, select {
      font-size: 12px;
      font-family: 'Open Sans', sans-serif;
    }
    input::placeholder, select::placeholder {
      font-size: 12px;
      font-family: 'Open Sans', sans-serif;
    }
    .el-checkbox {
      display: flex;
      height: 30px;
      align-items: center;
    }
  }

  /*---POPOVER----*/
  .el-dropdown-menu {
    li {
      a {
        font-size: 14px;
        color: #5a5e66;
        padding: 0;
        border: none;
        margin-top: 10px;
        margin-bottom: 10px;
        margin-right: 70px;
        transition: 0.3s ease;
        font-family: 'Open Sans', sans-serif;
        text-decoration: none;
        .mdi {
          font-size: 16px;
          margin-right: 10px;
        }
        &:focus {
          background-color: transparent;
          color: #409eff;
        }
      }
    }

  }

  @media screen and (min-width: 992px) and (max-width: 1400px) {
    .crm-container {

      .right__header {
        .right__header-buttons {
          button {
            font-size: 30px;
            margin: 0;
            padding: 0 15px;
            display: flex;
            justify-content: center;
          }
          .rheader__button-text, .el-badge {
            display: none;
          }
          .rheader__buttons-new {
            font-size: 12px;
            height: 32px;
            margin-left: 15px;
          }
        }
      }
      .crmRight__collapse-state {
        flex-wrap: wrap;
      }
      .crmRight__options .el-collapse-item__content {
        flex-wrap: wrap;
      }
      .crmRight__options{
        .optionLeft, .optionCenter, .optionRight{
          flex-basis: calc(50% - 15px);
        }
      }

    }
  }
  @media screen and (min-width: 769px) and (max-width: 991px) {
    .crm-container {

      .right__header {
        .right__header-buttons {
          button {
            font-size: 30px;
            margin: 0;
            padding: 0 15px;
            display: flex;
            justify-content: center;
          }
          .rheader__button-text, .el-badge {
            display: none;
          }
          .rheader__buttons-new {
            font-size: 12px;
            height: 32px;
            margin-left: 15px;
          }
        }
        .rheader__top-message, .rheader__top-name{
          font-size: 10px;
        }
      }
      .crmRight__collapse-state {
        flex-wrap: wrap;
      }
      .crmRight__options .el-collapse-item__content {
        flex-wrap: wrap;
      }
      .crmRight__options{
        .optionLeft, .optionCenter, .optionRight{
          flex-basis: 100%;
        }
      }
      .el-checkbox+.el-checkbox {
        margin-left: 10px;
      }
      .crm__left {
        width: 220px;
        min-width: 220px;
      }
      .rheader__button .mdi {
        margin-right: 0px;
      }
      .crm-container .right__header .right__header-buttons button {
        font-size: 20px;
        margin: 0;
        padding: 0 15px;
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        justify-content: center;
      }
    }
  }
</style>
