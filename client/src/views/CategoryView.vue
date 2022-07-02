<template>
  <!-- #### main Code #### -->
  <main id="main" class="clearfix">
    <section class="content_container">
      <app-page-title :title="page.title" />
      <div class="page-quarter">
        <category-v-nav></category-v-nav>
      </div>
      <div class="page-threequarter">
        <div class="category-line clearfix">
          <div class="category-title">
            <table class="category-table">
              <tr>
                <td class="col-color">&nbsp;</td>
                <td class="col-text">Top Categories</td>
              </tr>
            </table>
          </div>
          <div class="category-content">
            <category-item
              v-for="category in categories"
              :key="category.categoryId"
              :category="category"
            ></category-item>
          </div>
          <!--<div class="category-more">
            <router-link class="button button-tertiary" to="/category"
              >More ...</router-link
            >
          </div> -->
        </div>
        <div class="page-space">&nbsp;</div>
        <!-- <div class="category-line clearfix">
          <div class="category-title">
            <table class="category-table">
              <tr>
                <td class="col-color">&nbsp;</td>
                <td class="col-text">Favorite Books</td>
              </tr>
            </table>
          </div>
          <div class="category-content">
            <book-item
              v-for="(item, index) in books"
              v-bind:key="index"
              :category="item"
            ></book-item>
          </div>
          <div class="category-more">
            <router-link class="button button-tertiary" to="/book"
              >More ...</router-link
            >
          </div>
        </div> -->
      </div>
      <div class="page-space">&nbsp;</div>
    </section>
  </main>
  <!-- #### End main Code #### -->
</template>

<script>
// @ is an alias to /src
import AppPageTitle from "@/components/AppPageTitle";
import CategoryVNav from "@/components/CategoryVNav";
import CategoryItem from "@/components/CategoryItem";
//import BookItem from "@/components/BookItem";
import "@/assets/css/page-category.css";
//import bookGaia from "../assets/images/books/gaia_garden.png";
//import bookBookcases from "../assets/images/books/bookcases_cabinets.png";
//import bookIlluminated from "../assets/images/books/computerscience_illuminated.png";
//import bookFormalFoundations from "../assets/images/books/formal_foundations_reuse.jpg";
//import bookNoPicture from "../assets/images/books/no_book_picture.png";
import ApiService from "@/services/ApiService";

export default {
  name: "CategoryView",
  components: {
    AppPageTitle,
    CategoryVNav,
    CategoryItem,
  },
  data() {
    return {
      page: {
        title: "Browse Inventory",
      },
      categories: [],
      books: [],
    };
  },
  created: function () {
    console.log("Begin fetchCategories...");
    this.fetchCategories();
    console.log("End fetchCategories...");
  },
  methods: {
    fetchCategories() {
      const vm = this;
      ApiService.fetchCategories()
        .then((data) => {
          console.log("Data: " + data);
          vm.categories = data;
        })
        .catch((reason) => {
          console.log("Error: " + reason);
        });
    },
  },
};
</script>

<style scoped>
.content_container {
  width: 100%;
}
</style>
