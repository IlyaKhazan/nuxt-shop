<template>
  <button class="filterButton">{{ title }}</button>
</template>

<script>
export default {
  name: "FilterButton",
  props: {
    title: {
      type: String,
      default: "По умолчанию ^",
    },
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss">
.filterButton {
  width: 122px;
  height: 36px;
  font-size: 12px;
  background: #fffefb;
  color: #b4b4b4;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  border: none;
}
</style>
