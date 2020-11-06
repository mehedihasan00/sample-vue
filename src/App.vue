<template>
  <div class="header flex justify-between">
    <div class="w-1/6 text-center">
      <button @click="dropdownVisible" class="text-3xl px-3 py-1 text-blue-500 focus:outline-none">
        <i class="fal fa-bars"></i>
      </button>
    </div>
    <div class="input-group w-full">
      <input
        type="search"
        class="input"
        placeholder="Search Anything..."
        @focus="menuVisible"
      />
      <button class="search-btn">
        <img src="./assets/search.svg" alt />
      </button>
    </div>
    <div class="w-1/6 text-center">
      <button class="text-3xl px-3 py-1 text-blue-500 focus:outline-none">
        <i class="fal fa-shopping-bag"></i>
      </button>
    </div>
  </div>
  <div :class="{ 'menu-card ': true, 'menu-visible': menuVis }">
    <div
      class="w-full flex flex-wrap sm:divide-y sm:divide-x-0 lg:divide-y-0 xl:divide-x divide-gray-300"
    >
      <div class="lg:w-1/4 w-full h-full">
        <div class="menu-title">Menu</div>
      </div>
      <div class="lg:w-3/4 w-full h-full p-2">
        <div class="menu-title">Search Result</div>
        <ul>
          <li class="border-b border-b-1 px-1 py-2">
            <a href="#" class="text-blue-500">All Result</a> 20 results found
          </li>
          <li class="border-b border-b-1 px-1 py-2">
            <a href="#" class="text-blue-500">Category 1</a> 20 results found
          </li>
          <li class="border-b border-b-1 p-1">
            <a href="#" class="text-blue-500">Category 2</a> 20 results found
          </li>
        </ul>
      </div>
    </div>
  </div>

  <div :class="{'dropdown-card': true, 'dropdown-visible': dropdownVis}">
    <div
      class="h-full flex flex-col sm:divide-x sm:divide-y-0 lg:divide-x-0 xl:divide-y divide-gray-300"
    >
      <div class="dr-menu-profile">
        <div class="w-auto h-24 text-center">
          <img class="w-20 h-20 rounded-full" src="./assets/donald-trump-jm-0932.jpg" alt="Trump PowerMan">
          <span class="dr-menu-title">John Doe</span>
        </div>
      </div>
      <ul>
          <li v-for="route in routes" :key="route.id" class="border-b border-b-1 px-1 py-2 text-blue-500">
            <span v-html="route.icon"></span>
            {{ route.name }}
          </li>
        </ul>
    </div>
  </div>

  <button
    @click="backdropVisiblity"
    :class="{ backdrop: true, 'bd-visible': menuVis}"
  ></button>

  <div class="content-body">
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property" />
    </div>
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property" />
    </div>
    <div class="lg:full sm:w-auto p-2">
      <ProductCard :property="property" />
    </div>
    <div class="lg:full sm:w-auto p-2">
      <ProductCard :property="property" />
    </div>
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property" />
    </div>
  </div>
</template>

<script>
import ProductCard from "./components/ProductCard.vue";
//import ProductInfo from "./components/ProductInfo";

export default {
  name: "App",
  components: {
    ProductCard
  },
  data() {
    return {
      property: {
        imageUrl:
          "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
        imageAlt: "",
        beds: 2,
        baths: 2,
        title: "Nice",
        formattedPrice: 100,
        rating: 3,
        reviewCount: 5,
      },
      routes: [
        {id: 0, name: 'Home', icon: '<i class="fad fa-home"></i>'},
        {id: 1, name: 'Order', icon: '<i class="far fa-shopping-cart"></i>'},
        {id: 2, name: 'Contacts', icon: '<i class="fas fa-portrait"></i>'},
        {id: 3, name: 'Settings', icon: '<i class="far fa-cog"></i>'},
        {id: 4, name: 'Notifications', icon: '<i class="fal fa-bell"></i>'},
        {id: 5, name: 'Change Password', icon: '<i class="far fa-lock-alt"></i>'}
      ],
      menuVis: false,
      dropdownVis: false
    };
  },
  methods: {
    menuVisible() {
      this.menuVis = true;
      this.dropdownVis = false;
    },
    dropdownVisible() {
      this.dropdownVis = !this.dropdownVis;
      this.menuVis = false;
    },
    backdropVisiblity() {
      this.menuVis = false;
      this.dropdownVis = false;
    }
  },
};
</script>
