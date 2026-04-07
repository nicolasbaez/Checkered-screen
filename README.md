# Checkered-screen
We are pawns playing a game of life or death

![buh](https://github.com/nicolasbaez/Checkered-screen/blob/main/xp065.gif)
```javascript
setup = (_) => createCanvas((w = 500), w);
k = 0;
draw = (_) => {
  c = w / 10;
  background(0);
  q = 0;
  for (i = 0; i <= w; i += c)
    for (j = -w; j <= w; j += c) {
      q++;
      if (q % 2) {
        push();
        translate(i, j + k);
        rotate(map(j + k, 0, w, 0, 6 / k));
        s = map(sin(map(j + k, 0, w, 0, 3)), 0, 1, 1, c);
        rect(-s / 2, -s / 2, s, s);
        pop();
      }
    }
  if (k == 0) saveGif("xp065.gif", 500, { delay: 0, units: "frames" });
  k++;
  if (k > w) k = 0;
};
