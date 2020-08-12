<!--
 * @Descripttion: 
 * @version: 
 * @Author: linxp
 * @Date: 2020-08-12 14:55:26
 * @LastEditors: linxp
 * @LastEditTime: 2020-08-12 15:40:27
-->
<template>
  <div
    class="select-box"
    :style="{borderColor: active?color:'transparent'}"
    @click="onHandleActive"
  >
    <div v-show="active" class="select-box__check" :style="{backgroundColor: color}">
      <img
        src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAABKElEQVRYR+2V4TEEQRCFvxeBC0EGyOBEgAgQgggIQQaIABGQAUKQARE81VWjaotZ27d3t/vD9J+pmpqd9+3rnm4xc2hmfRpAc6A58D8csL0A7oGFpINu75nEAdsPwBHwLml3UgDbt8Ap8AksJb1OBjAkHiBbS0FGfGsAtq+Ay2L1oaTnvqG3cQdsnwE3RfBcUtRAb/wCKBW7A5xI+lhlXK8qXk2B7ajSPSDWsC8FMUa8DyCaRuQsDWF7CTwVty4kXWedq9ZA6VwpCNv7RTzA7yRFDaSjtwgzEOuKDz7DvyA2IT4IEAdqEDFUgJeyPko6Tnv+42CqD1Qg4prI/Vvp76mXUoNMAVSciK21xVMp6FJ3nIjtmGyj//z73rQDY3M89F0DaA7M7sAXMpl/Ia8A/tgAAAAASUVORK5CYII="
      />
    </div>
    <slot></slot>
  </div>
</template>
<script>
export default {
  name: "select-box",
  props: {
    "icon-size": {
      type: String,
      default: "50px",
    },
    color: {
      type: String,
      default: "#67C23A",
    },
    active: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    /**
     * @effect: 激活当前元素
     */

    onHandleActive() {
      this.$emit("update:active", !this.active);
    },
  },
};
</script>
<style scoped>
.select-box {
  position: relative;
  border-width: 1px;
  border-style: solid;
  overflow: hidden;
  box-sizing: border-box;
}
.select-box__check {
  position: absolute;
  top: -25px;
  right: -25px;
  display: flex;
  align-items: flex-end;
  justify-content: center;
  padding-bottom: 3px;
  box-sizing: border-box;
  width: 50px;
  height: 50px;
  transform: rotate(45deg);
  background-color: red;
  z-index: 2;
  user-select: none;
}
.select-box__check img {
  transform: rotate(-45deg);
  width: 16px;
  user-select: none;
}
</style>