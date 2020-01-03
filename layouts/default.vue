<template>
  <el-container class='layout-default'>
    <el-header>
      <hearder-contnt />
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</template>
<script>
import HearderContnt from "@/components/header";
export default {
  components: {
    HearderContnt
  }
}
</script>
