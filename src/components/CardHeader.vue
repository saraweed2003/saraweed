<template>
  <div class="">
    <ul class="flex justify-center text-[14px]">
      <li>
        <RouterLink
          to="/"
          class="m-1 px-[10px] py-[5px] border-2 border-gray-800 rounded-lg hover:bg-gray-800 hover:text-white hover:transition-all hover:duration-300 dark:text-white"
        >
          Home</RouterLink
        >
        <RouterLink
          to="/about"
          class="m-1 px-[10px] py-[5px] border-2 border-gray-800 rounded-lg hover:bg-gray-800 hover:text-white hover:transition-all hover:duration-300 dark:text-white"
        >
          About</RouterLink
        >
      </li>
    </ul>

    <div>
      <hr class="border-1 my-8 border-gray-500 sm:w-full mx-auto" />
    </div>
  </div>
</template>
<script setup>
import router from "../router";

const route = router.currentRoute.value.path;
</script>
