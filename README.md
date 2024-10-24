# Timed keyframes

A [sass](https://sass-lang.com/) mixin for easily making animations with specific durations. 

### Usage
```scss
@include timed_keyframes(
    animated-colors,
    (red 1.5s),
    (blue 1.5s 1.5s),
    (red 0.5s),
    (cyan 1.5s 1s),
    (red 0.5s 2s),
  )
  using ($step) {
  @if $step == red {
    background: red;
  } @else if $step == blue {
    background: blue;
  } @else if $step == cyan {
    background: cyan;
  }
}
```

Result
```css
:root {
  --duration-animated-colors: 10000ms;
}

@keyframes animated-colors {
  0%,
  15% {
    background: red;
  }
  30%,
  45% {
    background: blue;
  }
  50% {
    background: red;
  }
  65%,
  75% {
    background: cyan;
  }
  80%,
  100% {
    background: red;
  }
}
```


### TODO
- [ ] Add more options
    - Options to auto-generate animation class
    - Option to customize duration's var prefix or maybe to just specifie the entire name
- [ ] Write tests
