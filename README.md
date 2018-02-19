# datepicker (vue2)

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

This demo is based on vue-cli: vue init webpack-simple test-tree

A simple vue JS sliding button implementing font awesome and Bootstrap V4.

Available properties:

- "name"        : {type: String, default : ''}, // input field name
- "buttonbg"    : {type: String, default : ''}, // sliding button background color
- "buttonfg"    : {type: String, default : ''}, // sliding button foreground color
- "texton"      : {type: String, default : ''}, // text displyed when true (ON)
- "textonbg"    : {type: String, default : ''}, // text ON background color
- "textonfg"    : {type: String, default : ''}, // text ON foreground color
- "textoff"     : {type: String, default : ''}, // text displayed when false (OFF)
- "textoffbg"   : {type: String, default : ''}, // text OFF background color
- "textofffg"   : {type: String, default : ''}, // text OFF foreground color
- "value"       : {type: Boolean, default: false}, // slider switch initial value
- "rounded"     : {type: Boolean, default: true}, // rounded borders when true
- "borders"     : {type: Boolean, default: true}, // show borders when true
- "stylecl"     : {type: Boolean, default: true}, // style slider with classes like twbs v4 classes or ...
- "twbuttonbg" : {type: String, default : 'bg-secondary'}, // sliding button background color class
- "twbuttonfg" : {type: String, default : ''}, // sliding button foreground color class
- "twtextonbg" : {type: String, default : 'bg-primary'}, // text ON  background color class
- "twtextonfg" : {type: String, default : ''}, // text ON foreground color class
- "twtextoffbg": {type: String, default : 'bg-danger'}, // text OFF  background color class
- "twtextofffg": {type: String, default : ''}, // text OFF foreground color class


Works with claasses as with direct formattings with colors
