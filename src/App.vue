<template>
  <div id="app">
    <div class="control-box">
      <button @click="expandAll = !expandAll">{{ expandAll ? '收起' : '展开' }}</button>
      <button @click="changeData">更新数据</button>
    </div>
    <org-tree
      :data="data"
      collapsable
      :node-render="nodeRender"
      :expand-all="expandAll"
      :horizontal="false"
      :props="props"
      @on-expand="onExpand"
      @on-node-click="onNodeClick"></org-tree>
  </div>
</template>

<script>
import OrgTree from './components/org-tree'
import { data, newData } from './data'
export default {
  name: 'app',
  data () {
    return {
      data,
      expandAll: false,
      props: {
        id: 'dep_id',
        label: 'title',
        expand: 'expand',
        children: 'dep_children'
      }
    }
  },
  components: { OrgTree },
  methods: {
    nodeRender (h, data) {
      // console.log(data)
      return (
        <span>{data.label}</span>
      )
    },
    onNodeClick (e, data) {
      console.log(data)
    },
    onExpand (val) {
      console.log(val)
    },
    buttonRender (h, data) {
      return (
        <div style={{ width: '20px', height: '20px', background: data.expand ? 'red' : 'yellow' }}></div>
      )
    },
    changeData () {
      this.data = newData
    }
  }
}
</script>

<style lang="less">
html, body{
  height: 100%;
  width: 100%;
  margin: 0;
}
#app {
  height: 100%;
  width: 100%;
}
.control-box{
  padding: 10px;
  button{
    padding: 6px 10px;
    font-size: 14px;
    background: rgb(247, 245, 245);
    border: 1px solid rgb(149, 215, 253);
    border-radius: 4px;
    height: 14px;
    line-height: 14px;
    box-sizing: content-box;
  }
}
</style>
