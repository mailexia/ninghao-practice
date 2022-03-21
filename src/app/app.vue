<template>
  <h3>{{name}}</h3>
  <label for='sub-annual'>
    <input id='sub-annual' type='radio' value='annual' v-model='subscription'>
    一年
  </label>
  <label for='sub-season'>
    <input id='sub-season' type='radio' value='quarterly' v-model='subscription'>
    季度
  </label>
  <span>{{subscription}}</span>
</template>

<script>
export default {
  name: 'app',
  data: function() {
    return {
      name: 'ninghao',
      subscription:'annual'
    };
  }

};
</script>

<style scoped>
@import "./styles/app.css";
</style>