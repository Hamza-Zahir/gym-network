<template>
  <div class="chart-div">
    <LineChart :chartdata="chartdata" :options="options" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      chartdata: {
        labels: [
          "1.00",
          "2.00",
          "3.00",
          "4.00",
          "5.00",
          "6.00",
          "7.00",
          "8.00",
          "9.00",
          "10.00",
          "11.00",
          "12.00",
          "13.00",
          "14.00",
          "15.00",
          "16.00",
          "17.00",
          "18.00",
          "19.00",
          "20.00",
          "21.00",
          "22.00",
          "23.00",
          "00.00",
          "1.00",
          "2.00",
          "3.00",
        ],
        datasets: [
          {
            data: [
              5919384, 7115756, 6973242, 5002193, 4665252, 5470037, 6429470,
              4455900, 4535285, 5628432, 6900845, 5900845, 6900845, 5484921,
              4175670, 5324907, 6189341, 7393735, 7380303, 6797059, 6043755,
              3770137, 2724042, 4798495, 4351664, 6907783, 6900000,
            ],
            borderColor: "#e0aefd",
            bodyFillBackground: "red",
            fill: true,
            backgroundColor: "#ff00aa05",
            label: "WB",
            pointRadius: 5,
            pointBackgroundColor: "transparent",
            pointBorderColor: "transparent",
          },
          {
            data: [
              3919384, 2115756, 4973242, 4002193, 3665252, 6470037, 7429470,
              5455900, 4535285, 2628432, 5900845, 4900845, 4900845, 4484921,
              5175670, 4924907, 5189341, 5393735, 7380303, 3797059, 5043755,
              2770137, 3724042, 7798495, 6351664, 5907783, 5900000,
            ],
            borderColor: "#aad7ff",
            fill: true,
            backgroundColor: "#05b7fd07",
            label: "TP",
            pointRadius: 5,
            pointBackgroundColor: "transparent",
            pointBorderColor: "transparent",
          },
        ],
      },
      options: {
        legend: { display: false },
        maintainAspectRatio: false,
        responsive: true,
        tooltips: {
          backgroundColor: "#ffffff",
          titleFontColor: "#7c7c7c",
          bodyFontColor: "black",
          position: "nearest",
          mode: "nearest",
          intersect: 0,
          bodySpacing: 4,
          xPadding: 15,
          yPadding: 8,
        },
      },
    };
  },
};
</script>
