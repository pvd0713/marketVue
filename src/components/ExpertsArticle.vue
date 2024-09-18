<script setup>
defineProps({
  article: Object,
});
</script>

<template>
  <div class="expert">
    <div class="header">
      <div class="header__avatar">
        <img class="header__avatar__img" :src="article.img" alt="img" />
      </div>
      <div class="header__nameOnline">
        <div class="header__name">{{ article.name }}</div>
        <p
          class="header__online"
          :class="{ header__online_off: !article.online }"
        >
          {{ article.online ? "On-line" : "" }}
        </p>
      </div>

      <div class="header__price">
        <div class="header__priceIcon">
          <p class="header__price__price">{{ article.price }} руб.</p>
          <svg
            width="24"
            height="25"
            viewBox="0 0 24 25"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M17.75 21.25C17.5974 21.247 17.4487 21.202 17.32 21.12L12 17.41L6.68 21.12C6.56249 21.1915 6.42757 21.2294 6.29 21.2294C6.15243 21.2294 6.01751 21.1915 5.9 21.12C5.78491 21.0607 5.68741 20.9722 5.61722 20.8634C5.54703 20.7546 5.50661 20.6293 5.5 20.5V6.5C5.5 5.77065 5.78973 5.07118 6.30546 4.55546C6.82118 4.03973 7.52065 3.75 8.25 3.75H15.75C16.4793 3.75 17.1788 4.03973 17.6945 4.55546C18.2103 5.07118 18.5 5.77065 18.5 6.5V20.5C18.5005 20.6362 18.4634 20.7698 18.3929 20.8863C18.3223 21.0027 18.2209 21.0974 18.1 21.16C17.9927 21.2189 17.8724 21.2498 17.75 21.25ZM12 15.75C12.1532 15.7484 12.3033 15.7938 12.43 15.88L17 19.06V6.5C17 6.16848 16.8683 5.85054 16.6339 5.61612C16.3995 5.3817 16.0815 5.25 15.75 5.25H8.25C7.91848 5.25 7.60054 5.3817 7.36612 5.61612C7.1317 5.85054 7 6.16848 7 6.5V19.06L11.57 15.88C11.6967 15.7938 11.8468 15.7484 12 15.75Z"
              fill="black"
            />
          </svg>
        </div>

        <p
          class="header__price__comunication"
          :class="{ header__price__comunication_off: !article.comunication }"
        >
          {{ article.comunication ? "Готов к коммуникации" : "" }}
        </p>
      </div>
    </div>
    <div class="content">
      <div class="content__item">
        <p class="content__item__name">Рейтинг (Эксперт)</p>
        <p class="content__item__meaning">
          {{ article.rang_main }} / {{ article.rang_secondary }}
        </p>
      </div>
      <div class="content__item">
        <p class="content__item__name">Количество публикаций</p>
        <p class="content__item__meaning">
          {{ article.count_public }} / {{ article.count_public_common }}
        </p>
      </div>
      <div class="content__item">
        <p class="content__item__name">Количество консультаций</p>
        <p class="content__item__meaning">
          {{ article.count_consult }} / {{ article.count_consult_common }}
        </p>
      </div>
      <div class="content__item">
        <p class="content__item__name content__item__name_last">
          Последняя консультация
        </p>
        <p class="content__item__meaning content__item__meaning_last">
          {{ article.last_consult }}
        </p>
      </div>
    </div>
    <div class="buttons">
      <button class="buttons__button">
        <p class="buttons__button__tooltip">Написать</p>
        <svg
          width="25"
          height="24"
          viewBox="0 0 25 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M19.5 4.25H5.5C5.03668 4.25263 4.59309 4.43784 4.26546 4.76546C3.93784 5.09309 3.75263 5.53668 3.75 6V18C3.75263 18.4633 3.93784 18.9069 4.26546 19.2345C4.59309 19.5622 5.03668 19.7474 5.5 19.75H19.5C19.9633 19.7474 20.4069 19.5622 20.7345 19.2345C21.0622 18.9069 21.2474 18.4633 21.25 18V6C21.2474 5.53668 21.0622 5.09309 20.7345 4.76546C20.4069 4.43784 19.9633 4.25263 19.5 4.25ZM5.5 5.75H19.5C19.5663 5.75 19.6299 5.77634 19.6768 5.82322C19.7237 5.87011 19.75 5.9337 19.75 6V7.54L12.5 11.16L5.25 7.54V6C5.25 5.9337 5.27634 5.87011 5.32322 5.82322C5.37011 5.77634 5.4337 5.75 5.5 5.75ZM19.5 18.25H5.5C5.4337 18.25 5.37011 18.2237 5.32322 18.1768C5.27634 18.1299 5.25 18.0663 5.25 18V9.21L12.16 12.67C12.2656 12.7228 12.382 12.7503 12.5 12.7503C12.618 12.7503 12.7344 12.7228 12.84 12.67L19.75 9.21V18C19.75 18.0663 19.7237 18.1299 19.6768 18.1768C19.6299 18.2237 19.5663 18.25 19.5 18.25Z"
            fill="black"
          />
        </svg>
      </button>
      <button class="buttons__button">
        <p class="buttons__button__tooltip">Позвонить</p>
        <svg
          width="25"
          height="24"
          viewBox="0 0 25 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M18.9001 20.7498H18.6701C16.0789 20.4678 13.5894 19.5844 11.4001 18.1698C9.36627 16.8744 7.63947 15.151 6.3401 13.1198C4.92225 10.9248 4.03862 8.42799 3.7601 5.82977C3.72825 5.51986 3.75969 5.20672 3.85252 4.90934C3.94534 4.61195 4.09761 4.33653 4.3001 4.09977C4.49703 3.85984 4.74012 3.66187 5.01495 3.51758C5.28978 3.37329 5.59077 3.28562 5.9001 3.25977H8.5001C9.06321 3.26033 9.60756 3.46223 10.0348 3.829C10.4621 4.19578 10.7442 4.70324 10.8301 5.25977C10.925 5.97464 11.1029 6.67603 11.3601 7.34977C11.5165 7.77315 11.5488 8.2324 11.4532 8.6735C11.3575 9.11461 11.1379 9.51923 10.8201 9.83977L10.2101 10.4498C11.1705 11.966 12.4588 13.2474 13.9801 14.1998L14.5901 13.5998C14.9106 13.282 15.3153 13.0624 15.7564 12.9667C16.1975 12.871 16.6567 12.9033 17.0801 13.0598C17.7546 13.3146 18.4557 13.4924 19.1701 13.5898C19.7361 13.6749 20.2516 13.9636 20.6199 14.4018C20.9881 14.84 21.1838 15.3975 21.1701 15.9698V18.3698C21.1701 18.9939 20.9228 19.5927 20.4824 20.035C20.042 20.4773 19.4443 20.7271 18.8201 20.7298L18.9001 20.7498ZM8.5001 4.74977H6.1101C5.99275 4.75752 5.87819 4.789 5.77334 4.84228C5.6685 4.89556 5.57554 4.96955 5.5001 5.05977C5.42667 5.14428 5.3711 5.24277 5.33673 5.34932C5.30235 5.45587 5.2899 5.56827 5.3001 5.67977C5.54258 8.03654 6.33371 10.3038 7.6101 12.2998C8.78674 14.1464 10.3534 15.7131 12.2001 16.8898C14.1973 18.1796 16.4671 18.9875 18.8301 19.2498C18.953 19.2567 19.076 19.238 19.1913 19.195C19.3066 19.152 19.4118 19.0855 19.5001 18.9998C19.6593 18.8365 19.7489 18.6178 19.7501 18.3898V15.9998C19.7546 15.7893 19.6818 15.5845 19.5454 15.4242C19.409 15.2638 19.2185 15.1591 19.0101 15.1298C18.1839 15.0187 17.3724 14.8175 16.5901 14.5298C16.436 14.4721 16.2687 14.4594 16.1076 14.493C15.9465 14.5267 15.7983 14.6053 15.6801 14.7198L14.6801 15.7198C14.563 15.834 14.4121 15.9073 14.25 15.9289C14.0878 15.9506 13.923 15.9193 13.7801 15.8398C11.6463 14.634 9.88006 12.8712 8.6701 10.7398C8.58728 10.5977 8.55411 10.4322 8.57584 10.2692C8.59757 10.1062 8.67296 9.95513 8.7901 9.83977L9.7901 8.83977C9.90478 8.72379 9.98367 8.57727 10.0174 8.41769C10.051 8.2581 10.0381 8.0922 9.9801 7.93977C9.69129 7.15775 9.49006 6.34613 9.3801 5.51977C9.35529 5.30503 9.25142 5.10722 9.08875 4.96488C8.92607 4.82254 8.71622 4.74585 8.5001 4.74977Z"
            fill="black"
          />
        </svg>
      </button>
      <button class="buttons__button">
        <p class="buttons__button__tooltip buttons__button__tooltip_last">
          Перейти на страницу
        </p>
        <svg
          width="25"
          height="24"
          viewBox="0 0 25 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M12.5 12.25C11.7583 12.25 11.0333 12.0301 10.4166 11.618C9.79993 11.206 9.31928 10.6203 9.03545 9.93506C8.75163 9.24984 8.67736 8.49584 8.82206 7.76841C8.96675 7.04098 9.3239 6.3728 9.84835 5.84835C10.3728 5.3239 11.041 4.96675 11.7684 4.82206C12.4958 4.67736 13.2498 4.75162 13.9351 5.03545C14.6203 5.31928 15.206 5.79993 15.618 6.41661C16.0301 7.0333 16.25 7.75832 16.25 8.5C16.25 9.49456 15.8549 10.4484 15.1517 11.1517C14.4484 11.8549 13.4946 12.25 12.5 12.25ZM12.5 6.25C12.055 6.25 11.62 6.38196 11.25 6.62919C10.88 6.87643 10.5916 7.22783 10.4213 7.63896C10.251 8.0501 10.2064 8.5025 10.2932 8.93895C10.3801 9.37541 10.5943 9.77632 10.909 10.091C11.2237 10.4057 11.6246 10.62 12.061 10.7068C12.4975 10.7936 12.9499 10.749 13.361 10.5787C13.7722 10.4084 14.1236 10.12 14.3708 9.75003C14.618 9.38002 14.75 8.94501 14.75 8.5C14.75 7.90326 14.5129 7.33097 14.091 6.90901C13.669 6.48705 13.0967 6.25 12.5 6.25Z"
            fill="black"
          />
          <path
            d="M19.5 19.25C19.3019 19.2474 19.1126 19.1676 18.9725 19.0275C18.8324 18.8874 18.7526 18.6981 18.75 18.5C18.75 16.55 17.69 15.25 12.5 15.25C7.31 15.25 6.25 16.55 6.25 18.5C6.25 18.6989 6.17098 18.8897 6.03033 19.0303C5.88968 19.171 5.69891 19.25 5.5 19.25C5.30109 19.25 5.11032 19.171 4.96967 19.0303C4.82902 18.8897 4.75 18.6989 4.75 18.5C4.75 13.75 10.18 13.75 12.5 13.75C14.82 13.75 20.25 13.75 20.25 18.5C20.2474 18.6981 20.1676 18.8874 20.0275 19.0275C19.8874 19.1676 19.6981 19.2474 19.5 19.25Z"
            fill="black"
          />
        </svg>
      </button>
      <svg
        width="25"
        height="25"
        viewBox="0 0 25 25"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M12.4285 2C18.1093 2 22.7143 6.605 22.7143 12.2857C22.7143 17.9664 18.1093 22.5714 12.4285 22.5714C6.74782 22.5714 2.14282 17.9664 2.14282 12.2857C2.14282 6.605 6.74782 2 12.4285 2ZM12.4285 3.71429C7.69454 3.71429 3.85711 7.55171 3.85711 12.2857C3.85711 17.0197 7.69454 20.8571 12.4285 20.8571C17.1625 20.8571 21 17.0197 21 12.2857C21 7.55171 17.1625 3.71429 12.4285 3.71429ZM13.0843 7.51014C14.9584 7.51014 16.1785 8.80529 16.1785 10.5573C16.1785 12.3016 14.9314 13.583 13.0363 13.583H11.2367V14.9056H13.9701V15.6757H11.2367V17.1616H9.73068V15.6757H8.38711V14.9056H9.73025V13.5834H8.38711V12.8064H9.73025V7.51014H13.0843ZM12.6685 8.78471H11.2371V12.3564H12.6613C13.9838 12.3564 14.6447 11.6613 14.6447 10.5637C14.6447 9.47343 13.9838 8.78514 12.6681 8.78514"
          fill="black"
        />
      </svg>
    </div>
    <button class="buttonMain">
      <p>Записаться</p>
      <svg
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M17 4.75H15.75V3.5C15.75 3.30109 15.671 3.11032 15.5303 2.96967C15.3897 2.82902 15.1989 2.75 15 2.75C14.8011 2.75 14.6103 2.82902 14.4697 2.96967C14.329 3.11032 14.25 3.30109 14.25 3.5V4.75H9.75V3.5C9.75 3.30109 9.67098 3.11032 9.53033 2.96967C9.38968 2.82902 9.19891 2.75 9 2.75C8.80109 2.75 8.61032 2.82902 8.46967 2.96967C8.32902 3.11032 8.25 3.30109 8.25 3.5V4.75H7C6.27065 4.75 5.57118 5.03973 5.05546 5.55546C4.53973 6.07118 4.25 6.77065 4.25 7.5V18.5C4.25 19.2293 4.53973 19.9288 5.05546 20.4445C5.57118 20.9603 6.27065 21.25 7 21.25H17C17.7293 21.25 18.4288 20.9603 18.9445 20.4445C19.4603 19.9288 19.75 19.2293 19.75 18.5V7.5C19.75 6.77065 19.4603 6.07118 18.9445 5.55546C18.4288 5.03973 17.7293 4.75 17 4.75ZM7 6.25H8.25V7.5C8.25 7.69891 8.32902 7.88968 8.46967 8.03033C8.61032 8.17098 8.80109 8.25 9 8.25C9.19891 8.25 9.38968 8.17098 9.53033 8.03033C9.67098 7.88968 9.75 7.69891 9.75 7.5V6.25H14.25V7.5C14.25 7.69891 14.329 7.88968 14.4697 8.03033C14.6103 8.17098 14.8011 8.25 15 8.25C15.1989 8.25 15.3897 8.17098 15.5303 8.03033C15.671 7.88968 15.75 7.69891 15.75 7.5V6.25H17C17.3315 6.25 17.6495 6.3817 17.8839 6.61612C18.1183 6.85054 18.25 7.16848 18.25 7.5V10.25H5.75V7.5C5.75 7.16848 5.8817 6.85054 6.11612 6.61612C6.35054 6.3817 6.66848 6.25 7 6.25ZM17 19.75H7C6.66848 19.75 6.35054 19.6183 6.11612 19.3839C5.8817 19.1495 5.75 18.8315 5.75 18.5V11.75H18.25V18.5C18.25 18.8315 18.1183 19.1495 17.8839 19.3839C17.6495 19.6183 17.3315 19.75 17 19.75Z"
          fill="white"
        />
        <path
          d="M14 15.2998H10C9.80109 15.2998 9.61032 15.3788 9.46967 15.5195C9.32902 15.6601 9.25 15.8509 9.25 16.0498C9.25 16.2487 9.32902 16.4395 9.46967 16.5801C9.61032 16.7208 9.80109 16.7998 10 16.7998H14C14.1989 16.7998 14.3897 16.7208 14.5303 16.5801C14.671 16.4395 14.75 16.2487 14.75 16.0498C14.75 15.8509 14.671 15.6601 14.5303 15.5195C14.3897 15.3788 14.1989 15.2998 14 15.2998Z"
          fill="white"
        />
      </svg>
    </button>
  </div>
