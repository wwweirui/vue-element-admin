<template>
  <div>
    <transition name="el-fade-in">
      <div
        v-if="visible"
        :style="{
          'right': styleRight,
          'bottom': styleBottom,
        }"
        class="self-backtop"
        @click.stop="handleClick"
      />
    </transition>
  </div>
</template>

<script>
// import throttle from 'throttle-debounce/throttle'

// 缓动函数
// const cubic = (value) => Math.pow(value, 3)
// const easeInOutCubic = (value) =>
//   value < 0.5 ? cubic(value * 2) / 2 : 1 - cubic((1 - value) * 2) / 2

export default {
  name: 'SelfBackToTop',

  props: {
    visibilityHeight: { // 可见高度
      type: Number,
      default: 200
    },
    target: [String], // 挂载目标
    // 控制距离
    right: {
      type: Number,
      default: 40
    },
    bottom: {
      type: Number,
      default: 40
    }
  },

  data() {
    return {
      el: null, // 挂载元素对象
      container: null,
      visible: true
    }
  },
  computed: {
    styleBottom() {
      return `${this.bottom}px`
    },
    styleRight() {
      return `${this.right}px`
    }
  },

  mounted() {

  },

  methods: {
    // 初始化组件对象
    init() {

    },
    // 判断组件啥时候弹出
    onScroll() {

    },
    // 处理点击事件
    handleClick(e) {
      this.scroolToTop()
      this.$emit('click', e)
    },
    // 回到屏幕首页
    scroolToTop() {

    }

  }
}
</script>

<style scoped>
/* 不同的ui设计展示效果 */
.self-backtop {
  position: fixed;
  width: 88px;
  height: 88px;
  background: url('../../../assets/kunkunIcon/kunkun.png') no-repeat 0px 0px;
  background-size:100% 100%;
  cursor: pointer;
  animation: shake 1.5s ease infinite;
  /* animation 动画持续时间 缓动函数 无限循环 */
}

.self-backtop:hover {
  background-color: #d5dbe7;
}

/* 使用animation属性和@keyframes规则来创建晃动效果。@keyframes允许你定义动画的帧，而animation属性用于将这些帧应用到元素上。 */
@keyframes shake {
  0%, 100% {
    transform: translateX(0);
  }
  10%, 30%, 50%, 70%, 90% {
    transform: translateX(-10px);
  }
  20%, 40%, 60%, 80% {
    transform: translateX(10px);
  }
}
</style>
