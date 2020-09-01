<template>
  <div :class="['input-wrapper',input_wrapper_computed_class]">
    <label :class="floatLabel" :style="labelPositionWidth">{{label}}</label>
    <input
      class="my-input"
      @input="emitInput"
      v-bind="$attrs"
      @focus="focusEvent"
      @blur="blurEvent"
    />
    <div class="input-line"></div>
    <div :class="myFocus"></div>
  </div>
</template>
<script>
export default {
  name: "MyInput",
  props: {
    //label出现的位置
    labelPosition: {
      type: String,
      default: "left",
    },
    //当label出现在左侧时，传入宽度
    labelWidth: {
      type: String,
      default: "100px",
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      flag: false,
      isFocus: false,
      label: "",
    };
  },
  mounted() {
    this.$nextTick(() => {
      this.label = this.$el.querySelector("input").placeholder + ":";
    });
  },
  computed: {
    myFocus() {
      return {
        "line-focus": true,
        focus: this.isFocus,
      };
    },
    floatLabel() {
      return {
        "init-status": true,
        "show-status-top": this.labelPosition == "top" && this.isFocus,
      };
    },
    labelPositionWidth() {
      if (this.labelPosition == "left" && this.isFocus) {
        return `left:-${this.labelWidth};opacity: 1`;
      } else {
        return "";
      }
    },
    input_wrapper_computed_class() {
      console.log(this.disabled,typeof(this.disabled));
      return {
        "disabled": this.disabled
      }
    }
  },
  methods: {
    focusEvent(e) {
      this.$el.querySelector("input").placeholder = "";
      this.isFocus = true;
    },
    blurEvent(e) {
      //动画完毕，placehoder出现
      if (e.target.value) {
      } else {
        setTimeout(() => {
          this.$el.querySelector("input").placeholder = this.label;
        }, 250);
        this.isFocus = false;
      }
    },
    emitInput(e) {
      this.$emit("input", e.target.value);
    },
  },
};
</script>
<style lang="stylus" scoped>
.disabled
  &:hover
    cursor:not-allowed
  background-color:#F5F7FA
  
.input-wrapper
  width: 100%
  position: relative
  .line-focus.focus
    transform: scaleX(1)
  .line-focus
    position: absolute
    bottom: -1px
    height: 2px
    width: 100%
    background-color: #2196f3
    transform: scaleX(0)
    transition-property: transform
    transition-duration: 0.3s
    transition-timing-function: cubic-bezier(0.23, 1, 0.32, 1)
    transition-delay: 0s
  .input-line
    position: absolute
    bottom: -1px
    height: 1px
    width: 100%
    background-color: rgba(0, 0, 0, 0.12)
  .my-input
    width: 100%
    height: 32px
    line-height: 32px
    border: none
    outline: none
    background: none
  .init-status
    position: absolute
    top: 5px
    left: 2px
    bottom: 5px
    opacity: 0
    transition: all 0.3s ease-out
  .show-status-top
    top: -16px
    opacity: 1
</style>