```javascript
@font-face {
  font-family:xxxx;    //定义下面用这个字体写什么名字
  src: local(Poppins),
    url("./fonts/xx.ttf") format("truetype"),
    url() format(),
    ...;
  font-display:  ;
  font-style:   ;
  font-weight:    ;
}
```

- font-display: block 有较长文字不显示的时间（字体区域空白），比如3秒左右，字体还没加载完的话 就先切换备用字体？ swap 文字立即显示，字体加载完切换 fallback 极短时间文字不显示，如果几秒内加载完会切换，但是如果字体加载时间过长则不会切换了

