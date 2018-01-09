<template>
  <div id="app">
    <h1>Loading 加载</h1>
    <p>加载数据时显示动效。</p>

    <h2>区域加载</h2>
    <p>在表格等容器中加载数据时显示。Element 提供了两种调用 Loading 的方法：指令和服务。对于自定义指令v-loading，只需要绑定Boolean即可。默认状况下，Loading 遮罩会插入到绑定元素的子节点，通过添加body修饰符，可以使遮罩插入至 DOM 中的 body 上。</p>
    <el-table
      v-loading="loading"
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="date"
        label="日期"
        width="180">
      </el-table-column>
      <el-table-column
        prop="name"
        label="姓名"
        width="180">
      </el-table-column>
      <el-table-column
        prop="address"
        label="地址">
      </el-table-column>
    </el-table>

    <h2>自定义</h2>
    <p>可自定义加载文案、图标和背景色。在绑定了v-loading指令的元素上添加element-loading-text属性，其值会被渲染为加载文案，并显示在加载图标的下方。类似地，element-loading-spinner和element-loading-background属性分别用来设定图标类名和背景色值。</p>
    <el-table
      v-loading="loading2"
      element-loading-text="拼命加载中"
      element-loading-spinner="el-icon-loading"
      element-loading-background="rgba(0, 0, 0, 0.8)"
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="date"
        label="日期"
        width="180">
      </el-table-column>
      <el-table-column
        prop="name"
        label="姓名"
        width="180">
      </el-table-column>
      <el-table-column
        prop="address"
        label="地址">
      </el-table-column>
    </el-table>

    <h2>整页加载</h2>
    <p>页面数据加载时显示。当使用指令方式时，全屏遮罩需要添加fullscreen修饰符（遮罩会插入至 body 上），此时若需要锁定屏幕的滚动，可以使用lock修饰符；当使用服务方式时，遮罩默认即为全屏，无需额外设置。</p>
    <el-button
      type="primary"
      @click="openFullScreen"
      v-loading.fullscreen.lock="fullscreenLoading">
      指令方式
    </el-button>
    <el-button
      type="primary"
      @click="openFullScreen2">
      服务方式
    </el-button>

    <h2>服务</h2>
    <p>Loading 还可以以服务的方式调用。引入 Loading 服务：</p>
    <code>import { Loading } from 'element-ui';</code>
    <p>在需要调用时：</p>
    <code>Loading.service(options);</code>
    <p>其中 options 参数为 Loading 的配置项，具体见下表。LoadingService 会返回一个 Loading 实例，可通过调用该实例的 close 方法来关闭它：</p>
    <code>let loadingInstance1 = Loading.service({ fullscreen: true });<br>let loadingInstance2 = Loading.service({ fullscreen: true });<br>console.log(loadingInstance1 === loadingInstance2); // true</code>
    <p>此时调用它们中任意一个的 close 方法都能关闭这个全屏 Loading。</p>
    <p>如果完整引入了 Element，那么 Vue.prototype 上会有一个全局方法 $loading，它的调用方式为：this.$loading(options)，同样会返回一个 Loading 实例。</p>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        tableData: [{
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }],
        loading: true,
        loading2: true,
        fullscreenLoading: false
      };
    },
    methods: {
      openFullScreen() {
        this.fullscreenLoading = true;
        setTimeout(() => {
          this.fullscreenLoading = false;
        }, 2000);
      },
      openFullScreen2() {
        const loading = this.$loading({
          lock: true,
          text: 'Loading',
          spinner: 'el-icon-loading',
          background: 'rgba(0, 0, 0, 0.7)'
        });
        setTimeout(() => {
          loading.close();
        }, 2000);
      }
    }
  };
</script>
<style>
  body {
    margin: 0;
  }
  code {
    font-family: Consolas; 
    display: block; 
    border: 1px solid #ccc;
    padding: 20px
  }
</style>