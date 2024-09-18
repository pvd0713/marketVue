<script setup>
import { computed, ref, watch } from "vue";

// Продуктовые данные
const product = ref({
  name: "Самсунг 0101",
  images: [
    "https://cdn1.ozone.ru/s3/multimedia-n/6351301379.jpg",
    "https://alfasnab.com/files/images/news/telefon.jpg",
    "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Nokia_5800_XpressMusic_3Q.jpg/500px-Nokia_5800_XpressMusic_3Q.jpg",
    "https://avatars.dzeninfra.ru/get-zen_doc/9729319/pub_647d9d92a3f6b41a2ec255dd_647da14b69caf1277ba2e10c/scale_1200",
    "https://cdn1.ozone.ru/s3/multimedia-7/6003585391.jpg",
    "https://avatars.mds.yandex.net/i?id=f1b9360ddc703974c9ec4ef354b51c64100a4969-4912286-images-thumbs&n=13",
    "https://diamondelectric.ru/images/798/797992/philips_xenium_x518_3.jpg",
    "https://avatars.mds.yandex.net/i?id=eb6a450b03531393548fd0ac356a2c223c3fed1b-9147032-images-thumbs&n=13",
  ],
  specs: [
    { param: "Параметр", value: "Значение" },
    { param: "Параметр", value: "11111111111111" },
    { param: "Параметр", value: "11aaaaaaaa" },
    { param: "Параметр", value: "Значение" },
    { param: "Параметр", value: "Показатель" },
    { param: "Параметр", value: "123456789" },
  ],
});

// Текущее выбранное изображение
const selectedImage = ref(product.value.images[0]);

// Функция для выбора изображения
const selectImage = (image) => {
  selectedImage.value = image;
};

// Слайд на предыдущее изображение
const previousImage = () => {
  const currentIndex = product.value.images.indexOf(selectedImage.value);
  if (currentIndex > 0) {
    selectedImage.value = product.value.images[currentIndex - 1];
  }
};

// Слайд на следующее изображение
const nextImage = () => {
  const currentIndex = product.value.images.indexOf(selectedImage.value);
  if (currentIndex < product.value.images.length - 1) {
    selectedImage.value = product.value.images[currentIndex + 1];
  }
};

const props = defineProps({
  view: Array,
});

const widthBlock = computed(() => {
  if (props.view.indexOf("sallers") !== -1) {
    return "100%";
  } else {
    return "46%";
  }
});
</script>

