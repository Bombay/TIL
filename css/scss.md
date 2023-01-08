## variables
```scss
&bg: #be4bdb
```

## nesting
```scss
.box {
  &:hover {
    color: red;
  }
  
  h1 {
    color: blue;
  }
}
```

## mixin
상황에 따라 다르게 코딩하고 싶을 때 사용
```scss
@mixin link($color) {
  text-decoration: none;
  color: $color;
  font-size: 16px;
  @if $color === red {
    background-color: green;
  } @else if $color === green {
    background-color: blue;
  }
}
```
```scss
a {
  @mixin link(red)
}
```

## extends
단순히 css를 재사용하고 이어서 추가하고 싶을 떄 사용
```scss
%button {
  border-radius: 15px;
  background-color: white;
}
```
```scss
a {
  @extend %button
}

button {
  @extend %button
}
```


## awesome mixins
```scss
@mixin responsive($device) {
  @if $device == 'somePhone' {
    @media screen and (min-width: 500px) and (max-width: 750px) {
      @content;
    }
  }
  @else if $device == 'someTablet' {
    @media screen and (min-width: 751px) and (max-width: 1024px) {
      @content;
    }
  }
}
```

```scss
h1 {
  @include responsive('somePhone') {
    color: blue;
  }
  
  @inlcude responsive('someTablet') {
    color: brown;
  }
}
```

https://github.com/colourgarden/awesome-scss#libraries-and-mixins
https://www.bourbon.io/

