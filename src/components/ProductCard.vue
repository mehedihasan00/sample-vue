<template>
  <div class="div-card">
    <div class="flex justify-between">
      <div class="lg:w-1/12 w-3/12 overflow-hidden">
        <img :src="property.imageUrl" :alt="property.imageAlt" class="product-image">
      </div>
      <div class="lg:w-8/12 w-6/12 p-1">
        <div class="w-full">
          <div class="text-gray-600 text-xs uppercase font-semibold tracking-wide">Product Name</div>
          <h4 class="font-semibold text-lg leading-tight truncate mt-1">TK 100</h4>
        </div>
      </div>
      <div class="lg:w-2/12 w-3/12 flex flex-col text-center p-1">
          <div class="w-full">
            <button class="border rounded h-12 w-full p-1">
              <span class="text-xl">0</span>
            </button>
          </div>
          <div class="w-full flex mt-1">
            <button class="w-full border rounded h-8 w-8 mr-1">
              <span class="text-xl"><i class="fal fa-plus"></i></span>
            </button>

            <button class="w-full border rounded h-8 w-8 ml-1">
              <span class="text-xl"><i class="fal fa-minus"></i></span>
            </button>
          </div>
      </div>
        <!--<div class="w-1/3 text-right">
          <button class="border rounded-full h-20 w-20 p-4">
            <img src="../assets/cart.svg" alt />
          </button>
        </div>-->
    </div>
    <!---<div class="text-center mt-2 text-gray-700 text-sm text-red-700 mb-0">
      <button class="border rounded-sm px-4 py-2 w-full">
        Add to cart
      </button>
    </div>-->
  </div>
</template>

<script>
export default {
  props: {
    property: Object
  }
}
</script>

<style>
</style>