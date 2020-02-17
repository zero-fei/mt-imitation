<template>
  <el-container class='layout-default'>
    <el-header height='197px'>
      <hearder-contnt />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer height='100%'>
      <my-foot />
    </el-footer>
  </el-container>
</template>
<script>
import HearderContnt from "@/components/public/header";
import MyFoot from "@/components/public/footer";
export default {
  components: {
    HearderContnt,
    MyFoot
  }
}
</script>
<style >
</style>
