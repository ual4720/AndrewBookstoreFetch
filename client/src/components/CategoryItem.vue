<template>
  <div class="category-item-category">
    <div class="category-image">
      <router-link :to="formatCategoryPath(genre, title)"
        ><img :src="image" :alt="imageAlt"
      /></router-link>
    </div>
    <div class="category-info">
      <router-link :to="formatCategoryPath(genre, title)"
        >{{ genre }}: {{ title }}</router-link
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "category-item",
  methods: {
    formatCategoryPath(genre, title) {
      return (
        "/category/" +
        encodeURIComponent(genre) +
        "/" +
        encodeURIComponent(title)
      ).toLowerCase();
    },
  },
  props: {
    image: {
      type: String,
      required: true,
    },
    imageAlt: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    genre: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.category-image img {
  width: 175px;
  height: 150px;
}
</style>
