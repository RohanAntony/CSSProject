# Advanced CSS
- Project that is used to understand advanced CSS.

### Box model
- Set `box-sizing: border-box` to define that the element should include its `border` and `padding` while determining its `width` and `height` attribute.
- `display:flex` , `display:list-item` or `display:table` all are `display:block` and fill the entire page taking one element per line.
    - `display: block` can be used to set `height: <value>` but `width` is set 100%
- `display:inline` takes only space that is required and neither `height`, nor `width` property can be set. No line breaks are added.
    -  `paddings` and `margins` are only applied horizontally.
- `display:inline-block` have the property of no line breaks and take only content space but box model is applied as per block. `margin` and `padding` along with `height` and `width` can be set.

### Fonts and text
- `font-family: "Lato", sans-serif` states to use Lato if available and if not default to sans-serif.
- `font-weight: 400` defines the weight and `font-size` sets the size of font.
- `text-decoration: none` to remove underline.
- `text-transform: uppercase` to convert the text to uppercase.
- Value for font-size is inherited from the parent. 

### Background
- `background-image: url(...)` can be used to set an image as the background.
- `background-size: cover` states that the image must fit to fill the page.
- `background-position: top | bottom | left | right | center` states what portion of the image should be focused and kept when screen size changes.

### Positioning
- `position: absolute` states that the element is positioned absolutely with respect to its `top` and `left` defined values.
- `position: relative` states that the element is positioned relative to its normal positioning.
- `position: absolute` can only be defined on a child of `position: relative` element;
- Default positioning is `relative` and elements are laid out according to their source order.
- `top: 10px` or `left: 10px` can be used to move from a intial position.
- `transform: translateX(-10px)` or `transform: translateY(10px)` can also be used to move the element from its initial positioning. 

### Clipping
- `clip-path: polygon(0 0, 100% 0, 0 100%)` clips a triangular polygon. Use the polygon method to define accurate clipping.

### Animation
- `@keyframes <animationName> { 0% { <property_1>: <initial_value> } 100% { <property_1>: <final_value> }}` can be used to define an animation which can be used on any element.
- `animation: <animationName> 1.2s ease-in;` can be used to define the animation that should be performed on that element.
- For basic animation use `transition: all 1.2s` to perform transition from present state to psuedo selectors like `:hover` or `:after` (which is for on click)
- Add `animation-fill-mode: backwards` to set the 0% in the animation immediately while the page renders the element instead of waiting for delay.

### Specifity
- Each one has a higher power then the one below
    1. Inline Style
    2. IDs
    3. Classes, psuedo-classes, attribute
    4. Elements, psuedo-elements
- If specificity is same for 2 elements, the last declarations written will be used.
- To override specifity completely, use `!important` which is only to be used as last resort.

### Measurements
- `rem` is based on root font size which is default set to 16px and by the browser.
- `em` is based on font size. Using it on `font-size` sets it 
- `vh` is for viewport height.
- `vw` is for viewport width.
- One can also use `%` and `px` directly although it is not recommended to use px directly.