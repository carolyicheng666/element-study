<template>
  <div id="app">
    <h1>Slider 滑块</h1>
    <p>通过拖动滑块在一个固定区间内进行选择</p>

    <h2>基础用法</h2>
    <p>在拖动滑块时，显示当前值</p>
    <div class="block">
      <span class="demonstration">默认</span>
      <el-slider v-model="value1"></el-slider>
    </div>
    <div class="block">
      <span class="demonstration">自定义初始值</span>
      <el-slider v-model="value2"></el-slider>
    </div>
    <div class="block">
      <span class="demonstration">隐藏 Tooltip</span>
      <el-slider v-model="value3" :show-tooltip="false"></el-slider>
    </div>
    <div class="block">
      <span class="demonstration">格式化 Tooltip</span>
      <el-slider v-model="value4" :format-tooltip="formatTooltip"></el-slider>
    </div>
    <div class="block">
      <span class="demonstration">禁用</span>
      <el-slider v-model="value5" disabled></el-slider>
    </div>

    <h2>离散值</h2>
    <p>选项可以是离散的。改变step的值可以改变步长，通过设置 show-stops 属性可以显示间断点</p>
    <div class="block">
      <span class="demonstration">不显示间断点</span>
      <el-slider v-model="value6" :step="10"></el-slider>
    </div>
    <div class="block">
      <span class="demonstration">显示间断点</span>
      <el-slider v-model="value7" :step="10" show-stops></el-slider>
    </div>

    <h2>带有输入框</h2>
    <p>通过输入框设置精确数值。设置show-input属性会在右侧显示一个输入框</p>
    <div class="block">
      <el-slider v-model="value8" show-input></el-slider>
    </div>

    <h2>范围选择</h2>
    <p>支持选择某一数值范围。设置range即可开启范围选择，此时绑定值是一个数组，其元素分别为最小边界值和最大边界值</p>
    <div class="block">
      <el-slider v-model="value9" range show-stops :max="10"></el-slider>
    </div>

    <h2>竖向模式</h2>
    <p>设置vertical可使 Slider 变成竖向模式，此时必须设置高度height属性</p>
    <div class="block">
      <el-slider v-model="value9" vertical height="200px"></el-slider>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        value1: 0,
        value2: 50,
        value3: 36,
        value4: 48,
        value5: 42,
        value6: 0,
        value7: 0,
        value8: 0,
        value9: [4, 8],
        value10: 0
      }
    },
    methods: {
      formatTooltip(val) {
        return val / 100;
      }
    }
  }
</script>
