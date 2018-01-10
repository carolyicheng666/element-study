<template>
  <div id="app">
    <h1>Notification 通知</h1>
    <p>悬浮出现在页面角落，显示全局的通知提醒消息。</p>

    <h2>基础用法</h2>
    <p>适用性广泛的通知栏。Notification 组件提供通知功能，Element 注册了$notify方法，接收一个options字面量参数，在最简单的情况下，你可以设置title字段和message字段，用于设置通知的标题和正文。默认情况下，经过一段时间后 Notification 组件会自动关闭，但是通过设置duration，可以控制关闭的时间间隔，特别的是，如果设置为0，则不会自动关闭。注意：duration接收一个Number，单位为毫秒，默认为4500。</p>
    <el-button
      plain
      @click="open">
      可自动关闭
    </el-button>
    <el-button
      plain
      @click="open2">
      不会自动关闭
    </el-button>

    <h2>带有倾向性</h2>
    <p>带有 icon，常用来显示「成功、警告、消息、错误」类的系统消息。Element 为 Notification 组件准备了四种通知类型：success, warning, info, error。通过type字段来设置，除此以外的值将被忽略。同时，我们也为 Notification 的各种 type 注册了方法，可以在不传入type字段的情况下像open5和open6那样直接调用。</p>
    <el-button
      plain
      @click="open3">
      成功
    </el-button>
    <el-button
      plain
      @click="open4">
      警告
    </el-button>
    <el-button
      plain
      @click="open5">
      消息
    </el-button>
    <el-button
      plain
      @click="open6">
      错误
    </el-button>

    <h2>自定义弹出位置</h2>
    <p>可以让 Notification 从屏幕四角中的任意一角弹出。使用position属性定义 Notification 的弹出位置，支持四个选项：top-right、top-left、bottom-right、bottom-left，默认为top-right。</p>
    <el-button
      plain
      @click="open7">
      右上角
    </el-button>
    <el-button
      plain
      @click="open8">
      右下角
    </el-button>
    <el-button
      plain
      @click="open9">
      左下角
    </el-button>
    <el-button
      plain
      @click="open10">
      左上角
    </el-button>

    <h2>带有偏移</h2>
    <p>让 Notification 偏移一些位置。Notification 提供设置偏移量的功能，通过设置 offset 字段，可以使弹出的消息距屏幕边缘偏移一段距离。注意在同一时刻，所有的 Notification 实例应当具有一个相同的偏移量。</p>
    <el-button
      plain
      @click="open11">
      偏移的消息
    </el-button>

    <h2>使用 HTML 片段</h2>
    <p>message 属性支持传入 HTML 片段。将dangerouslyUseHTMLString属性设置为 true，message 就会被当作 HTML 片段处理。</p>
    <el-button
      plain
      @click="open12">
      使用 HTML 片段
    </el-button>

    <h2>隐藏关闭按钮</h2>
    <p>可以不显示关闭按钮。将showClose属性设置为false即可隐藏关闭按钮。</p>
    <el-button
      plain
      @click="open13">
      隐藏关闭按钮
    </el-button>
  </div>
</template>
<script>
  export default {
    methods: {
      open() {
        const h = this.$createElement;

        this.$notify({
          title: '标题名称',
          message: h('i', { style: 'color: teal'}, '这是提示文案这是提示文案这是提示文案这是提示文案这是提示文案这是提示文案这是提示文案这是提示文案')
        });
      },

      open2() {
        this.$notify({
          title: '提示',
          message: '这是一条不会自动关闭的消息',
          duration: 0
        });
      },

      open3() {
        this.$notify({
          title: '成功',
          message: '这是一条成功的提示消息',
          type: 'success'
        });
      },

      open4() {
        this.$notify({
          title: '警告',
          message: '这是一条警告的提示消息',
          type: 'warning'
        });
      },

      open5() {
        this.$notify.info({
          title: '消息',
          message: '这是一条消息的提示消息'
        });
      },

      open6() {
        this.$notify.error({
          title: '错误',
          message: '这是一条错误的提示消息'
        });
      },

      open7() {
        this.$notify({
          title: '自定义位置',
          message: '右上角弹出的消息'
        });
      },

      open8() {
        this.$notify({
          title: '自定义位置',
          message: '右下角弹出的消息',
          position: 'bottom-right'
        });
      },

      open9() {
        this.$notify({
          title: '自定义位置',
          message: '左下角弹出的消息',
          position: 'bottom-left'
        });
      },

      open10() {
        this.$notify({
          title: '自定义位置',
          message: '左上角弹出的消息',
          position: 'top-left'
        });
      },

      open11() {
        this.$notify({
          title: '偏移',
          message: '这是一条带有偏移的提示消息',
          offset: 100
        });
      },

      open12() {
        this.$notify({
          title: 'HTML 片段',
          dangerouslyUseHTMLString: true,
          message: '<strong>这是 <i>HTML</i> 片段</strong>'
        });
      },

      open13() {
        this.$notify.success({
          title: 'Info',
          message: '这是一条没有关闭按钮的消息',
          showClose: false
        });
      }
    }
  }
</script>
