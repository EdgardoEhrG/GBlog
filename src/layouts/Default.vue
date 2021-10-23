<template lang="pug">
  div.layout
    header.header
      strong
        g-link(to="/") GBlog
      nav.nav
        g-link.nav__link(to="/") Home
        g-link.nav__link(to="/posts") Posts
    transition(name="fade" appear)
      main
        slot
        LatestPost(v-show="isPage")
</template>

<script>
import LatestPost from "../components/LatestPost";

export default {
  props: {
    isPage: { type: Boolean, required: false },
  },
  components: {
    LatestPost,
  },
};
</script>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style lang="scss">
@import "../assets/styles/main.scss";

.layout {
  max-width: 760px;

  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  margin-bottom: 30px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}

.fade-enter-active {
  transition: 1s ease opacity;
}

.fade-enter {
  opacity: 0;
}
</style>
