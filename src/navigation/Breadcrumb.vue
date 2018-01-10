<template>
  <div id="app">
    <h1>Breadcrumb 面包屑</h1>
    <p>显示当前页面的路径，快速返回之前的任意页面。</p>

    <h2>基础用法</h2>
    <p>适用广泛的基础用法。在el-breadcrumb中使用el-breadcrumb-item标签表示从首页开始的每一级。Element 提供了一个separator属性，在el-breadcrumb标签中设置它来决定分隔符，它只能是字符串，默认为斜杠/</p>
    <el-breadcrumb separator="/">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item>活动管理</el-breadcrumb-item>
      <el-breadcrumb-item>活动列表</el-breadcrumb-item>
      <el-breadcrumb-item>活动详情</el-breadcrumb-item>
    </el-breadcrumb>

    <h2>图标分隔符</h2>
    <p>通过设置 separator-class 可使用相应的 iconfont 作为分隔符，注意这将使 separator 设置失效</p>
    <el-breadcrumb separator-class="el-icon-arrow-right">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item>活动管理</el-breadcrumb-item>
      <el-breadcrumb-item>活动列表</el-breadcrumb-item>
      <el-breadcrumb-item>活动详情</el-breadcrumb-item>
    </el-breadcrumb>
  </div>
</template>