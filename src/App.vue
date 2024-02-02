<script>
import AppMain from './components/AppMain.vue';


export default {
  data() {
    return {};  
  },
  components: { AppMain }
}


</script>

<template>
  <AppMain />

  <router-view></router-view>
</template>

<style lang="scss">
@use "./style/general.scss" as *;
</style>
