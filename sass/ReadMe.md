# Sass
- To define variables use `$<variable_name>:value` and use it in any place like `background-color: $color-primary-dark`. Use this to define a theme and reuse a single color set across your entire website.
- Sass supports nesting which leads to a cleaner code like `nav { li { a {} } }` applies a style to `nav li a {}`.
- Use the `&` variable to define styles on parent element like `nav { &:hover {} }` defines the style for `nav:hover {}`.
- Mixins can be defined used `@mixin <name_of_mixin> { /*Code for mixin*/ }` and use `@include <name_of_mixin>` to include it in a CSS styling.
- Mixins can also take in argument `@mixin <name_of_mixin>($color) { background-color: $color }` so that they can be called by `@include <name_of_mixin>($color_primary_dark)`.
- Inheritance can be used by defining a `%nameOfBaseClass { properties... }` and then use it by `extends %nameOfBaseClass`. Use mixins over inheritance when possible as mixins replace code in the final location whereas inheritance or extends replace the base class code naming by replacing it with names where extends has been called.
- `@import <filename>.scss` can be used to import styles from another scss file.

- Use `calc(100% - #{$variable})` to perform operations to determine values dynamically.

### Categories
- abstracts: should contain variables, mixins and functions.
- base: should contain 
    - base(*, html, body), 
    - animations, 
    - typography: anything realted to font's and text modifications.
    - utilities: classes which are not useful on their own but act as wrapper to solve problems like centering text.
- components: should contain reusable components across the sites such as buttons, textbox and so on.
- layouts: should contain components that are used as part of layouts such as header and footer. These can also be kept in component but better here.
- pages: should contain different page specific css for each pages.

### Psuedo selectors
- Use `:last-child` to define on last child and `:first-child` for first one.
- Use `:not(<other psuedo selector>)` to define on elements no in psuedo selector.

### Gradient text
- Set `background-image` for a text to a gradient like `background-image: linear-gradient(to right, <color1>, <color2>)`
- Use `-webkit-background-clip: text;` to clip the background only to the foreground text.
- Set `color: transparent;` to make the background clipped text visible. This will set the gradient on the text.

### Implementing a grid
- Create a `row` element which spans `max-width: <max-width-value>` and `margin: 0 auto` to center the element and this acts as the container.
- IMPORTANT: Set the font-size of this parent/container element to hide additional spaces inbetween child elements.
- For the child elements that go into the container, set `display:inline-block;` to float the elements one after the other. This property can be defined for `[class^="col-"]` which checks for classes starting with "col-" naming convention.
- To divide the container into
    - 1 column in 2 rows, width = (100% - gutter_horizontal) / 2
    - 1 column in 3 rows, width = (100% - 2 * gutter_horizontal) / 3
    - 1 column in 4 rows, width = (100% - 3 * gutter_horizontal) / 4
    - 2 column in 3 rows, width = 2 * (1 column in 3 rows) + gutter_horizontal
    - 2 column in 4 rows, width = 2 * (1 column in 4 rows) + gutter_horizontal
    - 3 column in 4 rows, width = 3 * (1 column in 4 rows) + 2 * gutter_horizontal
- On understanding the above logic, one can define or implement n-column based design.

### Implementing a rotating card
- Position 2 divs of same size overlapping each other using absolute. Define one card as front and one card as back with respective classes.
- Initialize the back class with default `transform: translateY(180deg)` to turn one div upside down hiding its content.
- Set `backface-visibility: hidden` on both cards to not display content when turned upside down.
- On hover, rotate the backfaced class to 0 deg `transform: translateY(0)`(original position) and the frontfaced class to -180deg `transform: translateY(-180deg)`. This hides the front faced class.
- Use `perspective: 1500px | 150rem` on the parent class to add the perspective of rotating the card instead of just a plain animation from one to another.
- View card.scss under components to see more details.
- Remember to set the height for parent class as both child class are set to absolute positioning making the parent class height to 0. Set the size to whatever is the child class height.