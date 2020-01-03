<template>
  <el-container class='layout-default'>
    <el-header height='197px'>
      <hearder-contnt />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer height='100%'>Footer</el-footer>
  </el-container>
</template>
<script>
import HearderContnt from "@/components/public/header";
export default {
  components: {
    HearderContnt
  }
}
</script>
<style >
</style>
