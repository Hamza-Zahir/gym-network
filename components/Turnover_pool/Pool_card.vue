<template>
  <div class="p-3 py-2 bg-light rounded-10 my-3">
    <div class="d-md-flex align-items-center">
      <h3 class="col-md-3">Pool {{ poolData.id }}</h3>
      <div class="d-md-flex col text-md-center">
        <div class="d-sm-flex col">
          <div class="py-2 col">
            <span class="text-secondary">Qualification </span><br />

            <span class="fw-bold">${{ poolData.qualification }}</span>
          </div>
          <div class="border d-sm-none"></div>
          <div class="py-2 col">
            <span class="text-secondary"> Rewards <br /></span>
            <span class="fw-bold">{{ poolData.rewards }}%</span>
          </div>
        </div>
        <div class="border d-md-none"></div>
        <div class="d-sm-flex col">
          <div class="py-2 col">
            <span class="text-secondary"> Participants <br /></span>
            <span class="fw-bold">{{ poolData.participants }}</span>
          </div>
          <div class="border d-sm-none"></div>
          <div class="py-2 col">
            <span class="text-secondary"> Status <br /></span>
            <span
              class="fw-600 rounded-10 d-inline-block p-2 mt-2"
              :class="
                poolData.status == 'Active' ? 'bg_success' : 'bg_secondary'
              "
              >{{ poolData.status }}</span
            >
          </div>
        </div>
      </div>
    </div>
    <div class="text-end p-2 py-1">
      <b-icon
        v-if="!expansion"
        icon="chevron-down"
        class="h4 m-0"
        @click="expansion = !expansion"
      ></b-icon>
      <b-icon
        v-if="expansion"
        icon="chevron-up"
        class="h4 m-0"
        @click="expansion = !expansion"
      ></b-icon>
    </div>

    <div v-if="expansion" class="">
      <div
        class="bg_grayLight rounded-10 p-3 my-2 d-md-flex align-items-center"
      >
        <div class="d-none d-sm-block col-md-3">
          <img :src="poolData.img1" alt="" />
          <span class="fw-bold">Gymnet</span>
        </div>
        <div class="d-sm-flex justify-content-between col">
          <div class="d-flex my-2">
            <span class="col-3 d-sm-none">
              <img :src="poolData.img1" alt=""
            /></span>
            <div class="mx-sm-2 col">
              <span class="fs-14"> Vault contribution</span> <br />
              <span class="fw-bold">{{ poolData.Vault_contribution }}</span>
            </div>
          </div>
          <div class="border d-sm-none"></div>
          <div class="my-2 d-flex">
            <span class="col-3 d-sm-none"></span>
            <div class="mx-sm-2 col">
              <span class="fs-14"> Single contribution </span><br />
              <span class="fw-bold">{{ poolData.Single_contribution }}</span>
            </div>
          </div>
          <div class="border d-sm-none"></div>
          <div class="my-2 d-flex">
            <span class="col-3 d-sm-none"></span>
            <div class="mx-sm-2 col">
              <span class="fs-14"> Farming contribution</span> <br />
              <span class="fw-bold">{{ poolData.Farming_contribution }}</span>
            </div>
          </div>
        </div>
      </div>

      <div
        class="bg_grayLight rounded-10 p-3 my-2 d-md-flex align-items-center"
      >
        <div class="d-none d-sm-block col-md-3">
          <img :src="poolData.img2" alt="" />
          <span class="fw-bold">BNB</span>
        </div>
        <div class="d-sm-flex justify-content-between col">
          <div class="d-flex my-2">
            <span class="col-3 d-sm-none">
              <img :src="poolData.img2" alt=""
            /></span>
            <div class="mx-sm-2 col">
              <span class="fs-14"> Miner sales contribution</span> <br />
              <span class="fw-bold">{{
                poolData.Miner_sales_contribution
              }}</span>
            </div>
          </div>
          <div class="border d-sm-none"></div>
          <div class="my-2 d-flex">
            <span class="col-3 d-sm-none"></span>
            <div class="col mx-sm-2">
              <span class="fs-14"> Land sales contribution</span> <br />
              <span class="fw-bold">{{
                poolData.Land_sales_contribution
              }}</span>
            </div>
          </div>
          <div class="border d-sm-none"></div>
          <div class="my-2 d-flex">
            <span class="col-3 d-sm-none"></span>
            <div class="col mx-sm-2">
              <span class="fs-14"> Maintainance contribution</span> <br />
              <span class="fw-bold">{{
                poolData.Maintainance_contribution
              }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      expansion: false,
    };
  },
  props: {
    poolData: {
      required: true,
      type: Object,
    },
  },
};
</script>

<style lang="scss" scoped>
.bg_success {
  background: #b1f1b8;
}
.bg_secondary {
  background: #dee5ed;
}
.bg_grayLight {
  background: #edf1ff;
}
img {
  max-width: 40px;
}
</style>
