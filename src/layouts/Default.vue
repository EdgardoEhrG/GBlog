<template lang="pug">
  div.layout
    header.header
      strong
        g-link(to="/") {{ $static.metaData.siteName }}
      nav.nav
        g-link.nav__link(to="/") Home
        g-link.nav__link(to="/about") About
        g-link.nav__link(to="/posts") Posts
    transition(name="fade" appear)
      main
        slot
        LatestPost
</template>

<script>
import LatestPost from '../components/LatestPost'

export default {
  components: {
    LatestPost
  }
}
</script>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
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
