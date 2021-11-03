# UUIDs-to-file-bookmarklet
Bookmarklet for generating a variable number of uuids and saving them to a text file

## About
Save as a browser bookmarklet to quickly generate multiple v4 UUIDs 

## Installation
- Create a new browser bookmark
- Set the `URL` to `javascript:` and the contents of `uuid.min.js`

```js
javascript:!function(){var n=new function(){function n(n){return 0|n*Math.random()}function t(t){for(var e="",o=0;o<t;++o)e+=n(16).toString(16);return e}this.generate=function(){return t(8)+"-"+t(4)+"-4"+t(3)+"-"+(3&n(16)|8).toString(16)+t(3)+"-"+t(12)}};var t=Number(window.prompt("How many UUIDs?"))||1,e="";!function n(t,e){t(),e&&--e&&n(t,e)}(()=>e+=`${e?"\n":""}${n.generate()}`,t),function(n,t){var e=document.createElement("a");e.href=window.URL.createObjectURL(new Blob([n])),e.download=t,document.body.appendChild(e),e.click(),e.parentNode.removeChild(e)}(e,`${t}xUUIDs.txt`)}();
```
![Bookmarklet](/bookmarklet.png)
