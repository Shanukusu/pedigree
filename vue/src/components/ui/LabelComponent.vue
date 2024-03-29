<template>
  <div class="label-container">
    <slot></slot>
    <span 
      v-if="value !== ''" 
      :class="{ 'label': true, 'label-with-text': !!value }"
    >
      {{ value }}
    </span>
    <span 
      v-else 
      class="label label-empty"
    >
    </span>
  </div>
</template>

<script>
  export default {
    name: 'LabelComponent',
    props: {
      value: {
        type: String,
        default: ''
      }
    }
  }
</script>

<style scoped lang="less">
.label-container {
  display: inline-block;
  position: relative;
  width: 100%;
}
.label {
  background-color: #ff7575;
  width: auto;
  height: auto;
  border-radius: 2em;
  position: relative;
  right: 8px;
  bottom: 15px;
  display: inline-block;
}
.label-with-text {
  padding: 5px;
  padding-left: 10px;
  padding-right: 10px;
}
.label-empty {
  width: 12px;
  height: 12px;
  border-radius: 6px;
}
</style>
