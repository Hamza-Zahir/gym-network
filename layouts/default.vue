<template>
  <div class="app-default">
    <div
      class="Sidebar"
      @click="
        () => {
          setShowSidbar(!showSidbar);
        }
      "
      :style="showSidbar ? 'left: 0%' : 'left: -100%'"
    >
      <Sidebar />
    </div>

    <div class="page col">
      <Nuxt />
    </div>
  </div>
</template>
<script>
import { mapGetters, mapMutations } from "vuex";
export default {
  data() {
    return {};
  },
  computed: {
    ...mapGetters(["showSidbar"]),
  },
  methods: {
    ...mapMutations(["setShowSidbar"]),
  },
};
</script>
<style lang="scss" scoped>
.app-default {
  max-width: 1500px;
  margin: 0 auto;
  overflow: hidden;
  position: relative;
  min-height: 200vh;

  .Sidebar {
    min-width: 270px;
    position: absolute;
    top: 0;
    z-index: 999;
    transition: all 1s ease;
  }
}
</style>
