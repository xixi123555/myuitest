<template>
  <div class="select-wrapper">
      <my-input></my-input>
      <div class="select-options">
          <slot></slot>
      </div>
  </div>
</template>
<script>
import MyInput from "./myInput";
export default {
  name: "MySelect",
  props: {},
  components: {
    MyInput,
  },
  data() {
    return {};
  },
  computed: {},
  methods: {},
};
</script>
<style lang="stylus" scoped>
.select-wrapper
    .my-select
        width: 100%
        height: 32px
        line-height: 32px
        border: none
        outline: none
        background: none
    .select-options
        width 100px

</style>