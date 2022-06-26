<template>
  <div id="v-nav" class="clearfix">
    <div class="v-nav-content">
      <div class="menu-title">
        <span class="text">Favorites</span>
        <span class="chevron"
          ><font-awesome-icon icon="fa-solid fa-chevron-down"
        /></span>
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" />
        Best Sellers
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> New Releases
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> In Stock
      </div>

      <div class="menu-title">
        <span class="text">Condition</span>
        <span class="chevron"
          ><font-awesome-icon icon="fa-solid fa-chevron-down"
        /></span>
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> All
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> New
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> Used
      </div>

      <div class="menu-title">
        <span class="text">Format</span>
        <span class="chevron"
          ><font-awesome-icon icon="fa-solid fa-chevron-down"
        /></span>
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> All
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> Hardcover
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> Paperback
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> eBook
      </div>
      <div class="menu-item">
        <font-awesome-icon icon="fa-regular fa-square" /> Textbook
      </div>

      <div class="menu-title">
        <span class="text">More</span>
        <span class="chevron"
          ><font-awesome-icon icon="fa-solid fa-chevron-right"
        /></span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "category-v-nav",
};
</script>
<style scoped>
#v-nav {
  padding-left: 15px;
  padding-bottom: 15px;
}

.v-nav-content {
  max-width: 100%;
  min-width: 175px;
  border: 1px var(--BorderShade) solid;
}

#v-nav .menu-title {
  background-color: var(--PrimaryColor);
  padding: 10px;
  color: #fff;
}

#v-nav .menu-title .text {
}

#v-nav .menu-title .chevron {
  float: right;
}

#v-nav .menu-item {
  padding: 5px;
  padding-left: 15px;
}
</style>
