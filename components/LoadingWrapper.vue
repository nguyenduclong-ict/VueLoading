<template>
  <div class="loading-wrapper">
    <Loading v-bind="$props" />
  </div>
</template>

<script>
import Loading from './Loading'
export default {
  name: 'LoadingWrapper',
  components: { Loading },
  props: ['name', 'nums', 'dotName', 'color', 'size'],
}
</script>

<style>
.loading-wrapper {
  height: 100%;
  width: 100%;
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  top: 0px;
  left: 0px;
}
</style>
