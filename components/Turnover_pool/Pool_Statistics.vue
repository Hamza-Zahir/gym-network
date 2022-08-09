<template>
  <div class="Pool_Statistics fw-600">
    <div class="head d-lg-flex justify-content-between">
      <div class="d-sm-flex">
        <div class="Turnover_progress m-2">
          <span class="circle mx-2 rounded-circle"></span>Turnover progress
        </div>
        <div class="Withdraw_barometer m-2">
          <span class="circle mx-2 rounded-circle"></span>Withdraw barometer
        </div>
      </div>
      <div class="times-Box mt-2">
        <div class="d-lg-none">
          <div
            class="btn bg-blueLight border w-100 rounded-10 fw-600"
            @click="showTimesCard = !showTimesCard"
          >
            {{ timeSelected }}
            <b-icon v-if="!showTimesCard" to="chevron-down"></b-icon>
            <b-icon v-if="showTimesCard" to="chevron-up"></b-icon>
          </div>

          <ul
            v-if="showTimesCard"
            class="sm p-0 m-0 w-100 text-center bg-light d-lg-none"
          >
            <li
              v-for="time in times"
              :key="time"
              @click="
                () => {
                  timeSelected = time;
                  showTimesCard = !showTimesCard;
                }
              "
              :class="timeSelected == time ? 'd-none' : ''"
              class="py-2 mb-2 border-top cp"
            >
              {{ time }}
            </li>
          </ul>
        </div>
        <ul class="p-0 m-0 d-none d-lg-flex">
          <li
            v-for="(time, i) in times"
            :key="`time-${i}`"
            @click="
              () => {
                timeSelected = time;
                showTimesCard = !showTimesCard;
              }
            "
            :class="timeSelected == time ? 'bg-blueLight' : ''"
            class="mx-2 px-2 py-1 cp"
          >
            {{ time }}
          </li>
          <li class="border mx-2 px-2 py-1 d-none d-xl-block cp">
            Select date
          </li>
          <li
            class="mx-2 px-2 py-1 d-none d-xl-block fw-bold text-secondary cp"
          >
            . . .
          </li>
        </ul>
      </div>
    </div>
    <div class="img mt-3">
      <img
        src="~/assets/images/schematicDiagram_sm.png"
        alt=""
        class="w-100 d-sm-none"
      />
      <img
        src="~/assets/images/schematicDiagram_bg.png"
        alt=""
        class="w-100 d-none d-sm-block"
      />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showTimesCard: false,
      timeSelected: "Hour",
      times: ["Hour", "Day", "Week", "Month", "Year", "All time"],
    };
  },
};
</script>

<style lang="scss" scoped>
.Pool_Statistics {
  .circle {
    width: 10px;
    height: 10px;
    display: inline-block;
  }
  .Turnover_progress {
    span {
      background: #aad7ff;
    }
  }
  .Withdraw_barometer {
    span {
      background: #e0aefd;
    }
  }
  li {
    list-style: none;
  }
  .bg-blueLight {
    background: #edf0f4;
  }
  .times-Box {
    position: relative;
    ul.sm {
      position: absolute;
      top: 100%;
      left: 0;
      right: 0;
    }
  }
}
</style>
