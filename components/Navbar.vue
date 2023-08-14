<script setup>
useHead({
  title: "Ruul I Worktech Solutions for Modern and Global Work",
});
const showMenu = ref(false);

function toggleMenu() {
  showMenu.value = !showMenu.value;
}
</script>
<template>
  <nav
    class="flex items-center justify-between px-5 md:px-10 py-7 border-b border-[#003e39] relative z-30 bg-[#C9FEC6] w-full"
  >
    <NuxtImg src="/images/ruul_logo.svg" format="webp" class="" />
    <button
      @click="toggleMenu()"
      class="shadow-[5px_5px_0px_0px_rgb(0,62,57)] bg-[#F6F8FF] rounded-md p-[14px] ring-1 ring-[#003e39] flex lg:hidden"
    >
      <NuxtImg src="/images/menu.svg" format="webp"></NuxtImg>
    </button>

    <Menu class="hidden lg:flex" />
  </nav>

  <Transition
    enter-from-class="translate-y-[-150%] opacity-0"
    enter-active-class="transition duration-300"
    leave-to-class="translate-y-[-150%] opacity-0"
    leave-active-class="transition duration-300"
  >
    <Menu v-if="showMenu" class="z-20 flex lg:hidden" />
  </Transition>
</template>