<template>
  <div class="product-card">
    <!-- Заголовок продукта -->
    <div class="product-title">
      <h2 class="product-title__title">{{ product.name }}</h2>
      <svg
        width="18"
        height="22"
        viewBox="0 0 18 22"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M16.1875 21.9375C15.9968 21.9338 15.8108 21.8775 15.65 21.775L9 17.1375L2.35 21.775C2.20311 21.8644 2.03446 21.9117 1.8625 21.9117C1.69054 21.9117 1.52189 21.8644 1.375 21.775C1.23114 21.7009 1.10926 21.5903 1.02152 21.4543C0.933781 21.3183 0.883259 21.1616 0.875 21V3.5C0.875 2.58832 1.23716 1.71398 1.88182 1.06932C2.52648 0.424664 3.40082 0.0625 4.3125 0.0625H13.6875C14.5992 0.0625 15.4735 0.424664 16.1182 1.06932C16.7628 1.71398 17.125 2.58832 17.125 3.5V21C17.1256 21.1702 17.0793 21.3373 16.9911 21.4828C16.9028 21.6284 16.7762 21.7468 16.625 21.825C16.4909 21.8986 16.3405 21.9373 16.1875 21.9375ZM9 15.0625C9.19156 15.0605 9.37914 15.1172 9.5375 15.225L15.25 19.2V3.5C15.25 3.0856 15.0854 2.68817 14.7924 2.39515C14.4993 2.10212 14.1019 1.9375 13.6875 1.9375H4.3125C3.8981 1.9375 3.50067 2.10212 3.20765 2.39515C2.91462 2.68817 2.75 3.0856 2.75 3.5V19.2L8.4625 15.225C8.62086 15.1172 8.80844 15.0605 9 15.0625Z"
          fill="black"
        />
      </svg>
    </div>

    <!-- Главное изображение с кнопками переключения -->
    <div class="main-image-container">
      <img
        class="image-btn left"
        @click="previousImage"
        src="../assets/img/ArrowLeft.svg"
        alt="img"
      />
      <img :src="selectedImage" :alt="product.name" class="main-image" />
      <img
        class="image-btn right"
        @click="nextImage"
        src="../assets/img/ArrowRight.svg"
        alt="img"
      />
    </div>

    <!-- Слайдер миниатюр -->
    <div class="sliderBlock">
      <div class="thumbnail-slider">
        <img
          class="slider-btn left"
          @click="previousImage"
          src="../assets/img/ArrowLeft.svg"
          alt="img"
        />
        <div class="thumbnails">
          <img
            v-for="(image, index) in product.images"
            :key="index"
            :src="image"
            :alt="'Image ' + (index + 1)"
            :class="{ active: selectedImage === image }"
            @click="selectImage(image)"
            class="thumbnail"
          />
        </div>
        <img
          class="slider-btn right"
          @click="nextImage"
          src="../assets/img/ArrowRight.svg"
          alt="img"
        />
      </div>
    </div>

    <!-- Таблица характеристик -->
    <h3>Характеристики</h3>
    <div class="specs">
      <div class="spec" v-for="(spec, index) in product.specs" :key="index">
        <div class="param">{{ spec.param }}</div>
        <div class="dotts"></div>
        <div class="value">{{ spec.value }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.product-card {
  box-sizing: border-box;
  max-width: 100%;
  min-width: 562px;
  padding: 20px;
  box-sizing: border-box;
  background-color: #f5f5f5;
  border: 1px solid #dedede;
  border-radius: 8px;
  margin-bottom: 50px;
}

.product-title {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;

  &__title {
    font-family: "Roboto", sans-serif;
    font-size: 30px;
    font-weight: 700;
    line-height: 30px;
    color: #000;
  }
}

/* Главное изображение */
.main-image-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 15px;
  // width: 100%;
}

.main-image {
  width: 100%;
  height: 655px;
  border-radius: 5px;
  object-fit: contain;
}

.image-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  color: #fff;
  border: none;
  font-size: 24px;
  cursor: pointer;
  padding: 10px;
  z-index: 1;
}

.image-btn.left {
  left: 10px;
}

.image-btn.right {
  right: 10px;
}

/* Слайдер миниатюр */
.sliderBlock {
  position: relative;
}
.thumbnail-slider {
  width: 100%;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.thumbnails {
  width: 100%;
  display: flex;
  flex-wrap: nowrap;
  // overflow-x: auto ;
}

.thumbnail-slider::-webkit-scrollbar {
  height: 10px;
}
.thumbnail-slider::-webkit-scrollbar-thumb {
  background-color: #ccc;
  border-radius: 4px;
}
.thumbnail-slider::-webkit-scrollbar-track {
  background-color: #f5f5f5;
}

.thumbnail {
  width: 136px;
  height: 91px;
  object-fit: contain;
  margin-right: 10px;
  cursor: pointer;
  border: 2px solid transparent;
  transition: border-color 0.2s;
}

.thumbnail:hover,
.thumbnail.active {
  border-color: #000;
}

.slider-btn {
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
  padding: 0 10px;
  position: absolute;
}

.left {
  left: 0;
}

.right {
  right: 0;
}

/* Таблица характеристик */
.specs {
  display: flex;
  flex-wrap: wrap;
  margin-top: 20px;
  column-gap: 40px;
}

.spec {
  display: flex;
  justify-content: space-between;
  width: v-bind(widthBlock);

  padding: 10px 0;
  box-sizing: border-box;
}

.param {
  color: #999;
  font-style: italic;
}

.dotts {
  width: auto;
  flex-grow: 1;
  // border-bottom: 1.5px dotted #999;
  background-image: linear-gradient(
    to right,
    #999 33%,
    rgba(255, 255, 255, 0) 0%
  );
  background-position: bottom;
  background-size: 5px 1.5px;
  background-repeat: repeat-x;
}

.value {
  color: #000;
  text-align: right;
}
</style>
