<template>
  <div id="app">
    <h1>TimePicker 时间选择器</h1>
    <p>用于选择或输入日期</p>

    <h2>固定时间点</h2>
    <p>提供几个固定的时间点供用户选择。使用 el-time-select 标签，分别通过star、end和step指定可选的起始时间、结束时间和步长</p>
    <el-time-select v-model="value1" :picker-options="{ start: '08:30', step: '00:15', end: '18:30' }" placeholder="选择时间"></el-time-select>

    <h2>任意时间点</h2>
    <p>可以选择任意时间。使用 el-time-picker 标签，通过selectableRange限制可选时间范围。提供了两种交互方式：默认情况下通过鼠标滚轮进行选择，打开arrow-control属性则通过界面上的箭头进行选择。</p>
    <el-time-picker v-model="value2" :picker-options="{ selectableRange: '18:30:00 - 20:30:00' }" placeholder="任意时间点"></el-time-picker>
    <el-time-picker v-model="value3" arrow-control :picker-options="{ selectableRange: '18:30:00 - 20:30:00' }" placeholder="任意时间点"></el-time-picker>

    <h2>固定时间范围</h2>
    <p>若先选择开始时间，则结束时间内备选项的状态会随之改变</p>
    <el-time-select v-model="startTime" :picker-options="{ start: '08:30', step: '00:15', end: '18:30' }" placeholder="起始时间"></el-time-select>
    <el-time-select v-model="endTime" :picker-options="{ start: '08:30', step: '00:15', end: '18:30', minTime: startTime }" placeholder="结束时间"></el-time-select>

    <h2>任意时间范围</h2>
    <p>可选择任意的时间范围。添加is-range属性即可选择时间范围，同样支持arrow-control属性。</p>
    <el-time-picker is-range v-model="value4" range-separator="至" start-placeholder="开始时间" end-placeholder="结束时间" placeholder="选择时间范围"></el-time-picker>
    <el-time-picker is-range v-model="value5" arrow-control range-separator="至" start-placeholder="开始时间" end-placeholder="结束时间" placeholder="选择时间范围"></el-time-picker>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        value1: '',
        value2: new Date(2016, 9, 10, 18, 40),
        value3: new Date(2016, 9, 10, 18, 40),
        startTime: '',
        endTime: '',
        value4: [new Date(2016, 9, 10, 8, 40), new Date(2016, 9, 10, 9, 40)],
        value5: [new Date(2016, 9, 10, 8, 40), new Date(2016, 9, 10, 9, 40)]
      };
    }
  }
</script>
