# What is this?

This project is the final assigment from the [HTML & CSS course from The Odin project](https://www.theodinproject.com/paths/full-stack-ruby-on-rails/courses/html-and-css/lessons/design-your-own-grid-based-framework).<br>
The assigment required to create a grid-base css framework. It's just need to have all the basic elements to create a 12 column grid. Once the framework was done, the second part of the assigment was to recreate a webpage of your choice, I chose [The Odin project's homepage](https://www.theodinproject.com/). If you want to see it, the webpage is in [this](https://github.com/JNFussion/odin-project-homepage) repository.


## The framework

I have used sass as a css preprocessors. The goal was to split the content in majors secctions using partials. Then compile them in a sigle css file.

### Table of contents
1. [main_styles](#main_styles)
2. [reset](#reset)
3. [layoiut](#layout)
4. [typography](#typography)
5. [box](#box)


## Sections:

<a name="#main_styles"></a>

### main_styles : 

Here are imported all the partials. Also it has some additional classes.
The extras are:
+ <code>.btn</code> : Use this class to create a button using anchor tag or to style a button tag.

+ <code>Diferent</code> classes for iframe and img:
  * <code>.iframe-container</code> and <code>.responsive-iframe</code> for iframe.
  * <code>ratio-x-y</code> to set the aspect ratio of the iframe. The default aspect ratios are: _16:9_, _4:3_, _3:2_ and _1:1_. Exaple:
  ```HTML
  <div class="iframe-container ratio-4-3">
    <iframe class="responsive-iframe" width="560" height="315" src="" allowfullscreen></iframe>
  </div>
  ```

  * <code>.media-container</code> and <code>.responsive-img</code> / <code>.responsive-img-alt</code> for images.

  * <code>.navigation</code> for a responsive navbar. Like this:

  ```HTML
  <ul class="navigation">
    <li><a href=""></a></li>
  </ul>
  ``` 

 <a name="#reset"></a>

### reset :

It's [Eric Meyer's reset](https://meyerweb.com/eric/tools/css/reset/). I just add <code>box-sizing: border-box;</code> to all tags.

<a name="#layout"></a>

### layout : 

Here are implemented the grid and flex layout. Also it has helpes to positioning, sizing, aligning and justifying.

* <code>.grid</code> is just for positioning the children of the element.
* <code>.grid-12</code> or <code>.row</code> will create a 12 column grid. The width of a column is <code>1fr</code>.
* The 12 column grid classes have 3 media queries at <code>min-width: 480px</code>, <code>min-width: 760px</code> and <code>min-width: 1020px</code>. This queries will set the <code>max-width</code> of the grid at <code>420px</code>, <code>720px</code> and <code>1200px</code> respectively.
* For the children you can position them using <code>.column-x</code>, <code>.span-s</code> or <code>.column-x-s</code>. The range of the values are from 1 to 12.
``` HTML
<div class="grid-12">
  <div class="column-3">ITEM1</div> /* WILL PLACE THE ITEM AT THE THIRD GUTTER */
  <div class="span-2">ITEM1</div> /* THIS ITEM TAKE UP TO 2 COLUMNS */
  <div class="column-3-2">ITEM1</div> /* SHORTHAND FOR THE PREVIOUS CLASSES. PLACED AT THE THIRD GUTTER AND TAKE UP 2 COLUMNS */
</div>
```
Beside the 12 column grid layout, you can also use flex-box.

* <code>.flex</code> or <code>.flex-column</code> will set the item to <code>display: flex</code>, the second class is to set the direction to column.
* <code>.flex-wrap</code> will make the flex box to wrap when there isn't enough space.
* <code>.flex-x</code> will set flex-grow and flex-shrink properties. The range of the values are from 1 to 4.

Shared classes:

* <code>.gap-s</code> to size the gap property.

<table>
  <tr>
    <th>s</th>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
  </tr>
  <tr>
    <th>size</th>
    <td>0.5em</td>
    <td>0.75em</td>
    <td>1em</td>
    <td>1.5em</td>
    <td>2em</td>
  </tr>
</table>

* For alignment you can use <code>.a-option-value</code> and for justification you can use <code>.j-option-value</code>.
  + __option__ can be replace with <code>content</code>, <code>items</code> and <code>slef</code>
  + __value__ can be replace with <code>start</code>, <code>end</code>, <code>center</code>, <code>space-evenly</code>, <code>space-around</code> and <code>space-between</code>.

<a name="#typography"></a>

### typography : 

Here are implemented some basis classes text related.

* <code>.content-container</code> is meant to be for focused text content like paragraph. It set the font size to __14px__, it use a serif font, <code>line-height: 1.5;</code> and add some padding and margin.

* <code>.title</code> is for headings it sets the text to __bold__, <code>line-height: 1.2</code> and the default font size is __22px__.

* <code>.size-s</code>, it set the font size.

<table>
  <tr>
    <th>s</th>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
    <td>6</td>
  </tr>
  <tr>
    <th>size</th>
    <td>20px</td>
    <td>22px</td>
    <td>24px</td>
    <td>26px</td>
    <td>2em</td>
    <td>2.5em</td>
  </tr>
</table>

* <code>.bold</code> and <code>.italic</code> set the weight to __bold__ and the style to __italic__ respectively.

* <code>.text-centered</code> and <code>text-upper</code> set the text-align to __center__ and text-transform to __upercasse__

* For the anchor tag, the undeline is remove, the color is grey
which change to black when is hovered in 0.2 seconds.

<a name="#box"></a>

### box : 

Here are implemented classes to add padding and margin. Also has some classes related to the style of the box.

* For padding there are the following options:
 + <code>p-s</code> to add padding to both axies, horizontal and vetical.
 + <code>px-s</code> to only add padding to the horizontal axis.
 + <code>py-s</code> to only add padding to the vertical axis.
 <br><br>
 To set only one side:
    - <code>pl-s</code> to only add padding to the left side.
    - <code>pr-s</code> to only add padding to the right side.
    - <code>pt-s</code> to only add padding to the top side.
    - <code>pb-s</code> to only add padding to the bottom side.

* For margin there are the following options:
 + <code>m-s</code> to add margin to both axies, horizontal and vetical.
 + <code>mx-s</code> to only add margin to the horizontal axis.
 + <code>my-s</code> to only add margin to the vertical axis.
 <br><br>
 To set only one side:
    - <code>ml-s</code> to only add margin to the left side.
    - <code>mr-s</code> to only add margin to the right side.
    - <code>mt-s</code> to only add margin to the top side.
    - <code>mb-s</code> to only add margin to the bottom side.

  <table>
  <tr>
    <th>s</th>
    <td>auto</td>
    <td>none</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td>4</td>
    <td>5</td>
    <td>6</td>
  </tr>
  <tr>
    <th>size</th>
    <td>auto</td>
    <td>0</td>
    <td>.75em</td>
    <td>1em</td>
    <td>1.25em</td>
    <td>1.5em</td>
    <td>1.75em</td>
    <td>2em</td>
  </tr>
  <caption style="caption-side: bottom;">
    auto only works in the horizontal axis.
  </caption>
</table>

* <code>.rounded</code> make the element a circule.
* <code>.bordered</code> and <code>.has-shadow</code> add simple 1px black border and some shadow respectively.