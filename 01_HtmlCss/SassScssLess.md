# Sass or Scss or less learning note

### 1.Store variables
```scss
  $color-primary: blue;

  h1 {
    font-size: 3rem;
    font-weight:600;
    
    color: $color-primary;

  }

```

### 2. Css nest in scss/sass/less
  | noted: don't nest too deep.

```scss

  body{
    margin:0;
    padding:0;
    background:#f2f2f2;

    header{
      border:1px solid #999;
      box-shadow: 0 0 15px rgba(0,0,0,0.3);

      h1{
        font-size:2rem;
        color:#555;
      }
    }
  }

```

### 3. Reusable Css - function similar feature: @mixin

```scss
  @mixin box-shadow($x,$y,$blur, $offset, $color) {
  -webkit-box-shadow: $x,$y,$blur, $offset, $color;
  -moz-box-shadow: $x,$y,$blur, $offset, $color;
  -ms-box-shadow: $x,$y,$blur, $offset, $color;
  box-shadow: $x,$y,$blur, $offset, $color;
  }

  .box1{
    background:pink;
    box-shadow: @include box-shadow(0,0,15px,0,rgba(0,0,0,0.3))
  }

```

### 4. @if @else if and @else to conditionally manipulate style

> As I said above Mixin is a function similar feature in the JavaScipt, so the @if and @else keywords are analogous features too. They work within @mixin. **I think.**
```scss
  @mixin text-effect($val) {
    @if $val == danger {
      color: red;
    }
    @else if $val == alert {
      color: yellow;
    }
    @else if $val == success {
      color: green;
    }
    @else {
      color: black;
    }
  }

  h2{
    font-size:2rem;
    color: @include text-effect(danger)

  }

```

### 5. @for to create sass/scss loop

```scss
  @for $i from 1 through 12 {
    .col-#{$i} { width: 100%/12 * $i; }
  }

  // result as following:
  .col-1 {
    width: 8.33333%;
  }

  .col-2 {
    width: 16.66667%;
  }

  // ...

  .col-12 {
    width: 100%;
  }


```

another instance:
```html
  <style type="text/scss">
    @for $j from 1 through 5 {
      .text-#{$j}{
        font-size:15px*$j;
      }
    }
    /* .text-1{font-size:15px}
    .text-2{font-size:30px}
    .text-3{font-size:45px}
    .text-4{font-size:60px}
    .text-5{font-size:75px} */
  </style>
  
  <p class="text-1">Hello</p>
  <p class="text-2">Hello</p>
  <p class="text-3">Hello</p>
  <p class="text-4">Hello</p>
  <p class="text-5">Hello</p>

```

### 6.Use @each to map over items in a list

```scss
  @each $color in blue, red, green {
    .#{$color}-text {color: $color;}
  }

  // 
  $colors: (color1: blue, color2: red, color3: green);

  @each $key, $color in $colors {
    .#{$color}-text {color: $color;}
  }

  ```
> Generate css classes as follow
``` css
  .blue-text {
    color: blue;
  }

  .red-text {
    color: red;
  }

  .green-text {
    color: green;
  }

```
> For instance
```html
<style type='text/sass'>
$colors:(color1:blue,color2:black,color3:red);
@each $key, $color in $colors{
  .#{$color}-bg { background-color: $color};
}

  div {
    height: 200px;
    width: 200px;
  }
</style>

<div class="blue-bg"></div>
<div class="black-bg"></div>
<div class="red-bg"></div>

```

### 7. Condition keyword @while
```scss
  $x:1;
  @while $x < 13 {
    .col-#{$x} { width:100%/12 *$x;  }
    $x:$x+1;
  }
  // the same result as @for loop will come out.
```

### 8. Split styles into smaller chunks with partials
>BENOTICE: Underscore(_)character, which tells Sass(scss) it is a small segement of css and not to convert it to CSS file. Also, Sass(scss) files end with the .scss extension.
```scss
// Write an @import statement to import a partial named _minins.scss into the main.scss file.
// In the main.scss file
@import 'mixins'

```

### 9. Extend(inherent) one set of css styles to anther class
```scss
  .panel{
    background-color:red;
    height:70px;
    border:2px solid green;
  }

  .big-panel{
    @extend .panel;
    width:150px;
    font-size:2em;
  }
```