</template>

<style scoped lang="scss">
.expert {
  width: 360px;
  height: 248px;
  background: #fff;
  border-radius: 8px;
  padding: 15px;
  border: 1px solid #dedede;
  display: flex;
  flex-direction: column;
  gap: 10px;
  background-color: #f5f5f5;
}
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 44px;
  gap: 4px;

  &__avatar {
    min-width: 38px;
    height: 38px;
    border-radius: 50%;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;

    &__img {
      width: 38px;
      height: 38px;
      object-fit: cover;
    }
  }

  &__nameOnline {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  &__name {
    font-family: "Roboto", sans-serif;
    font-size: 20px;
    font-weight: 700;
    line-height: 20px;
    color: #000;
    overflow: hidden;
    height: 22px;
    width: 135px;
    white-space: nowrap;
  }

  &__online {
    font-family: "Roboto", sans-serif;
    font-size: 14px;
    font-weight: 300;
    line-height: 14px;
    color: #999;
    height: 14px;

    &_off {
      visibility: hidden;
    }
  }

  &__price {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    // flex-grow: 1;

    &__price {
      font-family: "Roboto", sans-serif;
      font-size: 25px;
      font-weight: 700;
      line-height: 25px;
      color: #000;
    }

    &__comunication {
      font-family: "Roboto", sans-serif;
      font-size: 14px;
      font-weight: 300;
      line-height: 14px;
      color: #999999;
      height: 14px;

      &_off {
        visibility: hidden;
      }
    }
  }

  &__priceIcon {
    display: flex;
    align-items: center;
  }
}

