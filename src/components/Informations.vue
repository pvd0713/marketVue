<script setup>
import { ref, computed } from "vue";
import Article from "./InformationsArticle.vue";

// Array of articles (data)
const articles = ref([
  {
    id: 1,
    date: "2024-07-01",
    expert: "Иванов Иван",
    avatar:
      "https://avatars.mds.yandex.net/i?id=cfba15d1df37615f4a29f455d33fafa8e24856f5-9839669-images-thumbs&n=13",
    title: "Телефон Самсунг 0101 - новинка среди смартфонов",
    description:
      "Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст.",
    img: "https://avatars.mds.yandex.net/i?id=c771747cd2bc9fdb746e8b10cf27162161c84e8aba114fe9-12267805-images-thumbs&n=13",
    likes: 157,
    dislikes: 5,
    comments: 12,
    views: 10256,
  },
  {
    id: 2,
    date: "2024-07-02",
    expert: "Сидоров Иван",
    avatar:
      "https://avatars.mds.yandex.net/i?id=cfba15d1df37615f4a29f455d33fafa8e24856f5-9839669-images-thumbs&n=13",
    title: "Телефон Самсунг 0101 - новинка среди смартфонов",
    description:
      "Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст.",
    img: "https://avatars.mds.yandex.net/i?id=c771747cd2bc9fdb746e8b10cf27162161c84e8aba114fe9-12267805-images-thumbs&n=13",
    likes: 157,
    dislikes: 5,
    comments: 12,
    views: 10256,
  },
  {
    id: 3,
    date: "2024-07-03",
    expert: "Петров Алексей",
    avatar:
      "https://avatars.mds.yandex.net/i?id=cfba15d1df37615f4a29f455d33fafa8e24856f5-9839669-images-thumbs&n=13",
    title: "Телефон Самсунг 0101 - новинка среди смартфонов",
    description:
      "Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст.",
    img: "https://avatars.mds.yandex.net/i?id=c771747cd2bc9fdb746e8b10cf27162161c84e8aba114fe9-12267805-images-thumbs&n=13",
    likes: 120,
    dislikes: 10,
    comments: 15,
    views: 8000,
  },
  {
    id: 4,
    date: "2024-07-04",
    expert: "Кузнецов Александр",
    avatar:
      "https://avatars.mds.yandex.net/i?id=cfba15d1df37615f4a29f455d33fafa8e24856f5-9839669-images-thumbs&n=13",
    title: "Телефон Самсунг 0101 - новинка среди смартфонов",
    description:
      "Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст.",
    img: "https://avatars.mds.yandex.net/i?id=c771747cd2bc9fdb746e8b10cf27162161c84e8aba114fe9-12267805-images-thumbs&n=13",
    likes: 180,
    dislikes: 7,
    comments: 20,
    views: 9000,
  },
  {
    id: 5,
    date: "2024-07-05",
    expert: "Морозов Сергей",
    avatar:
      "https://avatars.mds.yandex.net/i?id=cfba15d1df37615f4a29f455d33fafa8e24856f5-9839669-images-thumbs&n=13",
    title: "Телефон Самсунг 0101 - новинка среди смартфонов",
    description:
      "Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст. Начало статьи, главная мысль, цитата, статистика, мнение автора, вывод по статье, любой текст.",
    img: "https://avatars.mds.yandex.net/i?id=c771747cd2bc9fdb746e8b10cf27162161c84e8aba114fe9-12267805-images-thumbs&n=13",
    likes: 110,
    dislikes: 8,
    comments: 10,
    views: 9500,
  },
]);

// Visibility flags for sorting and filtering modals
const showSorting = ref(false);
const showFilters = ref(false);

// Sorting key
const sorting = ref(null);

// Filter criteria
const filters = ref({
  date: null,
  likes: { min: null, max: null },
  dislikes: { min: null, max: null },
  comments: { min: null, max: null },
  views: { min: null, max: null },
});

// Toggle sorting modal visibility
const toggleSorting = () => {
  showSorting.value = !showSorting.value;
};

// Toggle filter modal visibility
const toggleFilters = () => {
  showFilters.value = !showFilters.value;
};

// Sorting function
const sortBy = (key) => {
  sorting.value = key;
  showSorting.value = false;
};

// Apply filter settings
const applyFilters = () => {
  showFilters.value = false;
};

