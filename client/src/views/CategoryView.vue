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
              v-for="(item, index) in categories"
              v-bind:key="index"
              :genre="item.genre"
              :title="item.title"
              :href="item.href"
              :imageAlt="item.imageAlt"
              :image="item.image"
            ></category-item>
          </div>
          <div class="category-more">
            <router-link class="button button-tertiary" to="/category"
              >More ...</router-link
            >
          </div>
        </div>
        <div class="page-space">&nbsp;</div>
        <div class="category-line clearfix">
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
              :id="item.id"
              :title="item.title"
              :author="item.author"
              :price="item.price"
              :imageAlt="item.imageAlt"
              :image="item.image"
              :free-read="item.freeRead"
              :read-path="item.readPath"
            ></book-item>
          </div>
          <div class="category-more">
            <router-link class="button button-tertiary" to="/book"
              >More ...</router-link
            >
          </div>
        </div>
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
import BookItem from "@/components/BookItem";
import "@/assets/css/page-category.css";
import fictionClassics from "../assets/images/categories/classics.png";
import fictionMystery from "../assets/images/categories/mystery.png";
import howToHomediy from "../assets/images/categories/homediy.png";
import bookGaia from "../assets/images/books/gaia_garden.png";
import bookBookcases from "../assets/images/books/bookcases_cabinets.png";
import bookIlluminated from "../assets/images/books/computerscience_illuminated.png";
import bookFormalFoundations from "../assets/images/books/formal_foundations_reuse.jpg";
import bookNoPicture from "../assets/images/books/no_book_picture.png";

export default {
  name: "CategoryView",
  components: {
    AppPageTitle,
    CategoryVNav,
    CategoryItem,
    BookItem,
  },
  data() {
    return {
      page: {
        title: "Browse Inventory",
      },
      categories: [
        {
          genre: "Fiction",
          title: "Classics",
          image: fictionClassics,
          imageAlt: "Classic Fiction Canvas",
        },
        {
          genre: "Fiction",
          title: "Mystery",
          image: fictionMystery,
          imageAlt: "Mysterious Lamp Canvas",
        },
        {
          genre: "How-To",
          title: "Home DIY",
          image: howToHomediy,
          imageAlt: "Mechanical Parts Canvas",
        },
      ],
      books: [
        {
          id: 1,
          title: "Gaia's Garden",
          author: "Toby Hemenway",
          image: bookGaia,
          imageAlt: "Gaia's Garden Floral Book Cover",
          freeRead: false,
          price: 9.99,
        },
        {
          id: 2,
          title: "Bookcases, Cabinets, & Built-Ins",
          author: "Fine Woodworking (editor)",
          image: bookBookcases,
          imageAlt: "Bookcases Cabinets and Built-ins Book Cover",
          freeRead: false,
          price: 8.49,
        },
        {
          id: 3,
          title: "Computer Science Illuminated",
          author: "Nell B Dale",
          image: bookIlluminated,
          imageAlt: "Computer Science Illuminated Book Cover",
          freeRead: false,
          price: 21.59,
        },
        {
          id: 4,
          title: "Treasure Island",
          author: "Robert Louis Stevenson",
          image: bookNoPicture,
          imageAlt: "Treasure Island Book Cover",
          freeRead: true,
          readPath: "testPath",
          price: 0.0,
        },
        {
          id: 5,
          title: "Formal Foundations of Reuse and Domain Engineering",
          author: "Stephen H. Edwards, Gregory Kulczycki (Eds.)",
          image: bookFormalFoundations,
          imageAlt: "Formal Foundations Book Cover",
          freeRead: false,
          price: 42.1,
        },
      ],
    };
  },
};
</script>

<style scoped>
.content_container {
  width: 100%;
}
</style>
