<template>
  <!-- container-custom -->
  <div
    class="bg-[#C9FEC6] min-h-screen font-strawford text-[#003e39] flex flex-col items-center z-auto antialiased "
  >
    <div class="relative w-full">
      <Navbar />

      <Hero />

      <Hero2 />

      <Hero3 />

      <Hero4 />

      <Hero5 />

      <Footer />

      <LazyCookies v-if="false" />
    </div>
  </div>
</template>
