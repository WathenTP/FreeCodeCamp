# Applied visual Design

Combines typography, graphics, animation and page layout. In web design, HTML gives semantics and structure to a page’s content. CSS controls the layout and appearance of it.

`text-align` this property controls the alignment on the page. Alignment can be justify, center, left or right.

The width of an element can be specified with the `width` property. Width can either have absolute or relative value e.g. `px` or `em`, respectively. Much like width, height can also be used as an attribute to changed the element.

`strong` makes the text bold and the browser applies the CSS font-weight: bold, to the element.

`u` tag gives an underline to the text and the browser applies the CSS text-decoration: underline.

`em` tag italicises the text, the browser applies the CSS font-style: italic.

`s` strike through tag puts a line through the text and the browser applies the CSS, text-decoration: line-through.

`hr` horizontal line tag adds exactly that through the text. In HTML the hr tag is a self closing tag.

Instead of adjusting the overall background or the color of text to make it the foreground more readable you can add a `background-color` to the element holding the text you want to emphasise. This challenge uses rgba() instead of hex or just rgb. The a stands for alpha or the opacity of the element. The alpha element can range from 0-1 with 0 being transparent and 1 being completely opaque.

The `box-shadow` property applies one or more shadows to an element. It takes the values offset-x (how far to push the shadow horizontally from the element), offset-y (how far to push the shadow vertically from the element), blur-radius, spread-radius and a color value, in that order. The latter two radii are optional. An example:

    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);

Here there are 2 sets of values one for offset-x and the other for offset-y, with the latter having more opacity and being offset-y.

`opacity` can be used to set the opacity / transparency of an element, follow the same rules as alpha.

`text-transform` in CSS is a way to make sure the text on a webpage stays consistent without having to change the text content of an actual HTML element. Here is what some transforms do to the following text “Transform me”

`lowercase` transform me
`uppercase` TRANSFORM ME
`capitalize` Transform Me
`initial` Use the default value
`inherit` Use the text-transform from the parent element
none Default: Use original text

`line-height` adjusts the height of each line in a block of text, it is the vertical space between each line.

Pseudo-classes are keywords that can dded to selectors in order to select a specific state of the element. For example the styling of an element can be changed for its hover state using the :hover pseudo-class e.g.

    a: hover {
      color: red;
    }

CSS treats each HTML elements as its own box, which is referred to as the CSS box model. Block-level items automatically start on a new line e.g. heading, paragraphs and divs, while inline items sit within surrounding content e.g. images, spans. The default layout of elements in this way is called normal flow of a document. CSS offers the position property to override this.

`relative` allows you to specify how CSS should move relative to its current position in the normal flow of the page. If pairs with the CSS offset properties, left, right,top and bottom. These say how many pixels, percentages or ems to move the item away from where it is normally positioned. Offsetting is done from a given spot, which moves the element away from the referenced side i.e. the opposite direction.

By changing an elements position to relative it does not remove it form the normal flow - other elements around it still b have as if that item were in its default position.

NB: Remember that no matter the position of elements, the underlying HTML mark-up should be organised and makes sense when read from top to bottom. This is how users with visual impairments (who rely on assistive devices e.g. screen readers) access your content.

`absolute` locks the element in place relative to its parent container. Unlike relative this removes the element from the normal flow of the document, so the surrounding items ignore it. The CSS offset properties are used to adjust the position.

Absolute positioning will be locked relative to its closest positioned ancestor. If you forget to add a position rule to the parent item (typically done with position: relative;) the browser will keep looking up the chain and ultimately default to the body tag.

`fixed` this is a type of absolute positioning that locks an elements relative to the browser window. Uses the CSS offset properties and also removes the element from the normal flow of the document. Other items no longer “realise” where it is positioned, which may require some layout adjustments elsewhere. One key difference is that when a a user scrolls the element with a fixed positioned won’t move.

`float` IS a property of an element which are removed from normal flow of a document and pushed either left or right of their containing parent element. It is commonly used with the width property to specify how much horizontal space the floated element requires.

When elements are positioned to overlap the elements which comes later in the HTML mark-up will be positioned on top of the other elements. However, z-index property can specify this order instead. It must always be an integer i.e. a whole number, with higher values for the z-index move it higher in the stack.

Another positioning technique is to centre a block element horizontally. One way is to set the margins to auto, margin: auto, this works for images too. By default images are inline elements but can be changed to block elements when you set the display property to block.

Complementary colours - when two colours are opposite each other on the colour wheel they are said to be complementary colours. When combined they are said to “cancel” each other out and create a grey colour. However, when placed side by side they appear more vibrant and produce a strong visual contrast.

Tertiary colours - Different colours are created on computer / device screens by combining amounts of RGB light. This is known as the RGB additive colour model. Teritary colours are the result of combining a primary colour with one of its secondary colour neighbours. For example red (primary) and yellow (secondary) to make orange.

One way of selecting a harmonious combination is called split-complementary colour scheme. You start with a base colour then pari it with two colours that are adjacent to its complement. The 3 colours provide strong visual contrast in design e.g. orange, cyan and raspberry.

Colours have several characteristics including hue, saturation and lightness. CSS3 introduced hsl() property as an alternative way to pick a colour by directly stating these characteristics. Hue is thoughts of as spectrum from red to blue using 0-360, saturation is the amount of gray in a colour this is given from 0-100% and finally lightness is the amount of white or black in a colour again from 0% (black) - 100% (white), 50% is normal colour. Mixing white with pure hue creates a tint of that colour and adding black will make a shade. Alternatively, a tone is produced by adding tray or by both tinting and shading. This is done with variation from s and l.

