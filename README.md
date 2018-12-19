# @mathewparet/vue-bs-disabled

> A Vue.Js directive to disable bootstrap controls. Unlike normal disable property of control buttons, bootstrap requires disabled added to the class to get the control to be disabled. This is useful mostly when you need to disable some controls in VUE based on certain conditions.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

## Installation
``` bash
npm i @mathewparet/vue-bs-disabled
```

## Initial Configuration Usage

``` js
// In your App.js
import Vue from 'vue';
import BsDisabled from '@mathewparet/vue-bs-disabled';
Vue.use(BsDisabled)
```

To use the directive simply add ```v-bs-disabled``` to the corresponding element with the required condition.

## Simple Usage Example

``` html
<div>
    <a class="btn btn-primary" v-bs-disabled="1==1">This button is disabled</a><br>
    <a class="btn btn-primary" v-bs-disabled="1==0">This button is enabled</a><br>
    <a class="btn btn-primary" v-bs-disabled.hidden="1==1">This button is hidden</a><br>
    <a class="btn btn-primary" v-bs-disabled.hidden="1==0">This button is enabled & visible</a><br>
</div>
```

## Advanced Usage Example

``` html
<div>
    <a class="btn btn-primary" v-bs-disabled="{hidden: false, condition: 1==1}">This button is disabled</a><br>
    <a class="btn btn-primary" v-bs-disabled="{hidden: false, condition: 1==0}">This button is enabled</a><br>
    <a class="btn btn-primary" v-bs-disabled="{hidden: true, condition: 1==1}">This button is hidden</a><br>
    <a class="btn btn-primary" v-bs-disabled="{hidden: true, condition: 1==0}">This button is enabled & visible</a><br>
</div>
```