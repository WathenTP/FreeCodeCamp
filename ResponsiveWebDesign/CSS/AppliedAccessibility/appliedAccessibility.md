# Applied Accessibility

Accessibility means having web content and a user interface that can be interacted with by a broad audience. Including those with visual, auditory, mobility or cognitive disabilities. Some users rely on assistive technology e.g. screen read or voice recognition. To achieve this 3 ideas should be kept in mind:

1. Well organised code that uses appropriate markup
2. Ensure text alternatives exist for non-text and visual content
3. Create an easily navigated page that’s keyboard friendly.

An excellent resource for projects going forward is W3 consortium’s Web Content Accessibility Guidelines (WCAG). They set the international standard for accessibility and provide a number of criteria you can sue to check your work.

The `alt` tag has previously been used to provide a description of an image, so that when it fails to load it can provide a text alternative of the image. This is also useful if the image can’t be seen by the user as well as what search engines use to understand what an image contains in order to include it in search results.

    <img src=“XYZ.jpeg” alt=“ABC”>

People with screen readers convert web content to an audio interface, screen readers can access the alt attribute and read its content to deliver key information. Good alt text should be short but descriptive. Per HTML5 specification this is now mandatory.

Sometimes images are grouped with a caption already describing them or are for decoration only. In this case the alt may seem redundant. However, the image still needs an alt attribute, but it can be set to an empty string. Background images usually fall under the decorative label too. However, they are typically applied with CSS rules and thus are not part of the markup screen readers process.

Even when images have a caption, adding alt text will still help search engines.

h1 - h6 elements are the workhorse tags that help proved structure and labelling too content. Screen readers can be set to only read these headings on a page, so the user gets a summary. This means it is important for the for heading tags in the markup to have semantic meaning and relate to each other, not just to be picked for size value.

Heading with equal (or higher) rank start new implied sections, headings with lower rank start subsections of the previous one. For example a h2 elements followed by several h4 would confuse a screen reader. While it may be tempting to use a tag because it looks better in the browser you can use CSS to edit the relative sizing.

Final note, each page should have 1 (and only 1) h1 element, which is the main subject of your content. This and other headings are used in part by search engines to understand the topic of the page.

HTML5 introduced a number of new elements that give developers more options while also incorporating accessibility features. Examples include, main, header, footer, nav, article and section among others.

By default a browser will render this like a div, however using them where appropriate gives additional meaning in the markup. The tag name alone can indicate the type of information it contains which adds semantic meaning to the content. Assistive tech ologies can access this information to provide better page summary or navigation.

`main` is used to wrap the main content, there should only be one pr page. It’s mean to surround the information that’s related to central topic of your page. It shouldn’t include items that repeat across pages e.g. banners or navigation links. It also has an embedded landmark feature that assistive technology can use to quickly navigate to the main content. “Jump to main content” link at the top of webpages yes the main tag to automatically give assistive devices that functionality.

`article` sectioning element, used to wrap independent, self-contained content. The tag works well with the blog entries, forum posts or news articles.

To judge whether content can stand alone you can perform a couple of simple tests:

- Ask yourself if you remove the surrounding context, would that context make sense?
- For text, would that content hold up if it were in an RSS

`section` similar to article but has different semantic `meaning` the latter is for standalone content and a `section` is for grouping thematically related content. For example if a book it the article, then each chapter is a section. When there is no relationship between groups of content, then use a `div`.

    <div> - Groups Content
    <section> - Groups Related Content
    <article> - Groups independent, self-contained content.

`header` used to wrap introductory information or navigation links for its parent tag and works well around content that’s repeated at the top on multiple pages. It shares the embedded landmark feature found in main allowing assistive technologies to quickly navigate to that content. header is meant for use in the body tag, this is different than the head element, which contains meta information.

`nav` another embedded landmark feature for easy screen reader navigation. It is meant to wrap around the main navigation links in your page.

If you have repeated site links at the bottom of the page it isn’t necessary to markup those with a nav tag as well. Using footer is sufficient.

`footer` has a built in landmark feature, that allows assistive devices to quickly navigate to it. It’s primarily used for to contain copyright information or links to related documents.

`audio` gives semantic meaning when it wraps sound or audio stream content in the markup. Audio content also needs a text alternative i.e. for deaf / hard of hearing. This can be done with nearby text on the page or a link to a transcript. audio supports the controls attribute, this shows the browser default play, pause etc. and supports keyboard functionality.

    <audio id=“XYZ” controls>
      <source src=“audio/XYZ.mp3” type=“audio/mpeg” />
      <source src=“audio/XYZ.ogg” type=“audio/ogg” />
    </audio>

NB: MM content usually has both vials and auditory components. These need to be synchronised captions and a transcript so users with visual/auditory impairments can access it. Generally a web developer isn’t responsible for creating captions or transcript, but needs to know to include them.

`figure` and `figcaption`, used together these items wrap a visual representation e.g. image, diagram or chart, along with its caption. For data visualisation the caption can be used to briefly note the trends / conclusions for users with visual impairments. figcaption always goes inside figure.

`label` wraps the text for a specific form control item. This ties meaning to the item and makes the form more readable. The for attribute on a label explicitly associates it with the form control and is used by screen readers.

Earlier we looked at radio buttons in the HTML section which can we wrapped the radio button input element inside a label element along with the label text in order to make the text clickable. Another way to achieve this is to use for attribute as explained above. The value of the for attribute must be the same as the value of the id attribute of the form control e.g.

    <form>
      <label for=“name”> Name: XYZ </label>
      <input type=“text” id=“name” name=“name”>
    </form>

