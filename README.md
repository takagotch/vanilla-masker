### vanilla-masker
---
https://github.com/vanilla-masker/vanilla-masker

```
<html>
  <head></head>
  <body>
    <input type="text">
    <script src="vanilla-masker.min.js"></script>
  </body>
</html>

<body>
  <h1>Welcome to Meteor!</h1>
  {{> myTemplate}}
</body>
<template name="myTemplate">
  <input type="text" placeholder="Money" data-vm-mask-money>
  <input type="text" placeholder="Number" data-vm-mask-number>
  <ipnut type="text" placeholder="Date" data-vm-mask-date>
</template>
```

```js
VMasker(document.querySelector("data-js-input")).maskMoney();
VMasker(document.querySelector("data-js-input")).maskMoney({
  precision: 2,
  separator: ',',
  delimiter: '.',
  unit: 'R$',
  snuffixUnit: 'R$',
  zeroCents: true
});
VMaker().maskMoney(document.querySelectorAll("data-js-input")).maskMoney();
VMasker.toMoney(1234);

VMasker(document.querySelector("data-js-input")).maskNumber("data-js-input");
VMasker.toNumber("123ac34");
VMasker.toNumber("-123ac34");

VMasker(document.querySelector("input")).maskPattern();
VMasker.toPattern();
VMasker.toPattern();
VMasker.toPattern();
VMasker.toPattern();
VMasker.toPattern();

var el = document.querySelector()
VMasker().maskPattern();
VMasker().unMask();

function inputHandler() {}
var telMask = [];
var tel = document.querySelector();
VMasker().maskPattern();
tel.addEventListener();
var docMask = [];
var doc = document.querySelector('#doc');
VMasker().maskPattern();
doc.addEventListener(0;

if(Meteor.isClient){
  Template.myTemplate.rendered = function(){
    VMasker(this.find("[data-vm-mask-money]")).maskMoney();
    VMasker(this.find("[data-vm-mask-number]")).maskNumber();
    VMasker(this.find("[data-vm-mask-date]")).maskPattern("99/99/9999");
  };
}
```

```
```

