
```js
let inner = document.querySelector(".inner");
let log = document.querySelector(".log");

function setCoords(e, type) {
  let idX = type + "X";
  let idY = type + "Y";

  document.getElementById(idX).innerText = e[idX];
  document.getElementById(idY).innerText = e[idY];
}
```



`setCoords()` 

```js
function update(e) {
  setCoords(e, "offset");
  setCoords(e, "client");
  setCoords(e, "page");
  setCoords(e, "screen");
}

inner.addEventListener("mouseenter", update, false);
inner.addEventListener("mousemove", update, false);
inner.addEventListener("mouseleave", update, false);
```



```html
<div class="outer">
  <div class="inner">
    <div class="log">
      <p>
        Offset-relative: <span id="offsetX">0</span>,
        <span id="offsetY">0</span>
      </p>
      <p>
        Client-relative: <span id="clientX">0</span>,
        <span id="clientY">0</span>
      </p>
      <p>
        Page-relative: <span id="pageX">0</span>,
        <span id="pageY">0</span>
      </p>
      <p>
        Screen-relative: <span id="screenX">0</span>,
        <span id="screenY">0</span>
      </p>
    </div>
  </div>
</div>
```

### CSS


```css
.outer {
  width: 1000px;
  height: 200px;
  background-color: red;
}

.inner {
  position: relative;
  width: 500px;
  height: 150px;
  top: 25px;
  left: 100px;
  background-color: blue;
  color: white;
  cursor: crosshair;
  user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  -webkit-user-select: none;
}

.log {
  position: relative;
  width: 100%;
  text-align: center;
}
```



- [Using CSS transforms](/en-US/docs/Web/CSS/CSS_Transforms/Using_CSS_transforms): how to alter a coordinate system
- Coordinates of a mouse event:

  - {{domxref("MouseEvent.offsetX")}} and {{domxref("MouseEvent.offsetY")}}
  - {{domxref("MouseEvent.clientX")}} and {{domxref("MouseEvent.clientY")}}
  - {{domxref("MouseEvent.pageX")}} and {{domxref("MouseEvent.pageY")}}
  - {{domxref("MouseEvent.screenX")}} and {{domxref("MouseEvent.screenY")}}
