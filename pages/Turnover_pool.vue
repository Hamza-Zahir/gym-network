<template>
  <div class="col-md-11 mx-auto pb-5 mb-5">
    <Header />
    <div class="p-2 Turnover_pool">
      <h1 class="mt-3">Turnover pool</h1>
      <div class="Navbar fw-600">
        <nuxt-link to="/Turnover_pool" class="text-dark link mx-3"
          >Turnover pools</nuxt-link
        >
        <nuxt-link to="/" class="text-dark link mx-3"
          >Tax pools (1mo)</nuxt-link
        >
        <nuxt-link to="/" class="text-dark link mx-3"
          >Tax pools (6mo)</nuxt-link
        >
      </div>
      <Claimed_box />
      <Turnover_progress />
      <div class="">
        <h1 class="p-2">Pool Statistics</h1>
        <Pool_Statistics />
      </div>
      <div class="">
        <h1 class="p-2">Pools</h1>
        <div class="" v-for="pool in pools" :key="pool.id">
   <Pool_card :poolData ="pool" />

        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Header from "../components/Header.vue";
import Claimed_box from "../components/Turnover_pool/Claimed_box.vue";
import Turnover_progress from "../components/Turnover_pool/Turnover_progress.vue";
import Pool_Statistics from "../components/Turnover_pool/Pool_Statistics.vue";
import Pool_card from "../components/Turnover_pool/Pool_card.vue";

const pools = [
  {
    id:1,
    img1: require("../assets/images/logo.png"),
    img2: require("../assets/images/bnb.png"),
    qualification: "200.000",
    rewards: 0.5,
    participants: 68,
    status: "Active",
    Vault_contribution:12229.89,
    Single_contribution:12229.89,
    Farming_contribution:12229.89,
     Miner_sales_contribution:12229.89,
    Land_sales_contribution:12229.89,
    Maintainance_contribution:12229.89,
  },
    {
    id:2,
    img1: require("../assets/images/logo.png"),
    img2: require("../assets/images/bnb.png"),
    qualification: "200.000",
    rewards: 0.5,
    participants: 68,
    status: "Pending",

  },
    {
    id:3,
    img1: require("../assets/images/logo.png"),
    img2: require("../assets/images/bnb.png"),
    qualification: "200.000",
    rewards: 0.5,
    participants: 68,
    status: "Pending",

  },
   {
    id:4,
    img1: require("../assets/images/logo.png"),
    img2: require("../assets/images/bnb.png"),
    qualification: "10.000.000",
    rewards: 0.5,
    participants: 68,
    status: "Pending",

  },
  {
    id:5,
    img1: require("../assets/images/logo.png"),
    img2: require("../assets/images/bnb.png"),
    qualification: "20.000.000",
    rewards: 1,
    participants: 68,
    status: "Pending",

  },
  ];
export default {
  components: { Header, Claimed_box, Turnover_progress, Pool_Statistics, Pool_card },
data(){
  return{
    pools,
  }
}

};
</script>
<style lang="scss" scoped>
.Turnover_pool {
  a.nuxt-link-exact-active {
    border-bottom: 2px solid black;
    font-weight: bold;
  }
  .Navbar {
    display: flex;
    flex-wrap: nowrap;
    width: 100%;
    overflow: scroll;
    &::-webkit-scrollbar {
      display: none;
    }

    .link {
      min-width: fit-content;
    }
  }
}
</style>
