# Sass
- To define variables use `$<variable_name>:value` and use it in any place like `background-color: $color-primary-dark`. Use this to define a theme and reuse a single color set across your entire website.
- Sass supports nesting which leads to a cleaner code like `nav { li { a {} } }` applies a style to `nav li a {}`.
- Use the `&` variable to define styles on parent element like `nav { &:hover {} }` defines the style for `nav:hover {}`.
- Mixins can be defined used `@mixin <name_of_mixin> { /*Code for mixin*/ }` and use `@include <name_of_mixin>` to include it in a CSS styling.
- Mixins can also take in argument `@mixin <name_of_mixin>($color) { background-color: $color }` so that they can be called by `@include <name_of_mixin>($color_primary_dark)`.
- Inheritance can be used by defining a `%nameOfBaseClass { properties... }` and then use it by `extends %nameOfBaseClass`. Use mixins over inheritance when possible as mixins replace code in the final location whereas inheritance or extends replace the base class code naming by replacing it with names where extends has been called.
- `@import <filename>.scss` can be used to import styles from another scss file.