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

```js
s0.initCam()

osc(10, 1., ()=>2*mouse.x/width)
  //.modulateScale(osc(10,0.2,()=>2*mouse.y/height).kaleid(12))
  //.repeat(6,4)
  //.modulate(o0, 0.03)
  .modulateKaleid(shape(4, 0.1,1))
  .modulate(src(s0), () => 8+Math.sin(time))
  .out(o0)
```

```js
a.setBins(4);
a.setSmooth(.8);
a.setScale(59);

src(s0)
	.rotate(()=>-.6*time+10*a.fft[0])
	.mask(shape(0.056).scale(2.1, 1.6))
	.scale(2.94)
	.modulate(noise(1.797, () => 0.177 * a.fft[0] * a.fft[3]))
	.modulate(src(s0).scale(() => 1.8 + 2*a.fft[0]).rotate(()=>.7*time+10*a.fft[2]))
	.modulateHue(osc(10, 10, 10))
	.out();
```