// Computed property for filtered and sorted articles
const sortedFilteredArticles = computed(() => {
  // Copy articles for sorting and filtering
  let sorted = [...articles.value];

  // Sorting logic
  if (sorting.value) {
    sorted.sort((a, b) => {
      if (sorting.value === "date") return new Date(b.date) - new Date(a.date);
      return a[sorting.value] > b[sorting.value] ? 1 : -1;
    });
  }

  // Filtering logic
  return sorted.filter((article) => {
    const matchesDate =
      !filters.value.date || article.date >= filters.value.date;

    const matchesLikes =
      (!filters.value.likes.min || article.likes >= filters.value.likes.min) &&
      (!filters.value.likes.max || article.likes <= filters.value.likes.max);

    const matchesDislikes =
      (!filters.value.dislikes.min ||
        article.dislikes >= filters.value.dislikes.min) &&
      (!filters.value.dislikes.max ||
        article.dislikes <= filters.value.dislikes.max);

    const matchesComments =
      (!filters.value.comments.min ||
        article.comments >= filters.value.comments.min) &&
      (!filters.value.comments.max ||
        article.comments <= filters.value.comments.max);

    const matchesViews =
      (!filters.value.views.min || article.views >= filters.value.views.min) &&
      (!filters.value.views.max || article.views <= filters.value.views.max);

    // Apply filters only if any criteria are defined
    const areFiltersApplied =
      filters.value.date ||
      filters.value.likes.min !== null ||
      filters.value.likes.max !== null ||
      filters.value.dislikes.min !== null ||
      filters.value.dislikes.max !== null ||
      filters.value.comments.min !== null ||
      filters.value.comments.max !== null ||
      filters.value.views.min !== null ||
      filters.value.views.max !== null;

    // If no filters are applied, return all articles
    return (
      !areFiltersApplied ||
      (matchesDate &&
        matchesLikes &&
        matchesDislikes &&
        matchesComments &&
        matchesViews)
    );
  });
});
</script>

