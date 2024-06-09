# hydra-experiments


## Basic Snippets
```js
osc(22, 0.8, [0.1, 1.0].smooth(1))
  .color(1.14, [0.1, 0.8].smooth(1), () => a.fft[0]*4)
  .mul(a)
  .out(o0);
```

```js
src(s0).pixelate(30,30).modulate(noise(1), 1).out();
```

```js
s0.initCam();
s1.initScreen();

src(s0).modulatePixelate(noise(5), 30).diff(src(s1)).out();
```

```js
s0.initCam(0)


a.setScale(1)
a.setBins(8)

src(s0)
  //.modulate(noise(4))
  //.thresh(0.1)
  .diff(src(s0).modulate(noise(5)), 3)
  .modulate(osc(20, 0.2, 2))

  .modulate(voronoi(20, 3))
  //.rotate(()=>1600*Math.PI*time)
  .out()
```

// s0.initCam() //initialize webcam as external source 's0'

// a.setBins(6)

// a.setBins(8)
//a.setScale(0.1)
// osc(110, 0.1,()=>a.fft[7]*3).modulate(noise(), ()=>a.fft[0]).out(o0)

noise([1,100].smooth()).pixelate(20,20).modulate(prev(), 1).out();



// a.show();

// osc(10, 0, () => a.fft[2]*6)
//   .out()

// src(s0).out() // use external source 's0' inside Hydra
