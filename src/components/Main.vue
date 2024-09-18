<script setup>
import Menu from "./Menu.vue";
import Content from "./Content.vue";
import { ref } from "vue";

const view = ref(["product", "information"]);

const changeProductView = () => {
  if (view.value.indexOf("product") !== -1) {
    view.value = view.value.filter((item) => item !== "product");
  } else {
    view.value.push("product");
  }
};

const changeSallersView = () => {
  if (view.value.indexOf("sallers") !== -1) {
    view.value = view.value.filter((item) => item !== "sallers");
  } else {
    view.value.push("sallers");
  }
};

const changeInformationView = () => {
  if (view.value.indexOf("information") !== -1) {
    view.value = view.value.filter((item) => item !== "information");
  } else {
    view.value.push("information");
  }
};

const changeExpertsView = () => {
  if (view.value.indexOf("experts") !== -1) {
    view.value = view.value.filter((item) => item !== "experts");
  } else {
    view.value.push("experts");
  }
};
</script>

<template>
  <header class="container-header">
    <div class="header">
      <div class="header__logo">
        <svg
          width="112"
          height="46"
          viewBox="0 0 112 46"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M18.3 -2.38419e-06V33.65C18.3 34.1833 18.2 34.55 18 34.75C17.8333 34.9167 17.4833 35 16.95 35H14.3V1.35C14.3 0.816666 14.3833 0.466666 14.55 0.3C14.75 0.0999983 15.1167 -2.38419e-06 15.65 -2.38419e-06H18.3ZM4.6 18.3V33.65C4.6 34.1833 4.5 34.55 4.3 34.75C4.13333 34.9167 3.78333 35 3.25 35H0.6V1.35C0.6 0.816666 0.683334 0.466666 0.85 0.3C1.05 0.0999983 1.41667 -2.38419e-06 1.95 -2.38419e-06H4.6V15.4H12.3V16.95C12.3 17.4833 12.2167 17.85 12.05 18.05C11.9167 18.2167 11.5833 18.3 11.05 18.3H4.6ZM38.6023 32.1V33.65C38.6023 34.1833 38.519 34.55 38.3523 34.75C38.219 34.9167 37.8857 35 37.3523 35H29.8023C28.069 35 26.8357 34.65 26.1023 33.95C25.4023 33.2167 25.0523 31.9833 25.0523 30.25V14.35C25.0523 12.6167 25.4023 11.4 26.1023 10.7C26.8357 9.96667 28.069 9.6 29.8023 9.6H35.3023C37.0357 9.6 38.2523 9.96667 38.9523 10.7C39.6857 11.4 40.0523 12.6167 40.0523 14.35V19.95C40.0523 21.6833 39.6857 22.9167 38.9523 23.65C38.2523 24.35 37.0357 24.7 35.3023 24.7H32.3023C31.769 24.7 31.419 24.6167 31.2523 24.45C31.119 24.25 31.0523 23.8833 31.0523 23.35V21.8H33.9523C34.9857 21.8 35.6357 21.5833 35.9023 21.15C36.169 20.7167 36.3023 19.9833 36.3023 18.95V15.1C36.3023 14.0667 36.1357 13.3833 35.8023 13.05C35.469 12.6833 34.7857 12.5 33.7523 12.5H31.6023C30.5023 12.5 29.8023 12.7 29.5023 13.1C29.2023 13.4667 29.0523 14.2167 29.0523 15.35V29.25C29.0523 30.2833 29.1857 31.0167 29.4523 31.45C29.719 31.8833 30.369 32.1 31.4023 32.1H38.6023ZM50.1066 -2.38419e-06V33.65C50.1066 34.1833 50.0066 34.55 49.8066 34.75C49.64 34.9167 49.29 35 48.7566 35H46.1066V1.35C46.1066 0.816666 46.19 0.466666 46.3566 0.3C46.5566 0.0999983 46.9233 -2.38419e-06 47.4566 -2.38419e-06H50.1066ZM68.5918 9.6C70.3251 9.6 71.5418 9.96667 72.2418 10.7C72.9751 11.4 73.3418 12.6167 73.3418 14.35V30.25C73.3418 31.9833 72.9751 33.2167 72.2418 33.95C71.5418 34.65 70.3251 35 68.5918 35H63.8418C62.8751 35 62.1751 34.7667 61.7418 34.3C61.3418 33.8 61.0418 33.0667 60.8418 32.1V43.7C60.8418 44.2333 60.7418 44.5833 60.5418 44.75C60.3751 44.95 60.0251 45.05 59.4918 45.05H56.8418V10.95C56.8418 10.4167 56.9251 10.0667 57.0918 9.9C57.2918 9.7 57.6585 9.6 58.1918 9.6H60.8418V32.1H66.9918C68.0251 32.1 68.6751 31.8833 68.9418 31.45C69.2085 31.0167 69.3418 30.2833 69.3418 29.25V15.35C69.3418 14.3167 69.2085 13.5833 68.9418 13.15C68.6751 12.7167 68.0251 12.5 66.9918 12.5H62.8418V10.95C62.8418 10.4167 62.9085 10.0667 63.0418 9.9C63.2085 9.7 63.5585 9.6 64.0918 9.6H68.5918ZM93.1922 32.1V33.65C93.1922 34.1833 93.1089 34.55 92.9422 34.75C92.8089 34.9167 92.4755 35 91.9422 35H84.3922C82.6589 35 81.4255 34.65 80.6922 33.95C79.9922 33.2167 79.6422 31.9833 79.6422 30.25V14.35C79.6422 12.6167 79.9922 11.4 80.6922 10.7C81.4255 9.96667 82.6589 9.6 84.3922 9.6H89.8922C91.6255 9.6 92.8422 9.96667 93.5422 10.7C94.2755 11.4 94.6422 12.6167 94.6422 14.35V19.95C94.6422 21.6833 94.2755 22.9167 93.5422 23.65C92.8422 24.35 91.6255 24.7 89.8922 24.7H86.8922C86.3589 24.7 86.0089 24.6167 85.8422 24.45C85.7089 24.25 85.6422 23.8833 85.6422 23.35V21.8H88.5422C89.5755 21.8 90.2255 21.5833 90.4922 21.15C90.7589 20.7167 90.8922 19.9833 90.8922 18.95V15.1C90.8922 14.0667 90.7255 13.3833 90.3922 13.05C90.0589 12.6833 89.3755 12.5 88.3422 12.5H86.1922C85.0922 12.5 84.3922 12.7 84.0922 13.1C83.7922 13.4667 83.6422 14.2167 83.6422 15.35V29.25C83.6422 30.2833 83.7755 31.0167 84.0422 31.45C84.3089 31.8833 84.9589 32.1 85.9922 32.1H93.1922ZM104.396 12.5V33.65C104.396 34.1833 104.296 34.55 104.096 34.75C103.93 34.9167 103.58 35 103.046 35H100.396V10.95C100.396 10.4167 100.48 10.0667 100.646 9.9C100.846 9.7 101.213 9.6 101.746 9.6H104.396V12.5C104.83 11.3667 105.28 10.6 105.746 10.2C106.213 9.8 106.93 9.6 107.896 9.6H109.846C110.38 9.6 110.713 9.7 110.846 9.9C111.013 10.0667 111.096 10.4167 111.096 10.95V12.5H104.396Z"
            fill="black"
          />
        </svg>
      </div>
      <div class="header__info">
        <p class="header__info_about">О нас</p>
        <p class="header__info_invest">Invest planner</p>
        <p class="header__info_forum">Форум</p>
      </div>
      <div class="header__donate">
        <svg
          width="20"
          height="20"
          viewBox="0 0 20 20"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M10 2C14.4183 2 18 5.58167 18 10C18 14.4183 14.4183 18 10 18C5.58167 18 2 14.4183 2 10C2 5.58167 5.58167 2 10 2ZM10 3.33333C6.318 3.33333 3.33333 6.318 3.33333 10C3.33333 13.682 6.318 16.6667 10 16.6667C13.682 16.6667 16.6667 13.682 16.6667 10C16.6667 6.318 13.682 3.33333 10 3.33333ZM10.51 6.28567C11.9677 6.28567 12.9167 7.293 12.9167 8.65567C12.9167 10.0123 11.9467 11.009 10.4727 11.009H9.073V12.0377H11.199V12.6367H9.073V13.7923H7.90167V12.6367H6.85667V12.0377H7.90133V11.0093H6.85667V10.405H7.90133V6.28567H10.51ZM10.1867 7.277H9.07333V10.055H10.181C11.2097 10.055 11.7237 9.51433 11.7237 8.66067C11.7237 7.81267 11.2097 7.27733 10.1863 7.27733"
            fill="black"
          />
        </svg>
        <p class="header__donate_text">Поддержать проект</p>
      </div>

      <div class="header__location">
        <svg
          width="14"
          height="16"
          viewBox="0 0 14 16"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M6.99996 15.7083C6.87744 15.7095 6.75773 15.6716 6.65829 15.6C6.40829 15.4417 0.541626 11.5 0.541626 6.70833C0.541626 4.99548 1.22206 3.35277 2.43323 2.1416C3.6444 0.93043 5.2871 0.25 6.99996 0.25C8.71282 0.25 10.3555 0.93043 11.5667 2.1416C12.7779 3.35277 13.4583 4.99548 13.4583 6.70833C13.4583 11.5 7.62496 15.4417 7.34163 15.6C7.24219 15.6716 7.12248 15.7095 6.99996 15.7083ZM6.99996 1.54167C5.62448 1.53724 4.30346 2.07883 3.32694 3.04753C2.35043 4.01623 1.79824 5.33286 1.79163 6.70833C1.79163 10.2167 5.78329 13.425 6.99996 14.3167C8.21663 13.425 12.2083 10.2167 12.2083 6.70833C12.2017 5.33286 11.6495 4.01623 10.673 3.04753C9.69646 2.07883 8.37544 1.53724 6.99996 1.54167Z"
            fill="black"
          />
          <path
            d="M6.99992 8.62533C6.54667 8.62533 6.1036 8.49092 5.72674 8.23911C5.34988 7.9873 5.05615 7.62939 4.8827 7.21064C4.70925 6.7919 4.66386 6.33112 4.75229 5.88658C4.84071 5.44204 5.05897 5.0337 5.37947 4.71321C5.69996 4.39271 6.1083 4.17445 6.55284 4.08603C6.99738 3.9976 7.45816 4.04299 7.8769 4.21644C8.29565 4.38989 8.65356 4.68362 8.90537 5.06048C9.15718 5.43734 9.29159 5.88041 9.29159 6.33366C9.29159 6.94145 9.05014 7.52434 8.62037 7.95411C8.1906 8.38388 7.60771 8.62533 6.99992 8.62533ZM6.99992 5.29199C6.7939 5.29199 6.5925 5.35309 6.4212 5.46755C6.2499 5.58201 6.11639 5.74469 6.03755 5.93503C5.9587 6.12537 5.93808 6.33482 5.97827 6.53688C6.01846 6.73894 6.11767 6.92455 6.26335 7.07023C6.40903 7.21591 6.59464 7.31512 6.7967 7.35531C6.99876 7.3955 7.20821 7.37488 7.39855 7.29603C7.58889 7.21719 7.75157 7.08368 7.86603 6.91238C7.98049 6.74108 8.04159 6.53968 8.04159 6.33366C8.04159 6.05739 7.93184 5.79244 7.73649 5.59709C7.54114 5.40174 7.27619 5.29199 6.99992 5.29199Z"
            fill="black"
          />
        </svg>
        <p class="header__location-text">Воронеж</p>
      </div>
      <button href="#" class="header__enter">Вход</button>
    </div>

    <div class="choose">
      <p class="choose__title">Видимость</p>
      <div class="choose__items">
        <button
          @click="changeProductView"
          class="choose__items_button"
          :class="{
            choose__items_button_noactive: view.indexOf('product') === -1,
          }"
        >
          Товар
        </button>
        <button
          @click="changeSallersView"
          class="choose__items_button"
          :class="{
            choose__items_button_noactive: view.indexOf('sallers') === -1,
          }"
        >
          Продавцы
        </button>
        <button
          @click="changeInformationView"
          class="choose__items_button"
          :class="{
            choose__items_button_noactive: view.indexOf('information') === -1,
          }"
        >
          Информация
        </button>
        <button
          @click="changeExpertsView"
          class="choose__items_button"
          :class="{
            choose__items_button_noactive: view.indexOf('experts') === -1,
          }"
        >
          Эксперты
        </button>
      </div>
    </div>
  </header>
  <main class="main">
    <div class="menu">
      <Menu />
    </div>
    <div class="content">
      <Content :view="view" />
    </div>
  </main>
