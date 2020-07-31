# scss-responsive-helper

Simple boilerplate SCSS framework to help write media queries in scss

## Installation

1. Run npm install scss-responsive-helper
2. Include in your main scss file by @import "scss-responsive-helper";

## Usage
#### - Mixins

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
