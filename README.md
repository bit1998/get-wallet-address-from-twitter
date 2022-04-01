# get-chain-address-from-twitter

first step: open twitter detail in chrome;

second step: open chrome dev tool -> console;

third step: copy the code below and press "enter";

wait a minite ，will get result in console;

if you can not use this ,you can contact me at twitter https://twitter.com/0xbit1998

like this:



https://user-images.githubusercontent.com/102477984/161298388-84791ffe-ea03-4d93-b5bd-03ea52640829.mp4




code: 

```javascript
let result = [];
function unique(arr) {
  return Array.from(new Set(arr));
}
let lastPos = 0;
function take() {
  setTimeout(() => {
    window.scrollTo(0, window.scrollY + document.body.clientHeight/2);
    setTimeout(() => {
      const nowPos = window.scrollY;
      if (nowPos <= lastPos) {
        console.log("result", result);
        return;
      }
      lastPos = nowPos;
      const r = Array.from(
        document.querySelectorAll(
          "article.r-kzbkwu >div:nth-child(2) >div:nth-child(2)"
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
  },200);
}

take();

```

my wallet address: bit1998.eth

my wallet address: 0x6E46A15f467a80ede92969F7d7Cc623E740176AA
