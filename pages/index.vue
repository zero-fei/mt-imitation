<template>
  <div class='page-index'>
    <el-row>
      <el-col :span='5'>
        <emenu />
      </el-col>
      <el-col :span='19'>2</el-col>
    </el-row>
    <el-row>24</el-row>
  </div>
</template>

<script>
import Emenu from '@/components/home/menu'
export default {
  components: {
    Emenu
  }
};
</script>
<style lang='scss'>
@import '@/assets/css/index/index.scss';
</style>
