# 参考

- https://lab.sonicmoov.com/markup/animation-library-tweenmaxjs/

# ロゴを書く

dasharrayをロゴのパスの長さと同じにし、さらにdashoffsetをパスの長さだけ指定する。プラスの値がマイナス位置となる。<br>
dashoffsetをマイナスから０にすることでアニメーションされる。下記は線をアニメーションで塗る例。

```html
<line class="line2" x1="0" y1="0.5" x2="395.9" y2="0.5"/>
```

```css
.myline{
  fill: none;
  stroke: blueviolet;
  stroke-width: 3;
}
```

```js
  (()=>{
    const myline = document.querySelectorAll(".myline");
    let width = 0;
    for(line of myline){
      width = line.getTotalLength();
      line.style.strokeDasharray = width;
      line.style.strokeDashoffset = width;
      setTimeout(()=>{
        line.style.strokeDashoffset = 0;
        line.style.transition = "stroke-dashoffset 1s";
      },1000)
    }
  })();
```

- stroke-dasharray

破線の間隔

- stroke-dashoffset

破線の開始位置
