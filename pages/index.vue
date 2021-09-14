<template>
  <div class="inner">
    <div class="flex-display">
      <CompanyDescription :details="descriptionDetails" @tabs="toggleTabs" />
      <div
        id="container02"
        data-scroll-id="work"
        data-scroll-behavior="default"
        data-scroll-offset="0"
        class="container default full screen"
      >
        <div class="wrapper">
          <div class="inner">
            <CompanyGallery v-if="activeTab == 0 && !confirmTab" />
            <CompanyProducts v-if="activeTab == 1 && !confirmTab" />
            <CommonConfirm v-if="confirmTab" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { defineComponent, reactive, ref } from "@nuxtjs/composition-api";

export default defineComponent({
  layout: "company",
  setup() {
    let activeTab = ref(0);
    let confirmTab = ref(0);
    let descriptionDetails = reactive({
      title: "Event Fantasy",
      description: "Estd 2019, Let's take this Celebration to the next level!!",
      buttonLabel: "Book Us",
    });

    const toggleTabs = function () {
      descriptionDetails.buttonLabel =
        descriptionDetails.buttonLabel == "Book Us" ? "Gallery" : "Book Us";
      activeTab.value = !activeTab.value;
    };

    return {
      activeTab,
      confirmTab,
      descriptionDetails,
      toggleTabs,
    };
  },
});
</script>

