# 84. Junction

[84. Junction](https://cssbattle.dev/play/84)

## Target

![image](https://github.com/thatmare/mycodegym/assets/113146161/7a821456-91a6-4fa2-8e34-d7f73f0880bc)


## Solución

```
<div class="across" id="left"></div>
<div class="across" id="right"></div>
<div class="down" id="bottom"></div>
<div class="down" id="top"></div>
<style>
  body {
    background-color: #191919;
  }
  .across {
    background-color: #A64942;
    width: 200px;
    height: 40px;
    border-radius: 40px;
  }
  #left {
    position: absolute;
    top: 130px;
    left: -20px;
  }
  #right {
    position: absolute;
    top: 130px;
    right: -20px;
  }
  .down {
    background-color: #FE5F55;
    width: 200px;
    height: 40px;
    border-radius: 40px;
  }
  #top {
    transform: rotate(270deg);
    position: absolute;
    bottom: 10px;
    left: 100px;
  }
  #bottom {
    transform: rotate(90deg);
    position: absolute;
    top: 10px;
    left: 100px;
  }
</style>
```
