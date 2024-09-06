<script setup>
import Menu from "./Menu.vue";
import Content from "./Content.vue";

</script>

<template>
  <header class="container-header">
    <div class="header">
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
        <button class="choose__items_button">Товар</button>
        <button class="choose__items_button">Продавцы</button>
        <button class="choose__items_button">Информация</button>
        <button class="choose__items_button">Эксперты</button>
      </div>
    </div>
  </header>
  <main class="main">
    <div class="menu">
      <Menu />
    </div>
    <div class="content">
      <Content />
    </div>
  </main>
</template>

<style scoped lang="scss">
.container-header {
  width: 100%;
  margin-top: 30px;
}

.header {
  background: #f5f5f5;
  border-radius: 8px;
  margin: 0 auto;
  display: flex;
  gap: 30px;
  align-items: center;
  height: 60px;
  justify-content: flex-end;
  padding: 0 25px;

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
    font-weight: 400;
    line-height: 16px;
    margin: 0;
    color: #000;
    background-color: #fff;
    border: 1px solid #dedede;
    border-radius: 4px;
    height: 26px;
    width: 56px;
  }
}

.choose {
  margin: 65px 70px 0;
  display: grid;
  grid-template-columns: 1fr 4fr;
  align-items: center;

  border-bottom: 1px solid #dedede;
  padding: 5px;

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
      border: 1px solid #dedede;
      border-radius: 6px;
    }
  }
}

.main {
  display: grid;
  gap: 40px;
  margin: 24px 70px 0;
  grid-template-columns: 1fr 4fr;
  max-width: 100%;
  height: 100%;
}

.menu {
  // background: #aaa;
  border: 1px solid #dedede;
  border-radius: 8px;
  padding: 5px;
}

.content {
  max-width: 100%;
}
</style>
