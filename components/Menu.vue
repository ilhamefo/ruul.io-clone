<script setup>
const currentOpenedMenu = ref(null);

const menuStates = ref({
  menu1: ref(false),
  menu2: ref(false),
  menu3: ref(false),
  menu4: ref(false),
});

const toggleMenu = (menuKey) => {
  for (const key in menuStates.value) {
    if (key !== menuKey) {
      menuStates.value[key] = false;
    }
  }

  menuStates.value[menuKey] = !menuStates.value[menuKey];
};

onMounted(() => {
  // console.log(menuStates);
});
</script>
<template>
  <div
    class="absolute lg:static top-[110px] left-0 bg-[#F6F8FF] lg:bg-transparent flex flex-col lg:flex-row lg:w-fit w-full"
  >
    <div
      class="grid grid-cols-1 lg:flex gap-2 w-full px-5 py-5 lg:py-0 border-b lg:border-0 border-[#003e39] xl:relative"
    >
      <div class="relative lg:static">
        <button
          @click="toggleMenu('menu1')"
          class="flex items-center justify-between w-full px-3 py-3 rounded-lg"
        >
          <div class="text-xl lg:text-base whitespace-nowrap">For Talents</div>
          <NuxtImg
            src="/images/chevron.svg"
            format="webp"
            class="transition-all duration-300"
            :class="[menuStates.menu1 ? '-rotate-180' : '']"
          ></NuxtImg>
        </button>

        <Transition
          enter-from-class="translate-y-[10%] opacity-0"
          enter-active-class="transition duration-200"
        >
          <div
            class="right-0 lg:absolute lg:w-screen lg:px-10 top-28 xl:top-20 xl:w-[830px]"
            v-if="menuStates.menu1"
          >
            <MenuModalTalents v-if="menuStates.menu1"></MenuModalTalents>
          </div>
        </Transition>
      </div>

      <div class="relative lg:static">
        <button
          @click="toggleMenu('menu2')"
          class="flex items-center justify-between w-full px-3 py-3 rounded-lg"
        >
          <div class="text-xl lg:text-base whitespace-nowrap">For Business</div>
          <NuxtImg
            src="/images/chevron.svg"
            format="webp"
            class="transition-all duration-300"
            :class="[menuStates.menu2 ? '-rotate-180' : '']"
          ></NuxtImg>
        </button>

        <Transition
          enter-from-class="translate-y-[10%] opacity-0"
          enter-active-class="transition duration-200"
        >
          <div
            class="right-0 lg:absolute lg:w-screen lg:px-10 top-28 xl:top-20 xl:w-[830px]"
            v-if="menuStates.menu2"
          >
            <MenuModalBusiness v-if="menuStates.menu2"></MenuModalBusiness>
          </div>
        </Transition>
      </div>

      <div class="flex items-center justify-between px-3 py-3 rounded-lg">
        <div class="text-xl lg:text-base whitespace-nowrap">Pricing</div>
      </div>

      <div class="relative lg:static">
        <button
          @click="toggleMenu('menu3')"
          class="flex items-center justify-between w-full px-3 py-3 rounded-lg"
        >
          <div class="text-xl lg:text-base whitespace-nowrap">Collaborate</div>
          <NuxtImg
            src="/images/chevron.svg"
            format="webp"
            class="transition-all duration-300"
            :class="[menuStates.menu3 ? '-rotate-180' : '']"
          ></NuxtImg>
        </button>

        <Transition
          enter-from-class="translate-y-[10%] opacity-0"
          enter-active-class="transition duration-200"
        >
          <div
            class="right-0 lg:absolute lg:w-screen lg:px-10 top-28 xl:top-20 xl:w-[830px]"
            v-if="menuStates.menu3"
          >
            <MenuModalCollaborate></MenuModalCollaborate>
          </div>
        </Transition>
      </div>

      <div class="relative lg:static">
        <button
          @click="toggleMenu('menu4')"
          class="flex items-center justify-between w-full px-3 py-3 rounded-lg"
        >
          <div class="text-xl lg:text-base whitespace-nowrap">Resources</div>
          <NuxtImg
            src="/images/chevron.svg"
            format="webp"
            class="transition-all duration-300"
            :class="[menuStates.menu4 ? '-rotate-180' : '']"
          ></NuxtImg>
        </button>

        <Transition
          enter-from-class="translate-y-[10%] opacity-0"
          enter-active-class="transition duration-200"
        >
          <div
            class="right-0 lg:absolute lg:w-screen lg:px-10 top-28 xl:top-20 xl:w-[830px]"
            v-if="menuStates.menu4"
          >
            <MenuModalResource></MenuModalResource>
          </div>
        </Transition>
      </div>
    </div>
    <div
      class="bg-[#FEEECA] lg:bg-transparent lg:border-0 grid grid-cols-1 md:grid-cols-2 gap-5 lg:gap-3 p-5 lg:p-0 border-b border-[#003e39] lg:place-items-center lg:flex lg:items-center lg:w-min"
    >
      <ButtonPrimary> Login </ButtonPrimary>
      <ButtonSecondary> Sign Up </ButtonSecondary>
    </div>
  </div>
</template>
