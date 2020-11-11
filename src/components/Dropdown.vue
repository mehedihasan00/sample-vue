<template>
  <div :class="{'dropdown-card': true, 'dropdown-visible': dropdownVis}">
    <div
      class="h-full flex flex-col sm:divide-x sm:divide-y-0 lg:divide-x-0 xl:divide-y divide-gray-300"
    >
      <div class="dr-menu-profile flex justify-between">
        <div class="w-auto h-24 flex flex-row">
          <img class="w-20 h-20 rounded-full" src="../assets/donald-trump-jm-0932.jpg" alt="Trump PowerMan">
          <span class="dr-menu-title pl-2 pt-6">John Doe</span>
        </div>
        <div>
          <button class="h-auto w-auto">
            <i class="fal fa-sign-out-alt"></i>
            Sign Out
          </button>
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
</template>

<script>
export default {
  name: "Dropdown",
  props: {
    routes: Array,
    dropdownVis: Boolean
  }
}
</script>