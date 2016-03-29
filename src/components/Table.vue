<style>
  .vue-grid {
    width:980px;
  }
  .table {
    padding-bottom: 10px;
		width:100%;
  }
	.table table {
		width:100%;
		font-size:12px;
    text-align: left;
	}
	.table thead tr{
		background: #eaf3f6;
		border-bottom:2px solid #fff;
	}
  .table thead th {
		font-size: 12px;
    font-weight: bold;
    line-height: 31px;
    padding-left: 5px;
    color: #085982;
		cursor:pointer;
  }
	.table tbody tr {
		background: #f5f8f9;
		line-height: 2.6em;
		margin-bottom:2px;
		border-bottom: 2px solid #fff;
	}
	.table tbody tr:hover {
		background:#eaf3f6;
	}
	.table tbody tr td{
		padding-left:2px;
	}
	.arrow.asc {
		border-left: 4px solid transparent;
		border-right: 4px solid transparent;
		border-bottom: 4px solid #fff;
	}
	.arrow.dsc {
		border-left: 4px solid transparent;
		border-right: 4px solid transparent;
		border-top: 4px solid #fff;
	}
  .operation{
    height:30px;
    margin-top:5px;
    margin-bottom:3px;
  }
  .search{
    float:right;
  }	
  .search input{
    height:25px;
  }
  .table .operation-th {
    width:30px;
  }	
</style>

<template>
  <div class="vue-grid">
  <template v-if="searchAble">
    <div class="operation">
      <div class="search"><form v-on:submit.prevent id="search"><input name="query" v-model="filterKey"></div>
    </div>
  </template>
  <div class="table">
    <table grid-select="{{checkedFields}}">
      <thead>
        <tr>
          <th v-if="checkAble" class="operation-th"></th>
          <th v-if="indexAble" class="operation-th"></th>
          <th v-for="item in columns" @click="sortBy(item.en)">
					  {{item.cn}}
					</th>
        </tr>
      </thead>
      <tbody>
        <template v-if="pageAble">
          <template v-if="filterRows.length > 0">
            <tr v-for="item in data | filterBy filterKey | orderBy sortKey sortOrders[sortKey] | limitBy pageSize pageStart">
              <td v-if="checkAble"><input type="checkbox" id="{{item[checkedField]}}" value="{{item[checkedField]}}" v-model="checkedFields"></td>
              <td v-if="indexAble">{{indexVal($index)}}</td>
              <td v-for="key in columnsEn" >{{{ item[key] }}} </td>
            </tr>
          </template>
          <template v-else>
            <tr><td :colspan="100">没有数据</td></tr>
          </template>
        </template>
        <template v-else>
          <tr v-for="item in data | filterBy filterKey | orderBy sortKey sortOrders[sortKey]">
            <td v-for="key in columnsEn" >{{{ item[key] }}} </td>
          </tr>
        </template>
      </tbody>
    </table>
  </div>
    <template v-if="pageAble">
      <pagination :page-size="pageSize" :rows-total="filterRows.length" :page.sync="page"></pagination>
    </template>
  </div>
</template>

<script>
  import Pagination from './Pagination'
  module.exports = {
    components: {
      pagination: Pagination
    },
    props: {
      pageAble: {
        type: Boolean,
        default: true
      },
      searchAble: {
        type: Boolean,
        default: true
      },
      indexAble: {
        type: Boolean,
        default: false
      },
      checkedField: {
        type: String,
        default: 'id'
      },
      checkedFields: {
        type: Array,
        default: []
      },
      checkAble: {
        type: Boolean,
        default: false
      },
      pageSize: {
        type: Number,
        default: 10
      },
      columns: {
        type: Array,
        required: true
      },
      columnsWidth: {
        type: Array
      },
      data: {
        type: Array,
        default: [],
        required: true
      }
    },
    methods: {
      sortBy: function (key) {
        this.page = 1
        this.sortKey = key
        this.sortOrders[key] *= -1
      },
      indexVal: function (index) {
        index = index + 1
        return index < 10 ? '0' + index : index
      }
    },
    computed: {
      filterRows: function () {
        this.page = 1
        return this.$options.filters.filterBy(this.data, this.filterKey)
      },
      pageStart: function () {
        return (this.page - 1) * this.pageSize
      },
      columnsCn: function () {
        let columns = this.columns
        let cl = columns.length
        let arr = []
        for (let i = 0; i < cl; i++) {
          arr.push(columns[i]['cn'])
        }
        return arr
      },
      columnsEn: function () {
        let columns = this.columns
        let cl = columns.length
        let arr = []
        for (let i = 0; i < cl; i++) {
          arr.push(columns[i]['en'])
        }
        return arr
      }
    },
    data: function () {
      let sortOrders = {}
      let columns = this.columns
      let cl = columns.length
      for (let i = 0; i < cl; i++) {
        sortOrders[columns[i]['en']] = 1
      }
      return {
        sortKey: '',
        filterKey: '',
        page: 1,
        sortOrders: sortOrders
      }
    }
  }
</script>
