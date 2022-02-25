<template>
  <div id="app">
    <div class="app-wrapper">
      <SideLeft :tab="tab"></SideLeft>
      <SideRight @change_tab="handleChangeTab"></SideRight>
    </div>
  </div>
</template>

<script>
import SideLeft from './components/sideLeft'
import SideRight from './components/sideRight'

export default {
  name: 'App',
  components: {
    SideLeft,
    SideRight
  },
  data: ()=>{
    return {
      tab: 'student'
    }
  },
  methods: {
    handleChangeTab(e){
      this.tab = e
    }
  }
}
</script>

<style lang="scss">

</style>