CSS provides the ability to use colour transitions, known as gradients, on elements. This is accessed through the background property’s linear-gradient( ) here is the general syntax:

    background: linear-gradient(gradient direction, color 1, color 2, color 3, …);

The first arguments, gradient direction, is stated as a degree, where 90 degree makes a vertical gradient and a 45 degree is angled like a backslash. Colours can be specified as hex code, rgb and hsl.

`repeating-linear-gradient( )`, is similar to above, major difference being that it repeats a specific gradient pattern. Color stops are like width values and tell the code where one colour begins and another starts e.g. yellow 0px, blue 40px, here yellow starts at 0px and blue starts 40px away from the start.

The background property supports the url( ) function in order to link and image of a chosen texture or pattern. The link address is wrapped in quotes inside the parentheses.

The scale of an element can be changed with the transform property, using the scale ( ) function.

    transform: scale(X);

`transform` has a variety of functions that let you scale, move, rotate, skew etc. When used with pseudo-classes such as :hover that specify a certain state of an element, the transform property can easily add interactivity to your elements.

`skewX/Y( )` is another function within the transform property. It skews the selected element along its X axis or Y axis by a given degree.

Manipulating different selectors and properties can make interesting shapes. For example to make a crescent moon you can achieve this using box-shadow and border-radius. To create this the following syntax can be used:

    .crescent-moon {
      position: absolute;
      margin: auto;
      top: 0;
      right: 0;
      bottom; 0;
      left; 0;
      width; 100px;
      height; 100px;
      background-color: transparent;
      border-radius: 50%;
      box-shadow: 25px 10px 0px 0px blue;
    }

Additional pseudo-elements:

`: :before` & `: :after`, These are used to add something before or after a selected element. For these elements to function they must have defined content property, this is usually used to add things like a photo or text to the selected element. Even when they are used to make shaped the content property is still required, but it is set to an empty string.

Animating an element can be done using animation properties and the @keyframes rules. This rule controls what happens during that animation. There are 8 in total.

`animation-name` set sthe name of the animation, which is later used by @keyframes to tell CSS which rules go with which animations.

`animation-duration` sets the length of time for the animation.

`@keyframes` specifies exactly what happens within the animation over the duration. This is done by giving CSS properties for specific “frames” during the animation, with percentages ranging from 0-100%.

Comparing to a movie 0% is how the elements displays the opening scene and at 100% is how the element appears at the end. Here is an example of the syntax:

    #anim {
      animation-name: colorful;
      animation-duration: 3s;
    }
    @keyframes colourful {
      0% {
        background-color: blue;
      }
      100% {
        background-color: yellow;
      }
    }

@keyframes can be used to change the color of buttons during their hover state. Or the size width of an image during hover. For example:

    Img:hover {
      animation-name: width;
      animation-duration: 500ms;
    }

    @keyframe width {
      100% {
        width: 40px;
      }
    }

In the above example the animation resets at 500ms, causing the img to resize to its original size. This can be done by setting animation-fill-mode property to forwards. The animation-fill-mode specifies the style applied to an element when the animation has finished.
When elements have a specified position, such as fixed or relative, the CSS offset properties right, left, top and bottom can be used in animation rules to create movement. To make an object move up and down you could for example have:

    0% {
    top: 0px;
    }
    50% {
    top: 50px;
    }
    100% {
    Top: 0px;
    }

Changing the opacity of an element can also give some interesting animations. Adding opacity to the @keyframes changes the opacity of the animation as it progresses through the %.

To ensure your animation continues on indefinitely and not ending once it reaches 100% you can use an infinite animation count. Adding animation-iteration-count, allows you to control how many times you would like to loop through the animation. Setting animation-iteration-count: infinite will ensure the animation continues indefinitely.

Elements can also be animated at varying rates. There are a variety of ways to animate similar elements at varying rates e.g. animation-iteration-count and setting @keyframes. Additionally. You can also change the animation-duration of multiple elements.

Animation timing can be adjusted with keywords. Using the animation-timing-function property controls how quickly an animated element changes over the duration of the animation e.g. if your animation is a car moving from A to B in a given time (animation-duration) then animation-timing-function says how the car accelerates and decelerates over the course of the drive.

There are a number of predefined keywords available for popular options:

`ease` starts slow, speeds up in the middle and then slows down again at the end.
`ease-out` quick beginning then slows down
`ease-in` slow beginning then speeds up
`linear` applies constant speed throughout the animation

To give even finer control over how the animation plays out you can use Bezier curves. These are used with the cubic-bezier function. The shape fo the curve represents how the animation plays out.

The curve lives on a 1 by 1 coordination system, the X-axis of this is the duration of the animation and the Y-axis is the change in the animation. The function itself consists of four main points that sit on the 1 by 1 grid: p0, p1, p2 and p3. p0 and p3 are control points and are always set to (0,0) and (1,1), they don’t move (left).

You set the x and y values for the other 2 points and where you place them in the grid dictates the shape of the curve for the animation to follow. In CSS this done by declaring the x and y value of the p1 and p2 “anchor” points in the form (x1, y1, x2, y2).

More points can be added, in fact the amount of points is irrelevant, adding more points can simply help to create more interesting animations.

Setting the y coordinate to be larger than 1 results in a bouncing moment that is ideal for simulating things like juggling, bouncing, snapping etc.
