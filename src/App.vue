<template>
  <vue-grid :columns="gridOption.columns" :data="gridOption.data"></vue-grid>
</template>

<script>
import VueGrid from './components/Table'

export default {
  components: {
    vueGrid: VueGrid
  },
  data: function () {
    return {
      gridOption: {
        columns: [
          {en: 'id', cn: '订单号'},
          {en: 'domain', cn: '域名'},
          {en: 'user', cn: '用户名'}
        ],
        data: [
          { id: 1, domain: 'bss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 2, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 3, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 4, domain: '<a href="http://www.baidu.com" target="_blank">中文怎么样</a>', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' },
          { id: 1, domain: 'oss_beijing', user: 'test@github.com' }
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
