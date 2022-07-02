<template>
  <div class="category-item-book">
    <div class="category-image">
      <div v-if="freeRead" class="button read-item">
        <router-link :to="formatReadPath(id)"
          ><font-awesome-icon icon="fa-solid fa-book-open"
        /></router-link>
      </div>
      <router-link :to="formatBookPath(id)"
        ><img :src="image" :alt="imageAlt"
      /></router-link>
    </div>
    <div class="category-info">
      <span class="category-info-line"
        ><router-link :to="formatBookPath(id)">{{ title }}</router-link></span
      ><br />
      <span class="category-info-line">by {{ author }}</span
      ><br />
      <span class="category-info-line"
        ><router-link :to="formatBookPath(id)"
          >Add to Cart | ${{ price.toFixed(2) }}
          <font-awesome-icon icon="fa-solid fa-cart-plus" /></router-link
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "book-item",
  methods: {
    formatBookPath(bookId) {
      let val = "/book/" + bookId.toString();
      return val.toLowerCase();
    },
    formatReadPath(bookId) {
      let val = "/book/" + bookId.toString() + "/read";
      return val.toLowerCase();
    },
    bookImageFileName(title) {
      let name = title.toLowerCase();
      name = name.replace(/ /g, "-");
      return `${name}.png`;
    },
  },
  props: {
    id: {
      type: Number,
      required: true,
    },
    image: {
      type: String,
      default: "../assets/images/books/no_book_picture.png",
    },
    imageAlt: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    author: {
      type: String,
      required: true,
    },
    freeRead: {
      type: Boolean,
      default: false,
    },
    readPath: {
      type: String,
      default: "#",
    },
    price: {
      type: Number,
      default: 0.0,
    },
  },
};
</script>

<style scoped>
.category-image img {
  width: 100px;
  height: 145px;
}
</style>
