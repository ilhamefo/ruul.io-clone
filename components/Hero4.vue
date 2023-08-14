<script setup>

const activeCard = ref("talent");

const heroData = ref({
  title: "WORK SOLUTIONS FOR TODAY",
  header: "Remedies for the new work landscape",
  description:
    "Discover our smart worktech solutions and products designed to future-proof your work, and meet today's needs with ease.",
  icon: "hero2-icon.svg",
  cards: [
    {
      id: "talent",
      cards: [
        {
          icon: "hero-4-icon-1.svg",
          title: "Global Invoicing",
          description:
            "Invoice your clients across 120 countries compliantly and get paid without having to set up a legal entity.",
          numberings: [
            "Free account setup",
            "Multi-currency invoicing",
            "Secure payments",
            "Get paid faster",
          ],
          color: "bg-[#F6F8FF]",
          button: "Explore Global Invoicing",
          type: "content",
        },
        {
          background: "bg-[url(/images/hero/background/641054fa62db2bd37e7182da_Group.svg)]",
          type: "background-only",
        },
        {
          background: "bg-[url(/images/hero/background/640acf93ad1bc30895905d85_banking.svg)]",
          type: "background-only",
        },
        
        {
          icon: "icon-payment-collections.svg",
          title: "Payment Collection",
          description:
            "Ensure a seamless, business-friendly checkout for your clients and accelerate your payment process.",
          numberings: [
            "Secure payment processing",
            "Flexible pay-out options",
            "140+ currencies",
            "Get paid within 1 business day",
          ],
          color: "bg-[#F6F8FF]",
          button: "Explore Payment Collection",
          type: "content",
        },
        
        {
          icon: "6409d4cfd9f112449248591b_Frame.svg",
          title: "Banking",
          description:
            "Integrated banking with zero friction. Create a borderless account — save, spend and track easily, from one place.",
          numberings: [
            "Available in 120 countries",
            "Compliance-integrated",
            "Virtual and physical cards",
            "No setup fee",
          ],
          color: "bg-[#F6F8FF]",
          button: "Explore Banking",
          type: "content",
        },
        {
          background: "bg-[url(/images/hero/background/642a8c47272c6ef3f5404661_Group%209.svg)]",
          type: "background-only",
        },
        {
          background: "bg-[url(/images/hero/background/6422b1a5a2692cd52a543461_Frame%209.svg)]",
          type: "background-only",
        },
        {
          icon: "6409d51197d7b9a8303752e2_Group 9 (1).svg",
          title: "Tax Assistance",
          description:
            "Streamline your self-employed tax filing with professional guidance, ensuring accuracy and optimizing earnings.",
          numberings: [
            "Precise calculation & filing",
            "100% online process",
            "Earning maximization",
            "Personalized consultation",
          ],
          color: "bg-[#F6F8FF]",
          button: "Explore Tax Assistance",
          type: "content",
        },
      ],
    },
    {
      id: "business",
      cards: [
        {
          icon: "hero-4-icon-1.svg",
          title: "Agency of Record",
          description:
            "Work with off-payroll talents compliantly, regardless of their location. Save resources by working in a B2B arrangement.",
          numberings: [
            "B2B invoicing",
            "Simplified compliance",
            "Cross-border standardization",
            "Flexible & cost-efficient",
          ],
          color: "bg-[#F6F8FF]",
          type: "content",
          button: "Explore AOR",
        },
        {
          background: "bg-[url(/images/hero/background/6422b0e10ddff80857912863_Frame.svg)]",
          type: "background-only",
        },
        {
          background: "bg-[url(/images/hero/background/6422b16912f69642acac6967_Frame%208.svg)]",
          type: "background-only",
        },
        {
          icon: "234.svg",
          title: "Payments",
          description:
            "Pay via credit card or bank transfer in any currency. Manage payments to your talents on a single platform.",
          numberings: [
            "Mass pay-out",
            "Compliant",
            "140+ currency options",
            "Seamless & secure",
          ],
          color: "bg-[#F6F8FF]",
          type: "content",
          button: "Explore Payments",
        },
        {
          icon: "6409d4cfd9f112449248591b_Frame.svg",
          title: "Talent Management",
          description:
            "Leverage Ruul's integrated solutions to manage onboarding and payments of your global talents on a single platform.",
          numberings: [
            "Fast onboarding",
            "Background checks",
            "Global payments",
            "Regulatory compliance",
          ],
          color: "bg-[#F6F8FF]",
          type: "content",
          button: "Explore Talent Management",
        },
        {
          background: "bg-[url(/images/hero/background/6422b1a5a2692cd52a543461_Frame%209.svg)]",
          type: "background-only",
        },
      ],
    },
  ],
  toggle: [
    {
      id: "talent",
      isActive: activeCard.value === "talent",
      title: "For Talents",
    },
    {
      id: "business",
      isActive: activeCard.value === "business",
      title: "For Businesses",
    },
  ],
});


function toggle(id) {
  heroData.value.toggle.forEach((item) => {
    if (item.id === id) {
      item.isActive = true;
      activeCard.value = id;
    } else {
      item.isActive = false;
    }
  });
}
</script>
<template>
  <div
    class="py-[40px] px-[21.25px] md:py-[120px] lg:py-[140px] md:px-[40px] flex flex-col bg-[#FEEECA] text-[#003e39] relative border-b border-[#003e39]"
  >

    <div class="flex items-start justify-between lg:gap-x-14">
      <div class="flex flex-col gap-5 lg:flex-grow-0 lg:gap-6 lg:mb-10">
        <div class="font-medium">{{ heroData.title }}</div>
        <h1
          class="mb-5 text-5xl font-bold md:text-[80px] md:leading-[1.2] lg:text-[48px]"
        >
          {{ heroData.header }}
        </h1>
        <p class="text-[20px] font-light leading-[1.5] my-10">
          {{ heroData.description }}
        </p>

        <div class="flex items-center justify-center">
          <div
            class="bg-[#F6F8FF] p-1 rounded-lg border border-[#003e39] flex items-center justify-center gap-x-1 relative w-full md:w-fit md:rounded-full md:mb-5"
          >
            <button
              v-for="item in heroData.toggle"
              @click="toggle(item.id)"
              class="flex-1 p-2.5 md:px-10 font-semibold text-center transition-colors duration-300 rounded-lg md:rounded-full whitespace-nowrap md:text-lg"
              :class="[item.isActive ? 'bg-[#003e39] text-[#CAFDC6]' : '']"
            >
              {{ item.title }}
            </button>

            <div class="absolute hidden -bottom-5 -right-16 md:flex">
              <IconsArrow />
            </div>
          </div>
        </div>

        <div class="grid grid-cols-1 gap-10 lg:grid-cols-2">
          <CardLarge
            :data="
              heroData.cards.find((cardData) => cardData.id === activeCard)
                .cards
            "
          />
        </div>
      </div>
    </div>
  </div>
</template>
