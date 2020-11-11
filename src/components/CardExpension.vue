<template>
  <div :class="{'card-expansion': true, 'card-expansion-visible': cardExpVis}">
    <div class="flex justify-between border-b pb-2">
      <img :src="property.imageUrl" class="w-64 h-64" alt="property">
      <button class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold 
        hover:text-white border border-blue-500 hover:border-transparent rounded h-8 w-16" 
        @click="cardExpVisible"
      >
        exit
      </button>
    </div>
    <div class="pt-2">
      <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Laudantium optio molestias, ducimus nostrum exercitationem eum sed placeat ullam blanditiis cumque quisquam aliquam praesentium sequi, at, asperiores architecto maxime similique dolor.</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cardExpVis: Boolean,
    property: Function,
    cardExpVisible: Function
  }
}
</script>