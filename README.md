# lego-scss

Building blocks for your scss code - Basic functions to increase reusability of code

## Installation

1. Run npm install lego-scss
2. Include in your main scss file by @import "lego-scss";

## Usage
#### - Common functions

1. font-face: Initialize font-family, font-size, font-weight, font-style and color 
    
  ```scss
  @include font-face(font-size, color, font-weight, font-style, font-family)
  ```
  All params are optional. If null is sent for any variable, it will fall back to "inherit"

2. positioning - Align left, right, top, bottom or center

  ```scss
  @include positioning(left/right/center, top/center/bottom)
  ```

3. center-block - Align a block element at the center

  ```scss
  @include center-block
  ```
  Allow centering of a block element

4. background-gradient - Apply a background gradient by specifying the start color, end color and orientation

  ```scss
  @include background-gradient(start-color, end-color, horizontal/vertical)
  ```

5. ellipsis - Truncate a text and show ellipsis

  ```scss
  @include ellipsis(max-width)
  ```


#### - Responsiveness

1.  for-phone-only: < 600px
2.  for-tablet-portrait-up: >=600px
3.  for-tablet-landscape-down: <=767px
4.  for-tablet-landscape-up: >=767px
5.  for-desktop-down: <=991px
6.  for-desktop-up: >=992px
7.  for-big-desktop-down: <=1199px
8.  for-big-desktop-up: >=1200px
9.  width-less-than($size): <=$size
10. width-more-than($size): >=$size
11. width-in-between($minSize, $maxSize): <=$minSize and >=$maxSize

#### - Common Shapes

1. Square

  ```scss
  @include scss-square(size, color)
  ```

2. Cirlces

  ```scss
  @include scss-circle(size, color)
  ```

3. Triangles

  ```scss
  @include scss-triangle(size1, size2, direction, color)
  ```
  The direction which the triangle is pointing can be - up/bottom/left/right/top-left/top-right/bottom-left/bottom-right


## Examples

```scss
.foo {
  font-size: 2rem;
  @include for-tablet-landscape-down {
    font-size: 1.2rem;
  }
  @include for-mobile-only {
    font-size: 1rem
  }
}
.foo1 {
  @include width-more-than(1200px) {
    width: 80%;
  }
  @include width-in-between(601px, 1199px) {
    width: 90%;
  }
  @include width-less-than(600px) {
    width: 100%;
  }
}
```
will transform to
```css
.foo {
  font-size: 2rem;
}
@media screen and (max-width: 767px) {
  .foo {
    font-size: 1.2rem;
  }
}
@media screen and (max-width: 600px) {
  .foo {
    font-size: 1rem;
  }
}
@media screen and (min-width: 1200px) {
  .foo1 {
    width: 80%;
  }
}
@media screen and (min-width: 601px) and (max-width: 1199px) {
  .foo1 {
    width: 90%;
  }
}
@media screen and (max-width: 600px) {
  .foo1 {
    width: 100%;
  }
}
```

## Contributing

Pull requests and feature requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT](https://github.com/sagnikpaul28/scss-responsive-helper/blob/master/License)
