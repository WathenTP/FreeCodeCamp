# Basic CSS

CSS stands for Cascading Style Sheets

CSS is case sensitive, so be careful with capitalisation. It allows the control of, colour, fonts, positioning, spacing, sizing, decorations and transitions.

3 main ways to apply CSS:

- Inline styles directly to HTML elements with the style attribute
- CSS rules within style tags in an HTML documents
- External style sheets that keep them separate to HTML elements (preferred)

The last one improves the readability and reusability of code.

`style` this is the property responsible for changing the appearance of HTML elements it is often then followed by a secondary attribute that directs what aspects the style are to be changed. Good practice always ends inline styles with a semicolon ;

- color
- font-size
- width

When applying style features a separate style block can be created within the HTML file, this is done by simply stating, `<style></style>`, and recording the features within this block. When using style blocks it is important to have open and closed curly brackets around each element’s style rule. An example:

    <style>
      h2 {color:red;}
    </style>

This would make all h2 elements red. Curly brackets and semicolon are essential for good practice.

Classes are reusable styles that can be added to HTML elements and example CSS class declaration:

    <style>
      .blue-text {
        color:blue;
      }
    </style>

This CSS class “.blue-text” can be applied to HTML elements in the following way,

    <h2 class=“blue-text”> ExampleText </h2>

Note that in the CSS style element class names start with a period (.) but in the HTML elements’ class is doesn’t.

`Font-size` CSS property written much like color,
h1 {
font-size: 30px;
}

`font-family` selects the actual font of an element e.g. sans serif, times new roman etc. In addition to specifiying common fonts found on most operating systems we can also specify non-standard, custom web fonts for use on our own websites. Google Fonts library being one of the best places to go!
To do this you need to import them from google, an example would be:

    <link href=“https://fonts.googleapis.com/css?family=lobster" rel=“stylesheet” type=“text/css”>

This imports the lobster font into our HTML. When referencing fonts the following format is used:

`Font-family: FAMILY_NAME, GENERIC_NAME;`

Family name needs to be wrapped in quotes if there is a space e.g. “Times New Roman”.

When one font isn’t available you can tell the browser to “degrade” to another font. Such as:

    p {
      font-family; Helvetica, sans-serif;
    }

The latter is the GENERIC font family and they not case-sensitive, additionally, they do not need quotes as they are CSS keywords.

`width` is a property that controls an elements width, just like fonts we can use px to specify and images’ width. For example if you wanted to give CSS a class larger-image that gave HTML elements 500 pixels you would do:

    <style>
      .larger-image {
      width: 500px;
      }
    </style>

CSS borders have properties like style, collar and width too. Fore example a red, 5 pixel border around a HTML element would be:

    .thin-red-border {
      border-color: red;
      border-width: 5px;
      border-style: solid;
      }

Multiple classes can be applied on the same element with a space imbetween, `<img class=“class 1 class 2”`.

`border-radius` this element can be used to round out sharp corners in CSS. It can be applied either to the border itself or the image. Additionally, other than pixels % can be used when specifying the order radius. For example a 50% border-radius would make an image perfectly circular.

`background-color` set the elements background color. For example if you wanted green you would put the following in the style element:

    .green-background {
      background-color: green;
      }

In addition to classes you can set an id to an html element. Benefits include; style single elements and to select and modify specific elements with javascript. Id elements should be unique, this is best practice, although it is not enforced by browsers. Much like classes, id elements can also be style by CSS. However, id’s are not reusable and should only be applied to one element. An id also has higher specificity (importance) than a class so if both are applied the id element will be shown.

Adjusting the padding of an element. Three important properties control the space that surrounds each HTML element; padding, margin and border.

- `padding` - amount of space between element’s content and border. Sometimes you will want customise and element so that it has different padding on each side. CSS allows the control of padding on all 4 sides of an element. With padding-top / right / bottom / left properties.
- `margin` - amount if space between an elements border and surrounding elements. Setting a margin to a negative value makes the element grow larger. The margin can also be controlled on each of the 4 sides with margin-top / right / bottom / left.
- `border` - the literal line that encapsulates an element it is applied to.

Instead of specifying an elements top, right, bottom, left properties, you can specify them all in one line like this:

    padding: 10px 20px 10px 20px;

These 4 values work like a clock; top, right, bottom and left and will produce the exact same result as using the side-specific instructions.

`attr` attribute selector matches and styles elements with a specific attribute value.

