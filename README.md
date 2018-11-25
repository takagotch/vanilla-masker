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
VMasker.toPattern(1099911111, "(99) 9999-9999");
VMasker.toPattern(12122000, "99/99/9999");
VMasker.toPattern(9991111101, "999.999.999-99");
VMasker.toPattern('ABC1234', "AAA-9999");
VMasker.toPattern('09GXXXXXXXXXX', "SS.SS.SSSSS.S.S.SSSSSS");
VMasker.toPattern('4', {pattern: "(999) 999-9999", placeholder: "x"});

var el = document.querySelector("input")
VMasker(el).maskPattern("(99) 9999-9999");
VMasker(el).unMask();

function inputHandler(masks, max, event) {
  var c = event.target;
  var v = c.value.replace(/\D/g, '');
  var m = c.value.length > max ? 1 : 0;
  VMasker(c).unMask();
  VMasker(c).maskPattern(masks[m]);
  c.value = VMasker.toPattern(v, masks[m]);
}
var telMask = ['(99) 9999-99999', '(99) 99999-9999'];
var tel = document.querySelector('#tel');
VMasker(tel).maskPattern(telMask[0]);
tel.addEventListener('input', inputHandler.bind(undefined, telMask, 14), false);
var docMask = ['999.999.999-999', '99.999.999/9999-99'];
var doc = document.querySelector('#doc');
VMasker(doc).maskPattern(docMask[0]);
doc.addEventListener('input', inputHandler.bind(undefined, docMask, 14), false);

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

