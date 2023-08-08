# mixins.scss
##1.  Responsive-max 
### description
**mixin for max responsive design **
-  var $width-pixels to set the screen size
-  var $width-em to convet px to em

#### code

```css
@mixin responsive-max($width-pixels) {
  $width-em:  calc($width-pixels/16);
  @media (max-width:'#{$width-em}em') {
    @content;
  }
}

```

### usage
```css
    @include responsive-max(767) {
      span{
        font-size: 16px ;
      }
    }
```