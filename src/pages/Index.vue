<template lang="pug">
  Layout(:isPage="true")
    h1 U.S. states
    p.text
      | In the United States, a state is a constituent political entity, of which there are currently 50. Bound together in a political union, each state holds governmental jurisdiction over a separate and defined geographic territory and shares its sovereignty with the federal government. Due to this shared sovereignty, Americans are citizens both of the federal republic and of the state in which they reside.
    hr
</template>

<script>
export default {
  metaInfo: {
    title: "GBlog",
  },
};
</script>

<style lang="scss">
.text {
  margin: 20px 0;
}
</style>
