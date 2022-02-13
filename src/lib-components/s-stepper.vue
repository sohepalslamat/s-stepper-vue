<template>
  <div class="text-center">
    <div id="progressbar" :style="backgroundStyle">
      <div :style="style"></div>
    </div>
    <div id="title" class="px-0">
      <span
        v-for="(item, index) in steps"
        :key="index"
        :class="{ 'grey-text': index + 1 > step }"
      >{{ item.title }}</span>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from 'vue';

interface step {title: string;}

export default /*#__PURE__*/Vue.extend({
  name: 'SStepper',
  model: {
    prop: 'step',
    event: 'change'
  },
  props: {
    color: {
      type: String,
      default: '#E30A17'
    },
    height: {
      type: Number,
      default: 15
    },
    backgroundColor: {
      type: String,
      default: '#F8F8F8'
    },
    steps: {
      type: Array as () => Array<step>,
      required: true 
    },
    step: {
      type: Number,
      default: 1
    }

  },
  computed: {
    stepLength() {
      return 100 / this.steps.length
    },
    progressWidth() {
      const length = (this.stepLength * this.step) - 10

      return this.step === this.steps.length || length > 100 ? 100 : length
    },
    style() {
      return `
        width: ${this.progressWidth}%;
        background-color: ${this.color};
        height: ${this.height}px;
        
        `
    },
    backgroundStyle() {
      return `
        background-color: ${this.backgroundColor};
        
        `
    }

  },
  watch: {
    step(val) {
      let newVal:number = val 
      if(val <= 1) newVal = 1 
      else if ( val >= this.steps.length) newVal = this.steps.length
      this.$emit('change', newVal)
    }
  }
});
</script>

<style lang="scss" scoped>
#progressbar {
  border-radius: 13px;
  /* (height of inner div) / 2 + padding */
  padding: 4px;
  margin-bottom: 2px;
}

#progressbar > div {
  /* Adjust with JavaScript */
  border-radius: 10px;
}
#title {
  display: flex;
  justify-content: space-between;
  span {
    width: 80px;
    word-break: break-word;
  }
}
.grey-text {
  color: #9d9d9d;
}
.text-center {
  text-align: center;
}
</style>
