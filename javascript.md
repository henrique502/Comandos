# get center popup
```javascript
function getCenter(width, height) {
  const windowLeft = window.screenLeft ? window.screenLeft : window.screenX;
  const windowTop = window.screenTop ? window.screenTop : window.screenY;
  const left = windowLeft + (window.innerWidth / 2) - (width / 2);
  const top = windowTop + (window.outerHeight / 2) - (height / 2);
  return { width, height, left, top };
}
```
