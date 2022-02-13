# s-stepper-vue

[![vue 2](https://img.shields.io/badge/vue-2-42b983.svg?style=flat-square)](https://vuejs.org)
[![npm](https://img.shields.io/npm/v/s-stepper-vue.svg?style=flat-square)](https://www.npmjs.com/package/s-stepper-vue)
[![npm](https://img.shields.io/npm/dt/s-stepper-vue.svg?style=flat-square)](https://www.npmjs.com/package/s-stepper-vue)
<!-- [![Codacy grade](https://img.shields.io/codacy/grade/3d15a7c11bfe47c69a2aed93cc67cc29.svg?style=flat-square)](https://www.codacy.com/app/LouisMazel/s-stepper-vue) -->

> A beautiful stepper made with VueJS
![s-stepper-vue](./public/s-stepper-vue.gif)

## Installation

### Using yarn

`yarn add s-stepper-vue`

### Using npm

`npm i --save s-stepper-vue`

## Usage

### ES6 Modules / CommonJS

```js
import {SStepper} from 's-stepper-vue';
Vue.component('S-stepper', SStepper);
```

```html
<SStepper v-model="step" steps="steps" />
```

```javascript
export default {
  data(){
    return{
        steps: [
            {title: 'step one'},
            {title: 'step tow'},
            {title: 'step three'}
        ],
        step: 1
    }
  }
}
```

## Props API

| Props                | Type               | Required | Default |
|----------------------|--------------------|--------|----------|
| v-model              | Int                | true   | 1        |
| steps                | Array`<object>`    | true   | null     |
| color                | String `HEX`       | no     | #E30A17  |
| height               | int                | no     | 15       |
| backgroundColor      | String `HEX`       | no     | #F8F8F8  |



(1) Ex : 1,2 .. it is step number

(2) Ex : 
```javascript
steps: [
    {title: 'step one'},
    {title: 'step tow'},
    {title: 'step three'}
]
```
title is required.

--------------------------------

@Vuango Simply Learn