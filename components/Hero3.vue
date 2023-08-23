<script setup>
const heroData = ref({
  title: "The New Way Of Work",
  header: "Tailored for the new economy",
  description:
    "Ruul's technology caters to the unique needs of modern talents and businesses. Our mission is empowering agility, autonomy, and compliance for staying ahead in a fast-evolving economy.",
  icon: "hero2-icon.svg",
  cards: [
    {
      icon: "hero2-icon-1.svg",
      title: "For Talents",
      subtitle: "IN 120 COUNTRIES",
      description:
        "Empower your independent career with financial autonomy. Work with any business worldwide, effortlessly and compliantly.",
      numberings: [
        "Global Invoicing",
        "Payment Collection",
        "Borderless Banking",
        "Tax Assistance",
      ],
      color: "bg-[#F6F8FF]",
      button: "Explore Payments",
      footer: "50k+ talents use Ruul"
    },
    {
      icon: "hero2-icon-1.svg",
      title: "For Businesses",
      subtitle: "IN 120 COUNTRIES",
      description:
        "Stay agile by working with talents all around the world. Streamline your talent operations with an easy attachment and detachment protocol.",
      numberings: [
        "Agency of Record",
        "Multi-currency Payments",
        "Global Payroll",
        "Talent Management",
      ],
      color: "bg-[#fec1aa]",
      button: "Explore Business Solutions",
      footer: "10k+ businesses use Ruul"

    },
  ],
});
</script>
<template>
  <div class="flex items-center justify-center bg-[#003e39]">

  <div
    class="py-[40px] px-[21.25px] md:py-[120px] lg:py-[140px] md:px-[40px] flex flex-col  text-[#cafdc6] relative container"
  >
    <div class="flex items-start justify-between lg:gap-x-14">
      <div class="flex flex-col gap-5 lg:flex-grow-0 lg:gap-6 lg:mb-10">
        <div class="font-medium">{{ heroData.title }}</div>
        <h1
          class="mb-5 text-5xl font-bold md:text-[80px] md:leading-[1.2] lg:text-[48px]"
        >
          {{ heroData.header }}
        </h1>
        <p class="text-[20px] font-light leading-[1.5] my-10 ">
          {{ heroData.description }}
        </p>

        <div class="grid grid-cols-1 gap-10 md:grid-cols-2">
          <Card :data="heroData.cards" />
        </div>
      </div>
    </div>
  </div>
</div>

</template>
