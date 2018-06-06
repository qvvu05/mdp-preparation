<template>
  <el-container>
    <!-- <Header/> -->
    <el-container>
      <SideBar/>
      <el-main>
        <nuxt/>
      </el-main>
    </el-container>
  </el-container>

</template>
<script>
import Header from '~/components/TheHeader'
import SideBar from '~/components/TheSideBar'
export default {
  components:{
    Header,
    SideBar
  }
}
</script>

<style>
</style>
