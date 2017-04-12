# vue-transfer-dom
> requires Vue v2.+

Transfer DOM to another place (eg. `<body>`).

Useful in some situations such as z-index management, see discussion [here](https://github.com/vuejs/vue/issues/2130).

## Installation
```sh
npm install vue-transfer-dom
```

## Usage

```js
Vue.use(VueTransferDom /*, {name: 'transferDom'}*/)

new Vue({
  template: '<div v-transfer-dom>foo</div>', // div will be appended to body(default)
})

// prepend to body
new Vue({
  template: '<div v-transfer-dom.prepend>foo</div>', // div will be prepended to body(default)
})
```

Move to a specific target element identifed by target's id:
```js
// append to specific place
new Vue({
  template: '<div v-transfer-dom:bar>foo</div>', // div will be appended to #bar(document.getElementById)
})

// prepend to specific place
new Vue({
  template: '<div v-transfer-dom:bar.prepend>foo</div>', // div will be prepended to #bar(document.getElementById)
})
```

**Note:** If appending or prepending to a non-existant target element, a console warning 
will be fired and the element will not be moved.

## Credits
Based on https://github.com/rhyzx/vue-transfer-dom