- `type` is a common attribute selector. This can be used to edit all ‘types’ to have the same values for example:

        [type = ‘XYZ’] {
          margin: 20px 0px 0px 20px;
          }

Gives all types XYZ top and bottom margins of 20px.

Absolute vs Relative units - Above we have used px (pixels to define the elements margin or padding. Px area. Type of length unit, however, CSS has a number of different length unit options.

The two main types of length units are absolute and ratline. The former. Tie to physical units of length e.g. in and mm refer to inches and millimetres, respectively. These units approximate the actual measurement on a screen but there are differences depending on screen resolution.

Relative units e.g. em or rem, are relative to another length value.

- `em` is based on the size of an elements font, if you use it set font-size property itself, its relative to the parent’s font-size.

CSS inheritance, in the style section you can simply target the body element, then define the styling within that element. This results in all other elements within the body to inherit those defined features.

However, if you then define a class in the style section and attached said class to an element that is contained within the body the class overrides the body’s CSS declaration. If you apply multiple class elements to a HTML element it doesn’t matter which order the classes are listed in (within the HTML element) what does matter is how they are listed in the `<style>` section. The last declaration will always take precedence over the first.

However, there are other ways to override this which include setting an id element to the element you want to change. You can also use inline style too e.g. `<h1 style=“color: green;”>`, this will override all CSS declarations in the style element.

Overriding can be important because in many cases CSS libraries will be used which could override your own CSS. So when you absolutely need to be sure that an element has a specific CSS you can use !important. This key work has to be added to the feature declaration e.g. color delcaration would look like this

    .pink-text {
      color: pink !important
    }

Colours can also be implemented by using hexadecimal code, hex code for short. Typically we use decimals, or base 10 numbers, which use the symbols 0-9 for each digit, for hex code there are 16 numbers. This means it uses 16 distinct symbols. Which are:

- 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F

Hexadecimal numbers are more human-friendly representations of binary-coded values. Each digit represents four binary digits, also known as a nibble, which is half a byte. A single byte can have values ranging from 0000 0000 to 1111 1111 in binary form, which can be more conveniently represented as 00 - FF in hexadecimal.

In CSS we can use 6 hexadecimal digits to represent colours, two each for red (R), green (G) and blue (B). For examples #000000 is black and the lowest possible value. Often hex code can be overwhelming and using the full 6 digits provides the possibility of more than 16 million different colours. Fortunately this can be shorted to just using 3 digits. For examples:

Red Hex code is `#FF0000` can be shortened to `#F00`, the shortened form gives 1 digit for R, G and B. Reducing possible colours to around 4000.

Another way to represent colours is with RGB value e.g. the RGB for black is rgb(0, 0, 0) and the rgb for white would be `rgb(255, 255, 255)`.

CSS variables, are a way to change many CSS style properties at once by only changing one value. To create a CSS variable you just need to give is a name with two dashes e.g. - - XYZ, once you create this variable you can then use that variable elsewhere in your CSS to change the value of other elements. It should be noted that styles will not be applied unless the variable acmes are an exact match.

When changing the elements use the following:

`elementXYZ: var(-- XYZ)`;

When using the variable as a CSS property value, you can attach a fallback value that your browser will revert too if a given variable is invalid. This is done like so:

`elementXYZ: var(-- XYZ, Fallback Value)`

This can be very useful for debugging. When the browser parses the CSS of a webpage, it ignore properties that is doesn’t recognise or support. This will then give a default value which is not ideal, so to overcome this it is best to provide another more widely supported value immediately before your declaration, this way older browsers will have something to fall back on.

Cascading CSS variables, creating a variable means it becomes available for you to use inside the element which you create it. It also becomes available within any elements nested within it, this is known as cascading. Because if this CSS variables are often defined in the `:root` element.

The `:root` element can be thought of as a container for the entire HTML document, in the same way HTML element is a container for the body element. Creating variables in :root they will be available throughout the whole web page.

These can be overwritten by setting them again within a specific element.

Media queries, CSS variable can simplify the way media queries can be used. For example if the screen is smaller or larger than your media query break point, you can change the value of a variable and it will apply its style wherever it is used. For example:

You may set the root size to be 300px and the colour to be white, however, under certain conditions you may want to resize and colour your elements to improve clarity e.g. if max width is 350px then then the image would need to be resized and color changed for clarification.

    @media (max-width: 350px) {
      : root {
        - - XYZ size: 250px
        - - XYZ colour: black
      }
    }
