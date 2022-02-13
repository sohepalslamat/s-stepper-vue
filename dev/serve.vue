<template>
  <div id="app">
    <SStepper class="stepper" v-model="step" :steps="steps"/>
      <h4 v-if="step == 1" class="content">{{steps[0].title}}</h4>
      <h4 v-if="step == 2" class="content">{{steps[1].title}}</h4>
      <h4 v-if="step == 3" class="content">{{steps[2].title}}</h4>
    <div class="actions">
      <button @click="step--">back</button>
      <button @click="step++">next</button>
      
    </div>
  </div>
</template>
<script lang="ts">
import Vue from 'vue';
// Uncomment import and local "components" registration if library is not registered globally.
import { SStepper } from '@/entry.esm';

export default Vue.extend({
  name: 'ServeDev',
  components: {
   SStepper,
  },
  data(){
    return{
      steps: [
        {title: "Submit Email"},
        {title: "Activation Code"},
        {title: "Change Password"}
      ],
      step: 1
    }
  }
});
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center; 
  color: #2c3e50;
  margin-top: 60px;
}
.actions{
  margin: 20px;
}
.stepper{
  width: 50%;
  margin: 1px auto;
}
.content{
  height: 150px;
  align-items: center;
  display: flex;
  justify-content: center;
}
</style>