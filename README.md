# CSS Cols
CSS grid and breakpoints.

## Installation

* `npm install`
* `npm start` in case you want to build grid and demo with your own values.

## How to link to your project

Import `src/scss/main.scss` to your project's main.scss file. In this case the [DartSass](https://sass-lang.com/dart-sass) is required.
```scss
@use "./node_modules/css-cols/src/scss/variables" as *;
@use "./node_modules/css-cols/src/scss/mixins" as *;
@use "./node_modules/css-cols/src/scss/cols" as *;
@use "./node_modules/css-cols/src/scss/functions" as *;
```

OR

Link built main.css to your site.

`<link rel="stylesheet" href="/css/main.min.css">`

## Usage
### Columns and devices
`{COL}` is a number from 1 to 12.

`{DEVICE}` is a device: 
- mobile 
- tablet
- tablet-landscape
- desktop
- desktop-big

### Default values of breakpoints
- "mobile": up to 599px, 
- "tablet": from 600px, 
- "tablet-landscape": from 900px, 
- "desktop": from 1200px, 
- "desktop-big": from 1800px

These values can be changed or you can add your own in `src/scss/_variables.scss`

### Classes
```scss 
.container {}
```

```scss
.row {}
```

```scss 
.col {}
```

```scss 
.col-{COL} {}
```

```scss 
.col-{DEVICE}-up {}
```

```scss 
.col-push-{COL}-{DEVICE}-up {}
```

```scss
.col-pull-{COL}-{DEVICE}-up {}
```

### Mixins
```scss 
@include breakpoint({DEVICE}) {}
```
### Examples
#### The same sizes of columns - all devices _including_ mobile
```html
<div class="row">
    <div class="col">col</div>
    <div class="col">col</div>
    <div class="col">col</div>
</div>
```

#### Various sizes of columns - all devices _including_ mobile
```html
<div class="row">
    <div class="col col-3">col-3</div>
    <div class="col col-4">col-4</div>
    <div class="col col-5">col-5</div>
</div>
```

#### Various sizes of columns - across all devices _except_ mobile. Mobile remains 100%.
```html
<div class="row">
    <div class="col col-12 col-4-tablet-up">col-12 col-4-tablet-up</div>
    <div class="col col-12 col-8-tablet-up">col-12 col-8-tablet-up</div>
</div>
```

#### Push & pull columns
```html
<div class="row">
    <div class="col col-6 push-1-desktop-up">col-6 push-1-desktop-up</div>
    <div class="col col-6 pull-2-desktop-up">col-6 pull-2-desktop-up</div>
</div>
```

### Demo
[Demo](https://wptom.com/demo/css-cols)

