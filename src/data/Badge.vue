<template>
  <div id="app">
    <h1>Badge 标记</h1>
    <p>出现在按钮、图标旁的数字或状态标记。</p>

    <h2>基础用法</h2>
    <p>展示新消息数量。定义value属性，它接受Number或者String。</p>
    <el-badge :value="12" class="item">
      <el-button size="small">评论</el-button>
    </el-badge>
    <el-badge :value="3" class="item">
      <el-button size="small">回复</el-button>
    </el-badge>

    <el-dropdown trigger="click">
      <span class="el-dropdown-link">
        点我查看<i class="el-icon-caret-bottom el-icon--right"></i>
      </span>
      <el-dropdown-menu slot="dropdown">
        <el-dropdown-item class="clearfix">
          评论
          <el-badge class="mark" :value="12" />
        </el-dropdown-item>
        <el-dropdown-item class="clearfix">
          回复
          <el-badge class="mark" :value="3" />
        </el-dropdown-item>
      </el-dropdown-menu>
    </el-dropdown>

    <h2>最大值</h2>
    <p>可自定义最大值。由max属性定义，它接受一个Number，需要注意的是，只有当value为Number时，它才会生效。</p>
    <el-badge :value="200" :max="99" class="item">
      <el-button size="small">评论</el-button>
    </el-badge>
    <el-badge :value="100" :max="10" class="item">
      <el-button size="small">回复</el-button>
    </el-badge>

    <h2>自定义内容</h2>
    <p>可以显示数字以外的文本内容。定义value为String类型是时可以用于显示自定义文本。</p>
    <el-badge value="new" class="item">
      <el-button size="small">评论</el-button>
    </el-badge>
    <el-badge value="hot" class="item">
      <el-button size="small">回复</el-button>
    </el-badge>

    <h2>小红点</h2>
    <p>以红点的形式标注需要关注的内容。除了数字外，设置is-dot属性，它接受一个Boolean。</p>
    <el-badge is-dot class="item">数据查询</el-badge>
    <el-badge is-dot class="item">
      <el-button class="share-button" icon="el-icon-share" type="primary"></el-button>
    </el-badge>

  </div>
</template>
<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