.content {
  display: flex;
  flex-direction: column;
  gap: 5px;
  &__item {
    display: flex;
    align-items: center;
    justify-content: space-between;

    &__name {
      font-family: "Roboto", sans-serif;
      font-size: 16px;
      font-weight: 400;
      line-height: 16px;
      color: #000;

      &_last {
        font-size: 14px;
        font-weight: 300;
        line-height: 14px;
        color: #999999;
      }
    }
    &__meaning {
      font-family: "Roboto", sans-serif;
      font-size: 16px;
      font-weight: 500;
      line-height: 16px;
      color: #000;

      &_last {
        font-size: 14px;
        font-weight: 300;
        line-height: 14px;
        color: #999999;
      }
    }
  }
}

.buttons {
  display: flex;
  gap: 10px;
  align-items: center;
  justify-content: space-between;
  &__button {
    border: 1px solid #dedede;
    border-radius: 8px;
    width: 103px;
    height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #fff;
    position: relative;

    &__tooltip {
      height: 24px;
      padding: 5px 10px 5px 10px;
      font-family: "Roboto", sans-serif;
      font-size: 14px;
      font-weight: 300;
      line-height: 14px;
      color: #000;
      background-color: #fff;
      border: 1px solid #d9d9d9;
      border-radius: 4px;
      box-shadow: 2px 2px 10px 0 rgba(0, 0, 0, 0.1);
      white-space: nowrap;
      display: none;
      position: absolute;
      bottom: -24px;

      &_last {
        left: -58px;
      }
    }

    &:hover {
      background-color: #ffbf4b4d;
    }

    &:hover &__tooltip {
      display: block;
    }
  }
}

.buttonMain {
  border: none;
  border-radius: 8px;
  background-color: #ffbf4b;
  color: #fff;
  width: 330px;
  padding: 10px 0;
  font-family: "Roboto", sans-serif;
  font-size: 16px;
  font-weight: 700;
  line-height: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  cursor: pointer;

  &:hover {
    background-color: #cc993c;
  }
}
</style>
