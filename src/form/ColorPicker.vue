<template>
  <div id="app">
    <h1>ColorPicker 颜色选择器</h1>
    <p>用于颜色选择，支持多种格式。</p>

    <h2>基础用法</h2>
    <p>使用 v-model 与 Vue 实例中的一个变量进行双向绑定，绑定的变量需要是字符串类型。</p>
    <div class="block">
      <span class="demonstration">有默认值</span>
      <el-color-picker v-model="color1"></el-color-picker>
    </div>
    <div class="block">
      <span class="demonstration">无默认值</span>
      <el-color-picker v-model="color2"></el-color-picker>
    </div>

    <h2>选择透明度</h2>
    <p>ColorPicker 支持普通颜色，也支持带 Alpha 通道的颜色，通过show-alpha属性即可控制是否支持透明度的选择。</p>
    <el-color-picker v-model="color3" show-alpha></el-color-picker>

    <h2>不同尺寸</h2>
    <el-color-picker v-model="color4"></el-color-picker>
    <el-color-picker v-model="color4" size="medium"></el-color-picker>
    <el-color-picker v-model="color4" size="small"></el-color-picker>
    <el-color-picker v-model="color4" size="mini"></el-color-picker>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        color1: '#409EFF',
        color2: null,
        color3: 'rgba(19, 206, 102, 0.8)'
      }
    }
  };
</script>