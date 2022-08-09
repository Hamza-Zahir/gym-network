<template>
  <div class="">
    <div class="box bg-light rounded-10 p-2">
      <h2>
        Turnover progress
        <b-icon icon="info-circle" class="h4 m-0 text-secondary"></b-icon>
      </h2>

      <div class="pools">
        <div v-for="(pool, i) in pools" :key="`pool${i + 1}`" class="pool col">
          <div class="lign"></div>
          <div class="text ms-auto my-2 text-center fw-600">
            pool {{ i + 1 }}
            <div class="text-secondary">{{ pool }}</div>
          </div>
        </div>
      </div>
      <div class="d-md-flex">
        <div class="withdraw px-2 py-3 rounded-10 m-2 col">
          <h5 class="mb-4">
            Withdraw barometer
            <b-icon icon="info-circle" class="h5 m-0 text-secondary"></b-icon>
          </h5>

          <div class="lign rounded-10 mt-3"></div>
          <div class="text-end px-2 my-1">$200.000</div>
        </div>
        <div class="turnover px-2 py-3 rounded-10 m-2 col">
          <div class="d-flex justify-content-between align-items-center">
            <h5>
              50% turnover rule
              <b-icon icon="info-circle" class="h5 m-0 text-secondary"></b-icon>
            </h5>
            <span class="fs-12 text-primary cp" @click="showDetails = !showDetails"
              >View details</span
            >
          </div>

          <div class="lign rounded-10 d-flex mt-3">
            <span class="gren w-50"></span>
            <span class="oringe w-25"></span>
            <span class="secondary w-25"></span>
          </div>
          <div class="text-center px-2 my-1">$200.000</div>
          <div v-if="showDetails" class="detailsCard bg-light rounded-10 p-2">
            <div class="d-flex justify-content-between">
              <h5>50% Turnover rule</h5>
              <b-icon
                icon="x-lg"
                class="cp"
                @click="showDetails = !showDetails"
              ></b-icon>
            </div>
            <div class="fs-14">
              The maximum share each direct can contribute to the required
              turnover is up to 50%
            </div>
            <div class="bg_grey p-2 mt-3 rounded-10">
              <div
                class="head d-flex justify-content-between align-items-center"
              >
                <div class="d-flex align-items-center">
                  <div>
                    <img
                      src="~/assets/images/Ellipse.png"
                      alt=""
                      class="me-1"
                      style="width: 35px"
                    />
                  </div>
                  <div class="fs-14 fw-600">
                    max@mail.com <br />
                    <span class="text-secondary">0x85E7...7340e</span>
                  </div>
                </div>
                <h2 class="text-primary">
                  50%
                  <b-icon
                    icon="info-circle"
                    class="h5 m-0 text-secondary"
                  ></b-icon>
                </h2>
              </div>
              <div class="d-sm-flex d-md-block d-lg-flex ">
                <div class="border rounded-10 p-2 my-2 mx-sm-2 col">
                  <div class="text-secondary py-2">Generated turnover</div>
                  <h2>216k $</h2>
                  <div
                    class="d-flex justify-content-between border-bottom py-2"
                  >
                    <span>Vault</span>
                    <span>125,2k</span>
                  </div>
                  <div
                    class="d-flex justify-content-between border-bottom py-2"
                  >
                    <span>Single pool</span>
                    <span>80,5k</span>
                  </div>
                  <div class="d-flex justify-content-between py-2">
                    <span>Farm</span>
                    <span>20,3k</span>
                  </div>
                </div>

                <div class="border rounded-10 p-2 my-2 mx-sm-2 col">
                  <div class="text-secondary py-2">Qualified turnover</div>
                  <h2>200k $</h2>
                  <div
                    class="d-flex justify-content-between border-bottom py-2"
                  >
                    <span>Vault</span>
                    <span>100k</span>
                  </div>
                  <div
                    class="d-flex justify-content-between border-bottom py-2"
                  >
                    <span>Single pool</span>
                    <span>80k</span>
                  </div>
                  <div class="d-flex justify-content-between py-2">
                    <span>Farm</span>
                    <span>20k</span>
                  </div>
                </div>
              </div>

            </div>
            <div class="mt-3">
                <h4>Other partners</h4>
                <div class="d-flex justify-content-between align-items-center py-2">
                  <span
                   class="fw-600"
                    ><img src="~/assets/images/Ellipse1.png" alt="" />
                    0x85E7...7340e</span
                  >
                  <span class="fw-bold">200k $</span>
                </div>
                <div class="d-flex justify-content-between align-items-center py-2">
                  <span
                  class="fw-600"
                    ><img src="~/assets/images/Ellipse1.png" alt="" />
                    0x85E7...7340e</span
                  >
                  <span class="fw-bold">200k $</span>
                </div>
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
      showDetails: false,
      pools: [200000, 400000, 400000, 500000, 600000],
      currentPool: 290000,
    };
  },
};
</script>
<style lang="scss" scoped>
.fs-12{
  font-size: 12px;
}
.pools {
  display: flex;
  flex-wrap: nowrap;
  width: 100%;
  overflow: scroll;
  position: relative;
  padding-top: 10px;

  &::-webkit-scrollbar {
    display: none;
  }

  .pool {
    min-width: 150px;
  }
  .lign {
    height: 6px;
    margin-left: 2px;
    background: #a8a8a8;
    position: relative;
    z-index: 0;
  }
  .text {
    width: fit-content;
  }
}
.withdraw {
  background: #edf0f4;
  .lign {
    height: 8px;
    background: #e2c3f4;
  }
}

.turnover {
  background: #edf0f4;
  position: relative;
  .lign {
    overflow: hidden;

    span {
      height: 8px;
      display: inline-block;
    }
    .gren {
      background: #b1f1b8;
    }
    .oringe {
      background: #ffc48d;
    }
    .secondary {
      background: #dee5ed;
    }
  }
  .detailsCard {
    position: absolute;
    top: 20px;
    left: 0;
    width: 100%;
    z-index: 99;
    box-shadow: 0px 0px 10px 0px #7c7c7c;
    .bg_grey {
      background: #edf0f4;
    }
  }
}
</style>
