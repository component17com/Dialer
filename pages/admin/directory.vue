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
        <div class="right__header-title">Справочник автомобилей</div>
      </div>
      <div class="adminContent">
        <div class="directory-row">
          <div class="directory directory__marka">
            <div class="directory__titles">
              <div class="directory__titles-title">Марка</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">AC</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">Acura</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__model">
            <div class="directory__titles">
              <div class="directory__titles-title">Модель</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">1 SERIES</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">4 SERIES GRAN COUPE</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__pokolenie">
            <div class="directory__titles">
              <div class="directory__titles-title">Поколение</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">E30 [1982 - 1987]</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">E90/E91/E92/E93 [рестайлинг] [2008 - 2013]</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__series">
            <div class="directory__titles">
              <div class="directory__titles-title">Серия</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">Compact хетчбэк</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">Touring универсал</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__modify">
            <div class="directory__titles">
              <div class="directory__titles-title">Модификация</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">316i AT (102 л.с.)</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
                <div v-for="item in 70" :key="item.id" class="directory__column-item">
                  <div class="column__item-title">316i MT (102 л.с.)</div>
                  <div class="column__item-button">
                    <el-button><i class="mdi mdi-delete"></i></el-button>
                  </div>
                </div>
            </div>
          </div>
          <div class="directory directory__complect">
            <div class="directory__titles">
              <div class="directory__titles-title">Комплектация</div>
              <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
              <div class="directory__titles-search">
                <el-input prefix-icon="el-icon-search" size="small"></el-input>
              </div>
            </div>
            <div class="directory__column">
                <div class="directory__column-item">
                  <div class="column__item-title">Нет данных</div>
                </div>
            </div>
          </div>
        </div>
        <!--Мобильная версия-->
        <div class="directory-rowMobile">
          <el-tabs v-model="activeName" @tab-click="handleClick">
            <el-tab-pane label="Марка" name="first">
              <div class="directory directory__marka">
                <div class="directory__titles">
                  <div class="directory__titles-title">Марка</div>
                  <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
                  <div class="directory__titles-search">
                    <el-input prefix-icon="el-icon-search" size="small"></el-input>
                  </div>
                </div>
                <div class="directory__column">
                  <div class="directory__column-item">
                    <div class="column__item-title">AC</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                  <div v-for="item in 70" :key="item.id" class="directory__column-item">
                    <div class="column__item-title">Acura</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                </div>
              </div>
            </el-tab-pane>
            <el-tab-pane label="Модель" name="second">
              <div class="directory directory__model">
                <div class="directory__titles">
                  <div class="directory__titles-title">Модель</div>
                  <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
                  <div class="directory__titles-search">
                    <el-input prefix-icon="el-icon-search" size="small"></el-input>
                  </div>
                </div>
                <div class="directory__column">
                  <div class="directory__column-item">
                    <div class="column__item-title">1 SERIES</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                  <div v-for="item in 70" :key="item.id" class="directory__column-item">
                    <div class="column__item-title">4 SERIES GRAN COUPE</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                </div>
              </div>
            </el-tab-pane>
            <el-tab-pane label="Поколение" name="third">
              <div class="directory directory__pokolenie">
                <div class="directory__titles">
                  <div class="directory__titles-title">Поколение</div>
                  <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
                  <div class="directory__titles-search">
                    <el-input prefix-icon="el-icon-search" size="small"></el-input>
                  </div>
                </div>
                <div class="directory__column">
                  <div class="directory__column-item">
                    <div class="column__item-title">E30 [1982 - 1987]</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                  <div v-for="item in 70" :key="item.id" class="directory__column-item">
                    <div class="column__item-title">E90/E91/E92/E93 [рестайлинг] [2008 - 2013]</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                </div>
              </div>
            </el-tab-pane>
            <el-tab-pane label="Серия" name="fourth">
              <div class="directory directory__series">
                <div class="directory__titles">
                  <div class="directory__titles-title">Серия</div>
                  <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
                  <div class="directory__titles-search">
                    <el-input prefix-icon="el-icon-search" size="small"></el-input>
                  </div>
                </div>
                <div class="directory__column">
                  <div class="directory__column-item">
                    <div class="column__item-title">Compact хетчбэк</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                  <div v-for="item in 70" :key="item.id" class="directory__column-item">
                    <div class="column__item-title">Touring универсал</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                </div>
              </div>
            </el-tab-pane>
            <el-tab-pane label="Модификация" name="fife">
              <div class="directory directory__modify">
                <div class="directory__titles">
                  <div class="directory__titles-title">Модификация</div>
                  <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
                  <div class="directory__titles-search">
                    <el-input prefix-icon="el-icon-search" size="small"></el-input>
                  </div>
                </div>
                <div class="directory__column">
                  <div class="directory__column-item">
                    <div class="column__item-title">316i AT (102 л.с.)</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                  <div v-for="item in 70" :key="item.id" class="directory__column-item">
                    <div class="column__item-title">316i MT (102 л.с.)</div>
                    <div class="column__item-button">
                      <el-button><i class="mdi mdi-delete"></i></el-button>
                    </div>
                  </div>
                </div>
              </div>
            </el-tab-pane>
            <el-tab-pane label="Комплектация" name="six">
              <div class="directory directory__complect">
                <div class="directory__titles">
                  <div class="directory__titles-title">Комплектация</div>
                  <el-button class="directory__titles-button"><i class="mdi mdi-plus"></i></el-button>
                  <div class="directory__titles-search">
                    <el-input prefix-icon="el-icon-search" size="small"></el-input>
                  </div>
                </div>
                <div class="directory__column">
                  <div class="directory__column-item">
                    <div class="column__item-title">Нет данных</div>
                  </div>
                </div>
              </div>
            </el-tab-pane>
          </el-tabs>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        menuClass: 'admin__left',
        adminLeftOpen: false,
        isCollapse: true,
      }
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
  /*-----Мобильная версия------*/

</style>
