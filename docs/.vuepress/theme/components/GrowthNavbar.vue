<template>
  <div class="nav-links hide-md">
    <div class="nav-item growth">
      <div class="btn-group">
        <a :href="gitHubUrl" class="btn btn-sm"
          ><i class="fa fa-star"></i> GitHub Stars <span>|</span>
          <span class="stars">{{ stars }}</span></a
        >
        <a href="https://www.patreon.com/openupm" class="btn btn-sm"
          ><i class="fab fa-patreon"></i> {{ $t("donate") }}</a
        >
      </div>
    </div>
  </div>
</template>

<script>
import util from "@root/docs/.vuepress/util";

export default {
  components: {},
  data() {
    return {};
  },
  computed: {
    stars() {
      return this.$store.getters.siteInfo.stars || "...";
    },
    gitHubUrl() {
      if (this.$site.themeConfig.region == "cn")
        return "https://github.com/openupm/openupm/blob/master/README.zh-cn.md";
      else return "https://github.com/openupm/openupm";
    }
  }
};
</script>

<style lang="stylus">
.nav-links
  .nav-item
    &.growth
      margin-left 0.4rem
      display inline-block
      .btn
        font-size 12px
        padding-top 0
        padding-bottom 0
        height 1.45rem

      .stars
        display inline-block
        min-width 1rem
</style>
