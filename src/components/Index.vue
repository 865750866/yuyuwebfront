<template>
<div class="index">
  <el-container>
    <el-header>Header</el-header>
    <el-container>

      <el-aside width="200px">
        <el-tree :data="data" :props="defaultProps" @node-click="handleNodeClick"></el-tree>
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
      data: [{
        label: '一级 1',
        id: 1,
        children: [{
          label: '二级 1-1',
          children: [{
            label: '三级 1-1-1'
          }]
        }]
      }],
      defaultProps: {
        children: 'children',
        label: 'label'
      }
    }
  },
  methods: {
    handleNodeClick (data) {
      console.log(data)
    }
  },
  mounted: function () {
    const axios = require('axios')

    // 得到所有菜单
    axios.get('/api/system/getAllMenu')
      .then(function (response) {
        // handle success
        console.log(response)
      })
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
