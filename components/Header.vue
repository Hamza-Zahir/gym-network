<template>
  <div class="m-0 d-flex justify-content-between p-2">
    <h3 class="m-0 p-0 cp d-flex align-items-center" @click="setShowSidbar(!showSidbar)">
      <span class="bluelogo rounded-circle me-2 ">
        <img
          src="~/assets/images/bluelogo.png"
          class="rounded-circle"
          alt=""
        />
      </span>
      <span class="d-none d-sm-inline">Gym Network</span>
    </h3>

    <div class="d-flex align-items-center justify-content-around">
      <span class="me-2">
        <b-icon icon="brightness-low" class="h3 m-0 p-0"></b-icon>
      </span>
      <div class="select fw-600" @click="showLanguages = !showLanguages">
        <span class="p-2"
          >{{ language }}
          <b-icon
            v-if="!showLanguages"
            icon="chevron-down"
            class="m-0 p-0"
          ></b-icon>
          <b-icon
            v-if="showLanguages"
            icon="chevron-up"
            class="m-0 p-0"
          ></b-icon>
        </span>
        <div v-if="showLanguages" class="other_languages text-center px-2">
          <div
            v-for="lang in languages"
            :key="lang"
            @click="language = lang"
            class="border-top py-2"
            :class="language === lang ? '' : 'text-secondary'"
          >
            <span class="">{{ lang }}</span>
          </div>
        </div>
      </div>
      <span
        class="me-2 notification d-flex justify-content-center align-items-center cp border rounded-circle"
        ><b-icon icon="bell" class="h5 m-0 p-0 text-secondary"></b-icon>

        <span class="sup rounded-circle px-1">2</span>
      </span>
      <span
        class="me-2 cp border rounded-circle dots d-flex justify-content-center align-items-center cp border rounded-circle"
      >
        <img src="~/assets/images/Income.png" alt="" />
      </span>
      <div class="me-2"><Wallet_btn /></div>
    </div>
  </div>
</template>
<script>
import { mapGetters, mapMutations } from "vuex";
import Wallet_btn from "./Wallet_btn.vue";
export default {
  data() {
    return {
      CurrentAccount: "0x780c37F286DF1b1309c94828b53f50987635Ad31",
      language: "EN",
      languages: ["EN", "ES", "ID", "JA"],
      showLanguages: false,
    };
  },

  computed: {
    ...mapGetters(["showSidbar"]),
  },
  methods: {
    ...mapMutations(["setShowSidbar"]),
  },
  components: { Wallet_btn },
};
</script>

<style lang="scss" scoped>
.header {
  background: #153151;
}
.notification,
.dots {
  width: 30px;
  height: 30px;
  position: relative;

  .sup {
    position: absolute;
    left: 45%;
    top: 10%;
    background: #f06553ea;
    font-size: 8px;
    color: white;
  }
  @media (min-width: 425px) {
    width: 35px;
    height: 35px;
  }
}
.bluelogo {
  img {
    width: 25px;
    height: 25px;
  }
  @media (min-width: 425px) {
    img {
      width: 35px;
      height: 35px;
    }
  }
}

.select {
  position: relative;
  cursor: pointer;
  .other_languages {
    position: absolute;
    top: calc(100% + 2px);
    left: 0;
    width: 100%;
    background: #f0f0f0;
  }
}
</style>
