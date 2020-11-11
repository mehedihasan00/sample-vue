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
  <!-- Search_bar Details -->
  
  <!-- SearchBar Details Ends -->

  <!-- dropdown_view -->
  <Dropdown :routes="routes" :dropdownVis="dropdownVis"/>
  <!-- dropdown_view_exit -->
  <SearchBarDetails :menuVis="menuVis"/>
  <!-- cardexpension -->
  <CardExpension :cardExpVis="cardExpVis" 
    :property="property"
    :cardExpVisible="cardExpVisible"
  />
  <!-- card_expansion ends -->

  <button
    @click="backdropVisiblity"
    :class="{ backdrop: true, 'bd-visible': menuVis, 'bd-visible-expansion': dropdownVis}"
  ></button>

  <div class="content-body">
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property"
        :cardExpVisible="cardExpVisible"
       />
    </div>
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property"
        :cardExpVisible="cardExpVisible"
       />
    </div>
    <div class="lg:full sm:w-auto p-2">
      <ProductCard :property="property"
        :cardExpVisible="cardExpVisible"
       />
    </div>
    <div class="lg:full sm:w-auto p-2">
      <ProductCard :property="property"
        :cardExpVisible="cardExpVisible"
      />
    </div>
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property"
        :cardExpVisible="cardExpVisible"
      />
    </div>
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property"
        :cardExpVisible="cardExpVisible"
      />
    </div>
    <div class="lg:w-full sm:w-auto p-2">
      <ProductCard :property="property"
        :cardExpVisible="cardExpVisible"
      />
    </div>
  </div>
</template>

<script>
import ProductCard from "./components/ProductCard.vue"
import SearchBarDetails from "./components/SearchBarDetails.vue"
import CardExpension from "./components/CardExpension.vue"
import Dropdown from "./components/Dropdown.vue"

//import ProductInfo from "./components/ProductInfo";

export default {
  name: "App",
  components: {
    ProductCard,
    SearchBarDetails,
    CardExpension,
    Dropdown
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
      dropdownVis: false,
      cardExpVis: false
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
    },
    cardExpVisible() {
      this.cardExpVis = !this.cardExpVis
    }
  },
};
</script>
