<template>
<div class="index">
  <el-container>
    <el-header>Header</el-header>
    <el-container>

      <el-aside width="200px">
        <el-tree :data="menuData" :props="defaultProps" @node-click="handleNodeClick"></el-tree>
      </el-aside>

      <el-container>
        <el-main>Main</el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </el-container>
  </el-container>
</div>
</template>

<script>

export default {
  name: 'Index',
  data: function () {
    return {
      menuData: [],
      defaultProps: {
        children: 'children',
        label: 'name'
      }
    }
  },
  methods: {
    handleNodeClick (d) {
      console.log(d)
    }
  },
  mounted: function () {
    const axios = require('axios')
    // 得到所有菜单
    axios.get('/api/system/getAllMenu')
      .then(function (response) {
        this.menuData = response.data.data
      }.bind(this))
  }

}
</script>

<style scoped>

  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }

</style>
