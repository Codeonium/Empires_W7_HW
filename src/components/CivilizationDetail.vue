<template lang="html">
  <div id="selected_civilization">
    <h2> {{selectedCivilization.name}} </h2>

</div>
</template>

<script>

export default {
  name: "civilization-detail",
  props: ['selectedCivilization'],
};
</script>

<style lang="css" scoped>
.lrg-flag {
  height: 100px;
}
</style>
