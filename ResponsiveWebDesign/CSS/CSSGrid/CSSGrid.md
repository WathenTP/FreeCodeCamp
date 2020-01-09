# CSS Grid

CSS Grid helps build complex web designs. It works by turning an HTML element into a grid container with rows and columns for you to place children elements where you want within the grid.

Any HTML element can be turned Ito a grid by setting display: grid; this gives you the ability to use all other properties associated with CSS grid.

NB: The parent element is referred to as the container and its children are called items.

Once the display has been defined as a grid you then need to define the structure of the grid as well. T odd columns use grid-template-columns property on a grid e.g.

    .container {
      display: grid;
      grid-template-columns: 50px 50px;
    }

The above code will give the grid 2 columns each with a a 50px width. The number of parameters given to the property defines the number of columns in the grid and each value gives the width. To adjust the rows manually you can use grid-template-rows property in the same way you used grid-template-columns.

Absolute and relative units can be used to e.g. px and em in the CSS grid to define the size of the rows and columns. You can also use:

`fr` - sets the column / row to a fraction of the available space

`Auto` - sets the column / row to the width / height of its content automatically.

`%` - adjusts the column / row to the percent of its container.

To add a gap between column / row you can use `grid-column-gap` and `grid-row-gap` the state the width of the gap e.g. 10px. A short hand for these is `grid-gap` which encompasses both of these only having one value. However, giving it two values will result in the first one being used for the gap between rows and the second between columns.

The previous properties have all been for grid containers. However, `grid-column` property is for the grid items themselves. The hypothetical horizontal and vertical lines are referred to as lines. They are numbered starting with 1 at the top left corner and move right for the columns and down for the rows, counting upward.

To control the amount of columns an item will consume, you can use the grid-column property in conjunction with the line numbers you want the item to start and stop at e.g.

    grid-column: 1 / 3;

The above will make the item start at the first vertical line and span to the 3rd line of the grid, consuming 2 columns.

Items can also be made to consume multiple rows just like with columns using grid-row property.

In CSS Grid the content of each item is located win a box which is referred to as a cell you can align the contents position within its cell horizontally using justify-self property on a grid item. By default this property has a value of stretch which will make the content fill the whole width of the cell. However, this CSS grid property also accepts:

`start` - aligns content at the left of cell

`center` - aligns content in the center of cell

`end` - aligns content at the right of the cell

To align an item vertically you use the `align-self` proper on an item and it accepts all the same values as `justify-self`.

When you want all items in the Grid to share the same alignment, this can be done with the aforementioned properties or you can align all of them at once using `justify-items` on the grid container. This property can accept all the same values as above, the difference being it will move all items in the grid to the desired alignment. Additionally, `align-items` property will set the vertical alignment for all items.

Cells of the grid can be grouped together into an area and give the area and custom name. This can be done with grid-template-areas on the container e.g.

    grid-template-areas:
    	“header header header”
    	“advert content content”
    	“footer footer footer”;

This code merges the top 3 cells into a header, the bottom 3 into a footer and it makes 2 areas in the middle content and 1 an advert.

NB: Every word in the code represents a cell and every “” represents a row. Additionally, you can use a period (.) to designate an empty cell in the grid.

Once areas have been created for the grid container, you can place and item in your custom area by referencing the name you gave it. To do this, you use the grid-area property on an item like this:

    .item1 {
    	grid-area: header;
    }

This lets the grid know that you want the item1 class to go in the area named header.

`Grid-area` can also be used in another way. IF you grid doesn’t have an areas template to reference, you can create an area on the fly from an item to be placed like this:

    .item1 {
    	grid-area: 1/1/2/4;
    }

This is using the line numbers as seen in the above image, to define where the area for this item will be. The number above represent:

    grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;

So in the example the item will consume rows between lines 1 - 2 and columns between lines 1 - 4.

When `grid-template-columns` and `grid-template-rows` has been used to define the structure of a grid, you enter a value for each row or column you have created. Imagine a grid that has a 100 rows of the same height, it isn’t practical to insert 100 value individually.

By using the `repeat` function to specify the number of times you want your column or row to be repeated, followed by a comma and the value you want to repeat. For example a 100 row grid with each row at 50px tall.

    grid-template-rows: repeat (100, 50px);

You can also repeat multiple values with the repeat function and insert the function amongst other values when defining a grid structure. e.g.

    grid-template-columns: repeat (2, 1fr 50px) 20px;

Which translates to

    grid-template-columns: 1fr 50px 1fr 50px 20px;

There is another built in function to use called `minmax` it is used to limit the size of items when the grid container changes size. To do this you need to specify the acceptable size range for the item e.g.

    grid-template-columns: 100px minmax(50px, 200px);

This code is set to create 2 columns; the first is 100px wide and the second has a minimum width of 50px and a maximum width of 200px.

The `repeat` function comes with an option called `auto-fill` which allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container. Flexible layouts can be creates when combining `auto-fill` with `min-max`.

`auto-fit` works almost identical to `auto-fill` he only difference is that when the containers size exceeds the size of all the items combined `auto-fill` keeps inserting empty rows or columns and pushes your items to the side, while `auto-fit` collapses those empty rows or columns and stretches your items to fit the size of the container.

CSS Grid can be an easy way to make your site more responsive by using media queries to rearrange grid areas, change dimensions of a grid and rearrange the placement of items.

Turning an area into a grid only affects the behaviour of its direct descendants, if we turn the direct descendent into a grid, you have a grid within a grid.
