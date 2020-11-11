<template>
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
</template>

<script>
export default {
  props: {
    menuVis: Boolean
  }
}
</script>