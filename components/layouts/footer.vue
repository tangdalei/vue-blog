<template>
  <footer :class="{'mobile': mobileLayout}">
    <div
      class="container clearfix font-futura">
      <span v-if="mobileLayout">©{{new Date().getFullYear()}}</span>
      <span v-else>BASE ON NUXT + NODE + MONGODB</span>
      <span> BY
        <nuxt-link to="/about">{{ user.name }}</nuxt-link>
      </span>
      
    </div>
  </footer>
</template>
<script>
export default {
  name: 'footer',

  computed: {
    mobileLayout () {
      return this.$store.state.options.mobileLayout
    },

    option () {
      return this.$store.state.options.option
    },

    user () {
      return this.$store.state.options.adminInfo
    }
  }
}
</script>

<style scoped lang="scss">

@import '~assets/scss/variable.scss';

footer {
  margin-top: $normal-pad;
  height: $header-height;
  line-height: $header-height;
  background: $module-bg;

  >.container {
    text-align: center;
  }

  &.mobile {
    margin-top: 0;

    >.container {
      width: 100%;
    }
  }
}
</style>

