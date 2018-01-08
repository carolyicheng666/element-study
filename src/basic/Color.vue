<template>
  <div id="app">
    <h1>Color 色彩</h1>
    <p>Element 为了避免视觉传达差异，使用一套特定的调色板来规定颜色，为你所搭建的产品提供一致的外观视觉感受。</p>

    <h2>主色</h2>
    <p>Element 主要品牌颜色是鲜艳、友好的蓝色。</p>
    <el-row>
      <el-col :span="6"><div class="grid-content bg-blue">Blue #409EFF</div></el-col>
    </el-row>

    <h2>辅助色</h2>
    <p>除了主色外的场景色，需要在不同的场景中使用（例如危险色表示危险的操作）。</p>
    <el-row>
      <el-col :span="6"><div class="grid-content bg-success">Success #67C23A</div></el-col>
      <el-col :span="6"><div class="grid-content bg-warning">Warning #E6A23C</div></el-col>
      <el-col :span="6"><div class="grid-content bg-danger">Danger #F56C6C</div></el-col>
      <el-col :span="6"><div class="grid-content bg-info">Info #909399</div></el-col>
    </el-row>

    <h2>中性色</h2>
    <p>中性色用于文本、背景和边框颜色。通过运用不同的中性色，来表现层次结构。</p>
    <el-row>
      <el-col :span="6"><div class="grid-content word-1">主要文字 #303133</div></el-col>
      <el-col :span="6"><div class="grid-content word-2">常规文字 #606266</div></el-col>
      <el-col :span="6"><div class="grid-content word-3">次要文字 #909399</div></el-col>
      <el-col :span="6"><div class="grid-content word-4">占位文字 #c0c4cc</div></el-col>
    </el-row>

    <el-row>
      <el-col :span="6"><div class="grid-content border-1">一级边框 #dcdfe6</div></el-col>
      <el-col :span="6"><div class="grid-content border-2">二级边框 #e4e7ed</div></el-col>
      <el-col :span="6"><div class="grid-content border-3">三级边框 #ebeef5</div></el-col>
      <el-col :span="6"><div class="grid-content border-4">四级边框 #f2f6fc</div></el-col>
    </el-row>
  </div>
</template>

<script>
  
</script>

<style>
.el-row {
  margin-bottom: 20px;
  &:last-child {
    margin-bottom: 0;
  }
}
.el-col {
  border-radius: 4px;
}
.grid-content {
  border-radius: 4px;
  text-align: center;
  color: #fff;
  height: 100px;
  line-height: 100px;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}
.bg-blue {
  background: #409eff;
}
.bg-success {
  background: #67c23a;
}
.bg-warning {
  background: #e6a23c;
}
.bg-danger {
  background: #f56c6c;
}
.bg-info {
  background: #909399;
}
.word-1 {
  background: #303133;
}
.word-2 {
  background: #606266;
}
.word-3 {
  background: #909399;
}
.word-4 {
  background: #c0c4cc;
}
.border-1 {
  background: #dcdfe6;
}
.border-2 {
  background: #e4e7ed;
}
.border-3 {
  background: #ebeef5;
}
.border-4 {
  background: #f2f6fc;
}
</style>