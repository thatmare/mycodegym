# 94. Ripples

[CSS Battle 94. Ripples](https://cssbattle.dev/play/94)

## Target

![image](https://github.com/thatmare/mycodegym/assets/113146161/93304072-5f01-454f-8146-7a093297aa66)


## Solución

```
<div>
  <div class="five">
    <div class="four">
      <div class="three">
        <div class="two">
            <div class="one"></div>
        </div>
      </div>
    </div>
  </div>
</div>
<style>
  body {
    background-color: #0E2E2C;
    display: flex;
    justify-content: center;
    align-items: center;
  }  
  .one {
    background-color: #F3AC3C;
    width: 40px;
    height: 40px;
    border-radius: 40px;
    border: 8px solid #0E2E2C;
  }
  .two {
    background-color: #F3AC3C;
    width: 80px;
    height: 80px;
    border-radius: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 10px solid #0E2E2C;
  }
  .three {
    background-color: #998235;
    width: 120px;
    height: 120px;
    border-radius: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 12px solid #0E2E2C;
  }
  .four {
    background-color: #F3AC3C;
    width: 160px;
    height: 160px;
    border-radius: 120px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 14px solid #0E2E2C;
  }
  .five {
    background-color: #F3AC3C;
    width: 200px;
    height: 200px;
    border-radius: 160px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 16px solid #0E2E2C;
  }
</style>
```