Typically radio buttons come in a group where the user must choose one, there’s a way to semantically show the choices are part of a set. The fieldset tag surrounds the entire grouping of radio buttons to achieve this. It often uses a legend tag to provide a description for the grouping, which is read by scree nreaders for each choice in the fieldset element.

The fieldset / legend are not necessary when the choices are self explanatory e.g. gender selection. Simply using the label with the for attribute would suffice.

    <form>
      <fieldset>
        <legend> Choose one of these 3 items: </legend>

            <input id=“one” type=“radio’ name=“items” value=“one”>
            <label for=“one”> Choice One </label> <br>

            <input id=“two” type=“radio’ name=“items” value=“one”>
            <label for=“two”> Choice Two </label> <br>

            <input id=“three” type=“radio’ name=“items” value=“one”>
            <label for=“three”> Choice Three </label> <br>
        </fieldset>

    </form>

Forms often contain an input field, which can be used to create several different form controls. The type attribute on this element indicates what kind of input will be created. Previously encountered input types include; text / submit, in addition to this HTML5 introduced an option to specify a date field. Depending on browser, a date picker shows up in the input field when it’s in focus.

In older browsers the type will default to text so it helps to show users the expected date forma in the label or as placeholder text just in case.

    <label for”input1”> Enter a date: </label>
    <input type=“date” id=“input1” name=“input1”>

HTML5 also introduced time element along with datetime attribute to standardise times. This is an inline element that can wrap a date or time on a page. This is the value accessed by assistive devices, it helps avoid confusion by stating a standardised version of a time, even if it’s written colloquially.

    <p> I watched game of thrones <time datetime=“2019-04-29”> yesterday </time>, which was shit. </p>

So far we have not used CSS with any of the aforementioned applied accessibility. This is to emphasise the importance of semantically meaningful tags around content before seeing the visual design aspect.

However, CSS can also improve accessibility on the page when you want to visually hide content meant only for screen readers e.g. when information is in a visual format such as a chart. But screen reader users need alternative presentation e.g. a table, to access data. CSS Is used to position the screen reader-only elements off the visual area of a browser window. Here is an example ion the CSS rules to accomplish this:

    .sr-only {
    position: absolute;
    left: -1000px;
    width: 1px;
    height: 1px;
    top: auto;
    overflow: hidden;
    }

Here are examples of additional approaches that can hide content:

`display: none;` or `visibility:hidden;` hides content for everyone, including screen readers.
Zero value for pixel sizes e.g. `width: 0px;` `height: 0px;` remove that element from the flow of the document.

Readability can be further improved by using high contrast text. The Web Content Accessibility Guidelines (WCAG) recommend at least a 4.5 to 1 contrast ratio for normal text. Ratio is calculated by comparing relative luminance values of 2 colours.

1:1 - for the same colour, no contrast
21:1 - for white against black, the strongest contrast

Colour-blindness issues can be avoided too with sufficient contrast. While colour is large part of visual design its use introduces issues.
Colour alone should not be used as a the only way to convey important information as screen readers won’t see it.
Foreground and background colours need sufficient contrast so colourblind users can distinguish them.

Previously we have seen how text alternative can be used to address issue 1. Above the WCAG recommended a colour contrast ratio of 4.5:1 for grey-scale combinations, this is also recommended for colour too.

However, colour-blindness issues can be avoided altogether by carefully choosing which colours convey information. The most common form of colour-blindness is reduced sensitivity to detect greens. Similar colours of used for the foreground and background should be avoided altogether when conveying information.

NB: Some online colour picking tools include visual simulations of how colours appear for different types of colourblindness. These are great resources in addition to online contrast checking calculators.

Looking back at screen readers, some have the option to only hear the links available on the page. They do this by reading the link text, or what’s between the anchor a tags. Thus, having a list of “click here” or “read more” links isn’t helpful. Instead, brief but descriptive text within the a tags to provide more meaning should be used.

Links can be made more navigable with the HTML Accesskey attribute. This specifies a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users. While HTML5 allows this to be used on any element it is particularly useful when it’s used with interactive ones e.g. links, buttons and form controls.

    <button accesskey=“b”> Important Button </button>

To add further keyboard focus tabindex attribute can be used. This attribute has 3 distinct functions relating to an element’s keyboard focus. When on a tag it indicates the element can be focused on, the value (an integer that’s positive, negative or zero) determines the behaviours.

Some elements e.g. links and form controls, automatically receive keyboard focus when a user tabs through a page. These are in the same order as the elements come in the HTML mark-up. This same functionality can be given to the other elements such as div, span and p by placing a tabindex=“0” attribute on them.

    <div tabindex = ”0”> GIVE ME KEYBOARD FOCUS </div>

Negative tabindex typically -1, indicates that an element is focusable but not reachable by a keyboard. This is generally done to bring focus to content programmatically e.g. when a div used for a pop-up window is activated.

tabindex also specifies the exact tab order of elements. This is achieved when the value of the attribute is set to a positive number of 1 or higher. Setting it to 1 brings keyboard focus to that element first. Then cycles through the sequence of specified tabindex values e.g. 2,3,4, etc. When the tab order is set this way it overrides the default order, which uses the HTML source.

    <div tabindex = “1”> YOU TAB HERE FIRST </div>
    <div tabindext = “2”> YOU TAB HERE SECOND </div>
