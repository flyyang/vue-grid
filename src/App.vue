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
    var data = []
    for (var i = 0; i < 30000; i++) {
      data.push({id: i, domain: i, user: Math.random() * 1000000})
    }
    return {
      checkedFields: [],
      gridOption: {
        columns: [
          {en: 'id', cn: '编号'},
          {en: 'domain', cn: '网址'},
          {en: 'user', cn: '邮箱'}
        ],
        data: data
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
