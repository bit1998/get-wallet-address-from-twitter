# get-chain-address-from-twitter

first step: open twitter detail in chrome;

second step: open chrome dev tool -> console;

third step: copy the code below and press "enter";

wait a minite ，will get result in console;


code: 

```javascript
let result = [];
function unique(arr) {
  return Array.from(new Set(arr));
}
let lastPos = 0;
function take() {
  setTimeout(() => {
    window.scrollTo(0, window.scrollY + document.body.clientHeight);
    setTimeout(() => {
      const nowPos = window.scrollY;
      if (nowPos <= lastPos) {
        console.log("result", result);
      }
      lastPos = nowPos;
      const r = Array.from(
        document.querySelectorAll(
          ".r-kzbkwu >div:nth-child(2) >div:nth-child(2)"
        )
      )
        .map((ele) => {
          return ele.innerHTML.match(/0x[a-fA-F0-9]{40}/);
        })
        .filter((v) => v)
        .map((v) => v[0]);
      result = unique(result.concat(r));
      take();
    }, 500);
  },500);
}

take();

```
