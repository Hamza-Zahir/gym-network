<template>
  <div class="">
    <div
      v-if="!CurrentAccount || ChainId != 97"
      class="btn btn-primary"
      :class="CurrentAccount && ChainId != 97 ? 'btn-warning' : ''"
      @click="
        () => {
          connectMetamask();
        }
      "
    >
      {{ CurrentAccount && ChainId != 97 ? "network erore" : " Conect Wallet" }}
    </div>
    <div
      v-if="CurrentAccount || ChainId !== 97"
      class="wallet d-flex align-items-center"
    >
      <span class="me-1"
        ><img src="../assets/images/Ellipse.png" alt=""
      /></span>

      <span class="account">{{
        `${CurrentAccount.slice(0, 3)}...${CurrentAccount.slice(
          CurrentAccount.length - 3
        )}`
      }}</span>
    </div>
  </div>
</template>
<script>
import { mapActions, mapGetters } from "vuex";

export default {
  data() {
    return {
      amountTokens: "",
    };
  },
  computed: {
    ...mapGetters(["CurrentAccount"]),
    ...mapGetters(["ChainId"]),
  },
  mounted() {
    this.checkWalletIsConnected();
  },
  methods: {
    ...mapActions(["checkWalletIsConnected"]),
    ...mapActions(["connectMetamask"]),
  },
};
</script>
<style lang="scss" scoped>
.wallet {
  .account {
    font-size: 14px;
  }
  img {
    width: 30px;
  }
  @media (min-width: 425px) {
    .account {
      font-size: 16px;
    }
    img {
      width: 35px;
    }
  }
}
</style>
