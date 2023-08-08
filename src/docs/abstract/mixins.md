# mixins.scss

## 1. Responsive-max

### description

 mixin for max responsive design 

- var $width-pixels to set the screen size
- var $width-em to convet px to em

#### code

```css
@mixin responsive-max($width-pixels) {
  $width-em: calc($width-pixels/16);
  @media (max-width:'#{$width-em}em') {
    @content;
  }
}
```

### usage

```css
@include responsive-max(767) {
  span {
    font-size: 16px;
  }
}
```

## 2. Responsive bootstrap

### description

they are defined with the aim of allowing the SCSS/CSS code of your app' behave accordingly to your user's device width,
the breakpoints I used were inspired by Bootstrap 

- var $breakpoint to set the type of screen size

#### code

```css
@mixin responsive($breakpoint) {
  @if $breakpoint == smartphone-portrait {
    @media only screen and (max-width: 575.98px) {
      @content;
    }
  }
  @if $breakpoint == smartphone-landscape {
    @media only screen and (min-width: 575.99px) and (max-width: 767.98px) {
      @content;
    }
  }
  @if $breakpoint == tablet {
    @media only screen and (min-width: 767.99px) and (max-width: 1199.97px) {
      @content;
    }
  }
  @if $breakpoint == laptop {
    @media only screen and (min-width: 1199.98px) and (max-width: 1399.98px) {
      @content;
    }
  }
  @if $breakpoint == desktop {
    @media only screen and (min-width: 1399.99px) {
      @content;
    }
  }
}
```

### usage

```css
.myCLass {
  @include responsive(smartphone-portrait) {
    font-size: 15px;
  }
}
```
