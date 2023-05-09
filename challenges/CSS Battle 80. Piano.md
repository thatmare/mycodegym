# 80. Piano

[CSS Battle 80. Piano](https://cssbattle.dev/play/80)

## Target

![image](https://github.com/thatmare/mycodegym/assets/113146161/f09852ed-323d-410e-93db-85deadcda8f3)

## Solución
98.7% match

```
<div class="container">
  <div class="rotation-container">
    <div class="white-key"></div>
    <div class="white-key"></div>
    <div class="white-key"></div>
    <div class="white-key"></div>
    <div class="white-key"></div>
    <div class="white-key"></div>
    <div class="white-key"></div>
  </div>
</div>
<div class="brown-container">
    <div class="dark-key"></div>
    <div class="dark-key"></div>
    <div class="dark-key"></div>
    <div class="dark-key"></div>
    <div class="dark-key"></div>
    <div class="dark-key"></div>
</div>
<style>
  body {
    background-color: #998235;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .container {
    background-color: #191919;
    width: 175px;
    height: 100px;
    border-radius: 10px;
  }
  .rotation-container {
    transform: rotate(90deg)
  }
  .white-key {
    background-color: #FFFFFF;
    width: 70px;
    height: 18px;
    margin: 6px 20px 0px 25px;
    border-radius: 5px;
  }
  .brown-container {
    transform: rotate(90deg);
    z-index: 1;
    position: absolute;
  }
  .dark-key:nth-child(4) {
    opacity: 0;
  }
  .dark-key {
    background-color: #191919;
    width: 36px;
    height: 15px;
    margin: 9px 0px 9px -16px;
  }
</style>
```
