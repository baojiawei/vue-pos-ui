<template>
  <div class="pos-button-group">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'pos-button-group',
  mounted() {
    let children = this.$el.children
    for (let i = 0, length = children.length; i < length; i++) {
      console.assert(children[i].tagName === 'BUTTON', '按钮组的子元素必须是button')
    }
  }
}
</script>

<style lang="scss">
@import '@/styles/_var.scss';
.pos-button-group {
  display: inline-flex;
  vertical-align: middle;
  button {
    border-radius: 0;
    &:not(:first-child) {
      margin-left: -1px;
    }
    &:first-child {
      border-top-left-radius: $border-radius;
      border-bottom-left-radius: $border-radius;
    }
    &:last-child {
      border-top-right-radius: $border-radius;
      border-bottom-right-radius: $border-radius;
    }
    &:hover {
      z-index: 1;
    }
    &:focus {
      z-index: 2;
    }
  }
}
</style>