</template>

<style scoped lang="scss">
.container-header {
  width: 100%;
}

.header {
  width: 100%;
  background: #FFBF4B4D;
  border-radius: 8px;
  margin: 0;
  display: flex;
  gap: 30px;
  align-items: center;
  height: 60px;
  justify-content: flex-end;
  min-width: 1160px;
  padding-left: calc((100% - 1160px) / 2);
  padding-right: calc((100% - 1160px) / 2);

  &__info {
    display: flex;
    gap: 40px;
    align-items: center;
    font-family: "Roboto", sans-serif;
    font-size: 16px;
    font-weight: 400;
    line-height: 16px;
    color: #000;
    flex-grow: 1;
    justify-content: center;
  }

  &__donate {
    display: flex;
    gap: 10px;
    align-items: center;
    font-family: "Roboto", sans-serif;
    font-size: 16px;
    font-weight: 400;
    line-height: 16px;
    color: #000;
  }

  &__location {
    display: flex;
    gap: 10px;
    align-items: center;
  }

  &__location-text {
    font-family: "Roboto", sans-serif;
    font-size: 16px;
    font-weight: 400;
    line-height: 16px;
    color: #000;
  }

  &__enter {
    font-family: "Roboto", sans-serif;
    font-size: 16px;
    font-weight: 700;
    line-height: 16px;
    margin: 0;
    color: #fff;
    background-color: #FFBF4B;
    border: 1px solid #FFBF4B;
    border-radius: 4px;
    padding: 5px 10px 5px 10px;
    cursor: pointer;
  }
}

