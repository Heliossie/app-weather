<template>
  <l-map ref="myMap" @ready="doSomethingOnReady()"></l-map>
</template>

<script>
export default {
  mounted() {
    this.nextTick(() => {
      this.$refs.myMap.mapObject.ANY_LEAFLET_MAP_METHOD();
    });
  },
  methods: {
    doSomethingOnReady() {
      this.map = this.$refs.myMap.mapObject;
    },
  },
};
</script>

<style>
</style>