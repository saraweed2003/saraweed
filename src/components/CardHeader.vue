<template>
  <div class="">
    <ul class="flex justify-center text-[14px]">
      <li>
        <RouterLink
          to="/"
          class="m-1 rounded-lg hover:text-gray-500 hover:transition-all hover:duration-300 dark:text-white"
        >
          HOME
        </RouterLink>
        <RouterLink
          to="/about"
          class="m-1 rounded-lg hover:text-gray-500 hover:transition-all hover:duration-300 dark:text-white"
        >
          ABOUT
        </RouterLink>
      </li>
    </ul>

    <div>
      <hr class="border-1 my-4 border-gray-500 sm:w-4/12 mx-auto" />
    </div>
  </div>
</template>
<script setup>
import router from "../router";

const route = router.currentRoute.value.path;
</script>
