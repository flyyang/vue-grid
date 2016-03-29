<style>
  .pagination {
    float:right;
    padding-right:10px;  
  }
  .pagination ul {
    list-style-type:none;
  }
  .pagination ul li {
    display:inline-block;
    background:#efefef;
    border-radius:12px;
    height:24px;
    width:24px;
    text-align:center;
    margin-right:2px;
  }
  .pagination ul li:hover{
    background:#2bbb9c;
  }
  .pagination ul li a {
    text-decoration:none;
    display:block;
    width:24px;
    height:24px;
    margin:0 auto;
    padding-top:5px;
    font-size:14px;
    color:#999;
  }
  .pagination ul li a:hover{
    color:#fff;
  }
  .pagination .active {
    background:#2bbb9c;  
  }
  .pagination .active  a{
    color:#fff;
  }
  .pagination .disabled{
    background:#fff;
    cursor:default;
    color: #fff !important;
  }
  .pagination>ul {
    float:right;
  }
  .pagination .stastics {
    float:right;
    font-size: 12px;
    padding-top: 5px;
    margin-right: 5px;
    margin-top: 16px;
  }
  .pagination .stastics span{
    color:#2bbb9c;
  }
</style>

<template>
  <div class="pagination-container">
    <template v-if="rowsTotal > 0">
      <div class="pagination">
        <ul>
          <li><a href="javascript:void(0)" @click="prev"  v-bind:class="{'disabled':isFirst}">&lt</a></li>
          <li v-for="n in pageChunkCurrent" v-bind:class="{'active':isActive[n+1]}" @click="nav( n+1 )"><a  href="javascript:void(0)">{{n + 1}}</a></li>
          <li><a href="javascript:void(0)" @click="next" v-bind:class="{'disabled':isLast}">&gt</a></li>
        </ul>
        <div class="stastics">共<span>{{rowsTotal}}</span>条，<span>{{pageTotal}}</span>页</div>
      </div>
    </template>
  </div>
</template>

<script>
  module.exports = {
    props: {
      pageSize: {
        type: Number,
        default: 10
      },
      rowsTotal: {
        type: Number,
        required: true
      },
      page: {
        type: Number,
        required: true
      }
    },
    watch: {
      rowsTotal: function (newVal, oldVal) {
        if (newVal !== oldVal) {
          // init option when rows changes
          this.page = 1
          this.isFirst = true
          this.isLast = false
        }
      },
      pageTotal: function (newVal, oldVal) {
        if (newVal === 1) {
          // only one page
          this.isFirst = true
          this.isLast = true
        }
      }
    },
    computed: {
      pageChunkCurrent: function () {
        let pageTotal = Math.ceil(this.rowsTotal / this.pageSize)
        let pageArr = []
        for (let i = 0; i < pageTotal; i++) {
          pageArr[i] = i
        }
        let pageChunk = []
        let j = pageArr.length
        for (let i = 0; i < j; i += this.pageSize) {
          pageChunk.push(pageArr.slice(i, i + this.pageSize))
        }
        return pageChunk[this.pageChunkIndex]
      },
      pageTotal: function () {
        let total = Math.ceil(this.rowsTotal / this.pageSize)
        if (total === 1) {
          this.isLast = true
          this.isFirst = true
        }
        return Math.ceil(this.rowsTotal / this.pageSize)
      },
      isActive: function () {
        let pageTotal = this.pageTotal
        let o = {}
        for (let i = 0; i < pageTotal; i++) {
          o[i + 1] = 0
        }
        o['actived'] = this.page
        o[this.page] = 1
        return o
      }
    },
    data: function () {
      let pageTotal = this.pageTotal
      let pageArr = []
      for (let i = 0; i < pageTotal; i++) {
        pageArr[i] = i
      }
      let pageChunk = []
      let j = pageArr.length
      for (let i = 0; i < j; i += this.pageSize) {
        pageChunk.push(pageArr.slice(i, i + this.pageSize))
      }
      return {
        pageChunk: pageChunk,
        pageChunkIndex: 0,
        isLast: false,
        isFirst: true
      }
    },
    methods: {
      nav: function (n) {
        let activeObj = this.isActive
        activeObj[activeObj['actived']] = 0
        activeObj[n] = 1
        activeObj['actived'] = n
        n === 1 ? this.isFirst = true : this.isFirst = false
        this.pageTotal === n ? this.isLast = true : this.isLast = false
        this.page = n
      },
      next: function () {
        let activeObj = this.isActive
        if (activeObj.actived % this.pageSize === 0) {
          this.pageChunkIndex += 1
          this.pageChunkCurrent = this.pageChunk[this.pageChunkIndex]
        }
        if (activeObj.actived + 1 <= this.pageTotal) {
          this.nav(activeObj.actived + 1)
        }
      },
      prev: function () {
        let activeObj = this.isActive
        if (activeObj.actived - 1 >= 1) {
          this.nav(activeObj.actived - 1)
        }
        if (activeObj.actived % this.pageSize === 0) {
          this.pageChunkIndex -= 1
          this.pageChunkCurrent = this.pageChunk[this.pageChunkIndex]
        }
      }
    }
  }
</script>