.choose {
  margin: 50px 0 24px;
  display: grid;
  grid-template-columns: 1fr 4fr;
  align-items: center;
  border-bottom: 1px solid #dedede;
  min-width: 1160px;
  padding-left: calc((100% - 1160px) / 2);
  padding-right: calc((100% - 1160px) / 2);

  &__title {
    margin: 0;
    font-family: "Roboto", sans-serif;
    font-size: 16px;
    font-weight: 400;
    line-height: 16px;
    color: #000;
  }

  &__items {
    display: flex;
    justify-content: space-between;
    border: 1px solid #dedede;
    border-radius: 8px;
    padding: 5px;
    gap: 5px;

    &_button {
      width: 100%;
      height: 26px;
      font-family: "Roboto", sans-serif;
      font-size: 16px;
      font-weight: 400;
      line-height: 16px;
      color: #000;
      border: 2px solid #FFBF4B;
      border-radius: 6px;
      background-color: #fff;
      cursor: pointer;
    }

    &_button_noactive {
      border: 1px solid #DEDEDE;
    }
  }
}

.main {
  display: grid;
  gap: 40px;
  margin: 24px 0;
  grid-template-columns: 1fr 4fr;
  // max-width: 100%;
  // height: 100%;
  padding-left: calc((100% - 1160px) / 2);
  padding-right: calc((100% - 1160px) / 2);
}

.menu {
  // background: #aaa;
  border: 1px solid #dedede;
  border-radius: 8px;
  padding: 5px;
  width: 160px;
}

.content {
  width: 960px;
}
</style>
