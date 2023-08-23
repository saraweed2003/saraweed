<template>
  <div :class="isDarkMode ? 'dark' : ''" class="bg">
    <div
      class="bg-white/80 min-h-screen sm:p-10 p-5 flex flex-col justify-center dark:bg-[#0e1013]/80 duration-500 transition-all ease-in-out"
    >
      <button @click="toggleDarkMode" class="animate-pulse">
        <ModeToggler
          :class="isDarkMode ? 'fa-solid fa-sun' : 'fa-solid fa-moon'"
        />
      </button>
      <CardHeader />
      <RouterView />
      <CardFooter />
    </div>
  </div>
</template>

<script setup>
import ModeToggler from "./components/ModeToggler.vue";
import CardHeader from "./components/CardHeader.vue";
import CardFooter from "./components/CardFooter.vue";

import { ref, onMounted } from "vue";

const isDarkMode = ref(false);

onMounted(() => {
  if (
    localStorage.theme === "dark" ||
    (!("theme" in localStorage) &&
      window.matchMedia("(prefers-color-scheme: dark)").matches)
  ) {
    isDarkMode.value = true;
  } else {
    isDarkMode.value = false;
  }
});

const toggleDarkMode = () => {
  if (isDarkMode.value) {
    localStorage.theme = "light";
    isDarkMode.value = false;
  } else {
    localStorage.theme = "dark";
    isDarkMode.value = true;
  }
};
</script>

<style>
.bg {
  background-image: url("https://img.freepik.com/premium-photo/green-purple-shades-cannabis-plants-leaves_124507-52281.jpg");
  background-size: cover; /* ทำให้ภาพปรับขนาดเพื่อเต็มจอ */
  background-position: center; /* จัดตำแหน่งภาพให้อยู่กลาง */
  background-repeat: no-repeat; /* ไม่ให้ภาพเติมซ้ำ */
  
}
</style>