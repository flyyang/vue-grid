<template>
  <vue-grid :check-able="true" chekedFiled="id" :index-able="true" :columns="gridOption.columns" :data="gridOption.data" :checked-fields.sync="checkedFields"></vue-grid>
</template>

<script>
import VueGrid from './components/Table'

export default {
  components: {
    vueGrid: VueGrid
  },
  data: function () {
    return {
      checkedFields: [],
      gridOption: {
        columns: [
          {en: 'id', cn: '编号'},
          {en: 'domain', cn: '网址'},
          {en: 'user', cn: '邮箱'}
        ],
        data: [
          { id: 1, domain: 'google', user: 'test@github.com' },
          { id: 2, domain: 'baidu', user: 'test@github.com' },
          { id: 3, domain: 'bing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 5, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 6, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 7, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 8, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 9, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 10, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 11, domain: 'test1', user: 'test@github.com' },
          { id: 12, domain: 'test2', user: 'test@github.com' },
          { id: 13, domain: 'test3', user: 'test@github.com' },
          { id: 14, domain: 'test4', user: 'test@github.com' },
          { id: 15, domain: 'test5', user: 'test@github.com' },
          { id: 16, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 17, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 18, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 19, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 20, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 21, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 22, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 23, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 24, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 25, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 26, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 27, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 28, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 29, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 30, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 31, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 32, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 33, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 34, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 35, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 36, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 37, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 38, domain: '<a href="http://www.baidu.com" target="_blank">百度</a>', user: 'test@github.com' },
          { id: 39, domain: '<a href="http://www.bing.com" target="_blank">必应</a>', user: 'test@github.com' },
          { id: 40, domain: 'test6', user: 'test@github.com' }
        ]
      }
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  margin-top: -100px;
  max-width: 600px;
  font-family: Helvetica, sans-serif;
  text-align: center;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
