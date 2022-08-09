<template>
  <div class="sidebar p-3 fw-600">
    <div class="">
      <div class="h5 d-flex align-items-center text-light">
        <span class="logo">
          <img src="~/assets/images/logo.png" alt="" class="" />
        </span>
        <span class="me-4  ms-2">Gym Network</span>
        <b-icon
          icon="chevron-double-left"
          class="h6 m-0 mt-1 "
        >
        </b-icon>
      </div>
    </div>
    <div class="py-2">
      <div v-for="link in links" :key="link.title" class="my-3">
        <nuxt-link
          :to="`/${link.link}`"
          class="p-2 rounded d-block link text-light"
        >
          <b-icon :icon="link.icon" class="m-0"></b-icon>

          <span class="me-4 ps-2">{{ link.title }}</span>
        </nuxt-link>
      </div>

      <div
        class="d-flex border-top border-secondary pt-3 ps-3 text-light"
      >
        <b-icon icon="link-45deg" class="h4 m-0 mt-1 me-2"></b-icon>
        <div class="d-flex flex-column text-center">
          <div class="">Referral Link</div>
          <small class="text-secondary">https:...zgpyy</small>
        </div>

        <b-icon icon="subtract" class="m-0 mt-1 ms-3"></b-icon>
      </div>
      <div class="mt-5">
        <nuxt-link
          to="/Settings"
          class="p-2 my-2 rounded d-block link text-light"
        >
          <b-icon icon="gear" class="m-0"></b-icon>
          <span class="me-4 ms-2">Settings</span>
        </nuxt-link>
        <nuxt-link
          to="/Help_Center"
          class="p-2 my-2 rounded d-block link text-light"
        >
          <b-icon icon="question-circle" class="m-0"></b-icon>

          <span class="me-4 ms-2">Help Center</span>
        </nuxt-link>

        <div
          class="p-2 ps-4 my-2 rounded-10 d-block border text-center text-light "
        >
          <span class="me-4">Dashboard</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const links = [

  {
    icon: "people-fill",
    title: "Career status",
    link: "Career_status",

  },
  {
    icon: "bar-chart-line",
    title: "Partner statistic",
    link: "Partner_statistic",

  },
  {
    icon: "bar-chart-line",
    title: "Vaults income",
    link: "Vaults_income",

  },
  {
    icon: "bar-chart-line",
    title: "Level pool",
    link: "Level_pool",

  },
  {
    icon: "bar-chart-line",
    title: "Single pool income",
    link: "Single_pool_income",

  },
  {
    icon: "bar-chart-line",
    title: "Turnover pool",
    link: "Turnover_pool",

  },
  {
    icon: "box",
    title: "NFT Statistic",
    link: "NFT_Statistic",

  },
  {
    icon: "bar-chart-line",
    title: "Incentives",
    link: "Incentives",

  },
];
export default {
  data() {
    return {
      links,
    };
  },
};
</script>

<style lang="scss" scoped>
.sidebar {
  background: #153151;
  width: fit-content;


  .logo {
    display: inline-block;
    width: 30px;
    height: 30px;

    img {
      width: 100%;
      height: 100%;
    }
  }

  .link.nuxt-link-exact-active {
    background: #e2e2e2;
    color: #153151 !important;
  }
}
</style>
