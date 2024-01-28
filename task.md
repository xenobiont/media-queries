# Task

In `_mixins.scss` file, define a mixins that will work as follows:

```scss
@include above(600px) {
	// some rules here
}

@include below(600px) {
	// some rules here
}

@include between(600px, 1200px) {
	// some rules here
}
```

And use them in main.scss code to show how they work.

e.g.

```scss
.element {
	@include above(600px) {
		background: green;
	}
}
```

should do the same, as

```scss
.element {
	@media screen and (min-width: 600px) {
		background: green;
	}
}
```

## Tip

use `@content` at-rule inside the mixins

## Advanced

Mixins should automatically convert px to em

Hiny: ou'll need strip-unit function to implement it

```scss
@function strip-unit($number) {
	@if type-of($number) == 'number' and not unitless($number) {
		@return $number / ($number * 0 + 1);
	}
	@return $number;
}
```
