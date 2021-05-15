<template>
  <div id="nav">
    <router-view></router-view>
    <tab-bar-content></tab-bar-content>
  </div>

</template>


<script>

import TabBarContent from 'components/content/TabBarContent'

export default {
  name:'App',
  components:{
    TabBarContent

  }
}
</script>

<style>

</style>
