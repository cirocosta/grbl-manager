# grbl-manager

> manages grbl using yaspm's devices

Being `device` a [yaspm's](https://github.com/cirocosta/yaspm) device:

```javascript
var grbl = new Grbl(device);

grbl
  .init()
  .on('status', function (status) {
    console.log(status);
  })
  .on('error', function (err) {
  console.log(err);
  }).on('ok', function () {
    console.log('ok');
  });

setTimeout(function () {
  grbl.process('G1 X10 Y10\n');
}, 300);

tmr = setInterval(function () {
  grbl.process('?\n');
}, 300);
```
