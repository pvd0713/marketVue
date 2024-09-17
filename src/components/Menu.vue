<script setup>
import { ref } from "vue";

// Список категорий и подкатегорий
const categories = ref([
  {
    id: 1,
    name: "Все категории",
    subcategories: [
      {
        id: 11,
        name: "Электроника",
        subcategories: [
          { id: 111, name: "Телефоны" },
          { id: 112, name: "Ноутбуки" },
        ],
      },
      {
        id: 12,
        name: "Одежда",
        subcategories: [
          { id: 121, name: "Мужская одежда" },
          { id: 122, name: "Женская одежда" },
        ],
      },
      {
        id: 13,
        name: "Мебель",
        subcategories: [
          { id: 131, name: "Кровати" },
          { id: 132, name: "Стулья" },
        ],
      },
    ],
  },
]);

// Выбранная категория
const selectedCategory = ref(null);

// Функция для выбора категории
const selectCategory = (category) => {
  selectedCategory.value = category;
};

// Функция для выбора подкатегории
const selectSubcategory = (subcategory) => {
  // Показываем вложенные подкатегории
  subcategory.open = !subcategory.open;
};

// Функция для выбора под-подкатегории (третьего уровня)
const selectSubSubcategory = (subSubcategory) => {
  alert(`Вы выбрали подкатегорию: ${subSubcategory.name}`);
};

// Функция для возврата к категориям верхнего уровня
const clearSelection = () => {
  selectedCategory.value = null;
};
</script>

<template>
  <p class="title">Категория</p>
  <div class="category-menu">
    <ul v-if="!selectedCategory">
      <li v-for="category in categories" :key="category.id">
        <div @click="selectCategory(category)">
          {{ category.name }}
        </div>
      </li>
    </ul>

    <!-- Подкатегории выбранной категории -->
    <ul v-else>
      <li
        v-for="subcategory in selectedCategory.subcategories"
        :key="subcategory.id"
      >
        <div @click="selectSubcategory(subcategory)">
          {{ subcategory.name }}
        </div>

        <!-- Вложенные подкатегории -->
        <ul v-if="subcategory.open">
          <li
            v-for="subSubcategory in subcategory.subcategories"
            :key="subSubcategory.id"
          >
            <div @click="selectSubSubcategory(subSubcategory)">
              {{ subSubcategory.name }}
            </div>
          </li>
        </ul>
      </li>

      <!-- Кнопка для возврата к категориям верхнего уровня -->
      <li>
        <button @click="clearSelection">Назад к категориям</button>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.title {
  font-family: "Roboto", sans-serif;
  font-size: 16px;
  font-weight: 700;
  line-height: 16px;
  color: #000;
}
.category-menu ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.category-menu li {
  margin: 5px 0;
  cursor: pointer;
}

.subcategory-list {
  padding-left: 15px;
  margin-top: 5px;
}

.category-menu div {
  padding: 5px;
}

.category-menu div:hover {
  font-weight: bold;
}

button {
  margin-top: 10px;
  padding: 5px 10px;
  cursor: pointer;
}
</style>