<template>
  <div class="informations">
    <!-- Title and buttons -->
    <div class="header">
      <p class="header__title">Информация</p>
      <p class="header__count">({{ articles.length }})</p>

      <div class="icons">
        <div class="header__sort" @click="toggleSorting">
          <svg
            width="30"
            height="30"
            viewBox="0 0 30 30"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M20 5.3125C20.5125 5.3125 20.9375 5.7375 20.9375 6.25V21.4875L22.4625 19.9625C22.825 19.6 23.425 19.6 23.7875 19.9625C23.975 20.15 24.0625 20.3875 24.0625 20.625C24.0625 20.8625 23.975 21.1 23.7875 21.2875L20.6625 24.4125C20.575 24.5 20.475 24.5625 20.3625 24.6125C20.1375 24.7125 19.875 24.7125 19.65 24.6125C19.5375 24.5625 19.4375 24.5 19.35 24.4125L16.225 21.2875C15.8625 20.925 15.8625 20.325 16.225 19.9625C16.5875 19.6 17.1875 19.6 17.55 19.9625L19.075 21.4875V6.25C19.075 5.7375 19.5 5.3125 20.0125 5.3125H20ZM10.9375 23.75V8.5125L12.4625 10.0375C12.825 10.4 13.425 10.4 13.7875 10.0375C13.975 9.85 14.0625 9.6125 14.0625 9.375C14.0625 9.1375 13.975 8.9 13.7875 8.7125L10.6625 5.5875C10.575 5.5 10.475 5.4375 10.3625 5.3875C10.1375 5.2875 9.875 5.2875 9.65 5.3875C9.5375 5.4375 9.4375 5.5 9.35 5.5875L6.225 8.7125C5.8625 9.075 5.8625 9.675 6.225 10.0375C6.5875 10.4 7.1875 10.4 7.55 10.0375L9.075 8.5125V23.75C9.075 24.2625 9.5 24.6875 10.0125 24.6875C10.525 24.6875 10.95 24.2625 10.95 23.75H10.9375Z"
              fill="black"
            />
          </svg>
        </div>
        <div class="header__filter" @click="toggleFilters">
          <svg
            width="30"
            height="30"
            viewBox="0 0 30 30"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M23.75 10.3125H15C14.7514 10.3125 14.5129 10.2137 14.3371 10.0379C14.1613 9.8621 14.0625 9.62364 14.0625 9.375C14.0625 9.12636 14.1613 8.8879 14.3371 8.71209C14.5129 8.53627 14.7514 8.4375 15 8.4375H23.75C23.9986 8.4375 24.2371 8.53627 24.4129 8.71209C24.5887 8.8879 24.6875 9.12636 24.6875 9.375C24.6875 9.62364 24.5887 9.8621 24.4129 10.0379C24.2371 10.2137 23.9986 10.3125 23.75 10.3125Z"
              fill="black"
            />
            <path
              d="M12.5 10.3125H6.25C6.00136 10.3125 5.7629 10.2137 5.58709 10.0379C5.41127 9.8621 5.3125 9.62364 5.3125 9.375C5.3125 9.12636 5.41127 8.8879 5.58709 8.71209C5.7629 8.53627 6.00136 8.4375 6.25 8.4375H12.5C12.7486 8.4375 12.9871 8.53627 13.1629 8.71209C13.3387 8.8879 13.4375 9.12636 13.4375 9.375C13.4375 9.62364 13.3387 9.8621 13.1629 10.0379C12.9871 10.2137 12.7486 10.3125 12.5 10.3125Z"
              fill="black"
            />
            <path
              d="M12.5 12.1875C12.2524 12.1843 12.0158 12.0845 11.8407 11.9093C11.6655 11.7342 11.5657 11.4976 11.5625 11.25V7.5C11.5625 7.25136 11.6613 7.0129 11.8371 6.83709C12.0129 6.66127 12.2514 6.5625 12.5 6.5625C12.7486 6.5625 12.9871 6.66127 13.1629 6.83709C13.3387 7.0129 13.4375 7.25136 13.4375 7.5V11.25C13.4343 11.4976 13.3345 11.7342 13.1593 11.9093C12.9842 12.0845 12.7476 12.1843 12.5 12.1875Z"
              fill="black"
            />
            <path
              d="M23.75 21.5625H15C14.7514 21.5625 14.5129 21.4637 14.3371 21.2879C14.1613 21.1121 14.0625 20.8736 14.0625 20.625C14.0625 20.3764 14.1613 20.1379 14.3371 19.9621C14.5129 19.7863 14.7514 19.6875 15 19.6875H23.75C23.9986 19.6875 24.2371 19.7863 24.4129 19.9621C24.5887 20.1379 24.6875 20.3764 24.6875 20.625C24.6875 20.8736 24.5887 21.1121 24.4129 21.2879C24.2371 21.4637 23.9986 21.5625 23.75 21.5625Z"
              fill="black"
            />
            <path
              d="M12.5 21.5625H6.25C6.00136 21.5625 5.7629 21.4637 5.58709 21.2879C5.41127 21.1121 5.3125 20.8736 5.3125 20.625C5.3125 20.3764 5.41127 20.1379 5.58709 19.9621C5.7629 19.7863 6.00136 19.6875 6.25 19.6875H12.5C12.7486 19.6875 12.9871 19.7863 13.1629 19.9621C13.3387 20.1379 13.4375 20.3764 13.4375 20.625C13.4375 20.8736 13.3387 21.1121 13.1629 21.2879C12.9871 21.4637 12.7486 21.5625 12.5 21.5625Z"
              fill="black"
            />
            <path
              d="M12.5 23.4375C12.2524 23.4343 12.0158 23.3345 11.8407 23.1593C11.6655 22.9842 11.5657 22.7476 11.5625 22.5V18.75C11.5625 18.5014 11.6613 18.2629 11.8371 18.0871C12.0129 17.9113 12.2514 17.8125 12.5 17.8125C12.7486 17.8125 12.9871 17.9113 13.1629 18.0871C13.3387 18.2629 13.4375 18.5014 13.4375 18.75V22.5C13.4343 22.7476 13.3345 22.9842 13.1593 23.1593C12.9842 23.3345 12.7476 23.4343 12.5 23.4375Z"
              fill="black"
            />
            <path
              d="M23.75 15.9375H20C19.7514 15.9375 19.5129 15.8387 19.3371 15.6629C19.1613 15.4871 19.0625 15.2486 19.0625 15C19.0625 14.7514 19.1613 14.5129 19.3371 14.3371C19.5129 14.1613 19.7514 14.0625 20 14.0625H23.75C23.9986 14.0625 24.2371 14.1613 24.4129 14.3371C24.5887 14.5129 24.6875 14.7514 24.6875 15C24.6875 15.2486 24.5887 15.4871 24.4129 15.6629C24.2371 15.8387 23.9986 15.9375 23.75 15.9375Z"
              fill="black"
            />
            <path
              d="M17.5 15.9375H6.25C6.00136 15.9375 5.7629 15.8387 5.58709 15.6629C5.41127 15.4871 5.3125 15.2486 5.3125 15C5.3125 14.7514 5.41127 14.5129 5.58709 14.3371C5.7629 14.1613 6.00136 14.0625 6.25 14.0625H17.5C17.7486 14.0625 17.9871 14.1613 18.1629 14.3371C18.3387 14.5129 18.4375 14.7514 18.4375 15C18.4375 15.2486 18.3387 15.4871 18.1629 15.6629C17.9871 15.8387 17.7486 15.9375 17.5 15.9375Z"
              fill="black"
            />
            <path
              d="M17.5 17.8125C17.2524 17.8093 17.0158 17.7095 16.8407 17.5343C16.6655 17.3592 16.5657 17.1226 16.5625 16.875V13.125C16.5625 12.8764 16.6613 12.6379 16.8371 12.4621C17.0129 12.2863 17.2514 12.1875 17.5 12.1875C17.7486 12.1875 17.9871 12.2863 18.1629 12.4621C18.3387 12.6379 18.4375 12.8764 18.4375 13.125V16.875C18.4343 17.1226 18.3345 17.3592 18.1593 17.5343C17.9842 17.7095 17.7476 17.8093 17.5 17.8125Z"
              fill="black"
            />
          </svg>
        </div>
      </div>
    </div>

    <!-- Articles Display -->
    <div class="informations__articles">
      <div v-for="article in sortedFilteredArticles" :key="article.id">
        <Article :article="article" />
      </div>
    </div>

    <!-- Sorting Modal -->
    <div v-if="showSorting" class="modal">
      <h3>Сортировка</h3>
      <button @click="sortBy('date')">От новых к старым</button>
      <button @click="sortBy('expert')">По алфавиту А...Я</button>
      <button @click="sortBy('likes')">Количество лайков</button>
      <button @click="sortBy('dislikes')">Количество дизлайков</button>
      <button @click="sortBy('comments')">Количество обсуждений</button>
      <button @click="sortBy('views')">Количество просмотров</button>
    </div>

    <!-- Filter Modal -->
    <div v-if="showFilters" class="modal">
      <h3>Фильтры</h3>
      <label
        >Дата публикации:
        <input type="date" v-model="filters.date" />
      </label>
      <label
        >Количество лайков:
        <input
          type="number"
          v-model="filters.likes.min"
          placeholder="Минимум"
        />
        -
        <input
          type="number"
          v-model="filters.likes.max"
          placeholder="Максимум"
        />
      </label>
      <label
        >Количество дизлайков:
        <input
          type="number"
          v-model="filters.dislikes.min"
          placeholder="Минимум"
        />
        -
        <input
          type="number"
          v-model="filters.dislikes.max"
          placeholder="Максимум"
        />
      </label>
      <label
        >Количество обсуждений:
        <input
          type="number"
          v-model="filters.comments.min"
          placeholder="Минимум"
        />
        -
        <input
          type="number"
          v-model="filters.comments.max"
          placeholder="Максимум"
        />
      </label>
      <label
        >Количество просмотров:
        <input
          type="number"
          v-model="filters.views.min"
          placeholder="Минимум"
        />
        -
        <input
          type="number"
          v-model="filters.views.max"
          placeholder="Максимум"
        />
      </label>
      <button @click="applyFilters">Сохранить</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.informations {
  box-sizing: border-box;
  position: relative;
  max-width: 100%;

  &__articles {
    display: grid; /* 1 */
    grid-template-columns: repeat(auto-fill, 460px); /* 2 */
    justify-content: center;
    max-width: 100%;
    row-gap: 20px;
    column-gap: 40px;
  }
}

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
  border-bottom: 1px solid #dedede;
  gap: 10px;

  &__title {
    font-family: "Roboto", sans-serif;
    font-size: 30px;
    font-weight: 700;
    line-height: 30px;
    color: #000;
  }

  &__count {
    font-family: "Roboto", sans-serif;
    font-size: 20px;
    font-weight: 400;
    line-height: 20px;
    color: #999999;
    padding-top: 4px;
  }
}

.icons {
  display: flex;
  gap: 10px;
  flex-grow: 1;
  justify-content: flex-end;
}

.modal {
  position: absolute;
  background-color: white;
  border: 1px solid #ccc;
  padding: 20px;
  top: 150px;
}
</style>
