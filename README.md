Web-Development-Fundamentals
============================

This tutorial is based on the material HTML/CSS/JavaScript from the Group Up by Google, found [here](https://www.youtube.com/playlist?list=PL697D36B35F92E9E4).


Introduction
----------------------------

First of all, lets take a look at what we use HTML, CSS and JavaScript (also known as JS) for.

The User Interface (UI) is the interface that we, as users, interact with. For web applications this is done through a web browser, like the one you're using to read this with. The UI is made up of 3 parts:
  1. *Structure* - The content of the UI.
  2. *Presentation* - How the content is displayed.
  3. *Behaviour* - How the content behaves when certain actions occur.

These 3 components correspond to the 3 technologies we're going to be looking at:
  1. *Structure* - HTML
  2. *Presentation* - CSS
  3. *Behaviour* - JavaScript

Web pages used to have these 3 technologies jumbled together, in short, it was a nightmare. Over time practices have changed so that now our HTML, CSS and JS are all separated.

This means that if we want to change how a website looks, we need to only swap out the corresponding CSS files, and any images used instead of having to root through HTML files looking for all CSS references.

###Why?
* _Accessibility_ - easy to use with screen readers and other accessibility devices
* _Portability_ - easy to make a web page support mobile or tablet formats
* _Maintainability_ - easy to make changes to on component without much effect on the others
* _Reduced Latency_ - we can use caching techniques to have browsers download the CSS or JS files once, and check after a determined expiry period, meaning they don't have to download them every time they visit.
* _Graceful Degradation_ - The web page will still function if the CSS or JS files don't get loaded in, for whatever reason.

Let's take a look at a website that does this [here](http://webremix.org/labs/lab2/demos/demo.html) or just follow along with the screen shots below.

![alt text](https://raw.githubusercontent.com/AndrewSpeed/Web-Development-Fundamentals/master/images/demo_page.jpg "http://webremix.org/labs/lab2/demos/demo.html")
As you can see, the page has an interactive navigation bar at the top that highlights whatever is hovered over, and displays a list of items under the 'Contact' tab. 
It also has lists of links on the left that can be shrunk or expanded by clicking on the '-' or '+' buttons, this is provided by JavaScript. 
There is also a form for submitting data and table for displaying it.

If we disable the JavaScript, we can see below that the only change is that the '-' and '+' buttons are gone from the quicklink lists, there have been other changes but they're more subtle.
![alt text](https://raw.githubusercontent.com/AndrewSpeed/Web-Development-Fundamentals/master/images/demo_page_no_js.jpg "Javascript disabled")

Finally if we disable CSS as well, we end up with a rather barebones, but still functional web page.
![alt text](https://raw.githubusercontent.com/AndrewSpeed/Web-Development-Fundamentals/master/images/demo_page_no_css_js.jpg "CSS and Javascript disabled")


###Recap
So far we've learned what each of the web technologies we're looking at is for, and how they affect different parts of the page's functionality.


HTML
----------------------------

As we've already learned, HTML is used to define the content and structure of a webpage.

One of the common misconceptions is that HTML is a programming language, it's not.
Markup languages like HTML add structured information, a markup language called markdown was used to write this tutorial.

###What does it look like?
You may have seen HTML before, but if not is looks something like this
```HTML
<tagname attribute='value'>
  content
</tagname>

<p id='id' class='classname'>
  Lorem ipsum dolorem...
</p>
```

In the section above, there are two __elements__, a tagname and a paragraph. Each element has an opening tag, some content and a closing tag. Elements can also be nested inside each other, creating what is known as a tree.

The paragraph element seen above has both an id and a class, these are used to identify it for CSS and JavaScript. 
__Id's should be unique, classes can be reused.__

Since HTML is the skeleton of the web page, you should write this first, then add style and behaviour afterwards.

We'll very briefly cover some of the common HTML elements.

###Headers
Header tags are used in HTML to create headlines that separate sections of content, these have been used throughout this page.

Header tags look like the following
```HTML
<h1>Header</h1>
<h2>Header</h2>
<h3>Header</h3>
...
<h6>Header</h6>
```

H1 tags are used for main headings, with the decreasing numbers being used for less important headings. 

It's important not to use these headings for their size, as that can be changed in the CSS, but to separate content. 

You ideally shouldn't use h1 for main headers then h3 tags for subheadings.


###Paragraphs
Paragraphs `<p>content</p>` are used to display, as their name suggests, paragraphs of content.


###Lists
Lists are, you guessed it, used to display lists of content such as links.

There are two kinds of lists in HTML, both of which you've already seen, Ordered Lists and Unordered Lists.

####Ordered Lists
```HTML
<ol>
  <li>Item</li>
  ...
</ol>
```
Ordered lists should be used for lists when the order of items is significant, such as for search results or instructions.

####Unordered Lists
```HTML
<ul>
  <li>Item</li>
  ...
</ul>
```
In contrast, unordered lists can be used for lists where the order doesn't matter, like a shopping list.


###Emphasized text
Text can be emphasized in HTML using the `<em>text</em>` tag, this is better than the older `<i>` tags, which aren't always picked up by screen readers used by those who are visually impaired.

In a regular browser this is displayed in italics, where as a screen reader will rise in pitch.

###Bold text
Text can also be displayed in bold, this used to be done with the `<b>` tag, but it's now recommended to use the `<strong>` tag instead, for reasons similar to the emphasized text tags.


###Tables
```HTML
<table>               <!--opening table tag-->
  <tr>                <!--opening row tag-->
    <th>Name</th>     <!--define table headers-->
    <th>Age</th>
  </tr>
  <tr>
    <td>Andrew</td>   <!--define table cells-->
    <td>22</td>
  </tr>
</table>
```
As seen above, tables are made up of 3 parts, denoted by the comments.

1. table tags - used to open and close the table
2. table rows - used to open and close a row
3. table headers - used to define a header cell for all cells beneath it
4. table cells - used to define a regular cell


###Doctype
Finally, and also most importantly, you should always start your HTML page with `<!DOCTYPE html>`, this tells your browser that it's adhering to HTML standards.


###Recap
In this section we've looked at some of the common HTML elements and how they should be used for the type of content to be displayed, and never because of how they appear in the browser.



HTML Exercise
----------------------------

Okay, so now that we've learned some of the basics of HTML, but first we need to install a tool to write it with. If you're using Windows I recommend you download either [notepad++](http://notepad-plus-plus.org/) or [crimson editor](http://www.crimsoneditor.com/).

Now let's download our specification for this exercise. You can copy the file contents from [here](https://raw.githubusercontent.com/AndrewSpeed/Web-Development-Fundamentals/master/exercises/html-exercise-unfinished.html).

We're going to pretend that we've been given this template from a customer, who wants a web page that has this content. So to start we'll work on the HTML portion for this exercise.

So, breaking this up into parts, how do we mark up:
1. the text 'Web Developers, Inc.'?
2. site navigation
3. related brands, title of a section
  * the brands inside the related brands section, should it be ordered or unordered?
4. sign up, probably equal importance as related brands
  * the create a user section
5. block of text

Feel free to ask for help or ask someone's opinion. 
__You can also go ahead and Google for a particular tag if you don't know what it is, it's usually best to search for something like 'HTML tag form input' if, for example, you were wanting to find the tag to create input for a form.__

Once you think you're done, get a couple of other people to look it over, these can be the people around you! Discuss it and see what other people think, it's okay to disagree as long as you have a reason for why you made your decision.



CSS
----------------------------

Cascading Style Sheets (CSS), as we've mentioned before, modifies the style of your page's content.

###How do we get it into my web page?
There are 3 possible options, from worst to best.

1. Inline CSS (Bad, don't ever do this) - 
  ```HTML
  <body>
  <h1 style="color: red;">Hello</h1>
  <body>
  ```
  Using the style attribute on an element, you can change the a particular element, but you're mixing your content and style, and also means you have to do this for each element you want to style. *Even control-c, control-v gets boring after a while*

2. Embedded CSS (Okay, but not great either) - 
  ```HTML
  <head>
  <style type="text/css">
    p {
        color: red;
    }
  </style>
  </head>
  ```
  This makes use of the `<style>` tag to affect whatever elements in your page you select inside it, for example in this example we make all paragraph elements red.

3. External CSS (Good) - 
  ```HTML
  <head>
  <link
    rel="stylesheet"
    href="my_styles.css">
  </head>
  ```
  This is the best of all, it uses the `<style>` tag from before, but downloads the stylesheet (that's the one with the .css extension) and applies it to this page. This allows us to write one stylesheet to affect an entire site instead of rewriting all the CSS for each page!


###How does it work?
CSS has 3 parts:
1. Selector
2. Properties
3. Values

For example, first we __select__ the element:
`p { }`

Next we __select the properties we want to change__:
`p { color: }`

Finally, we say what __values we want these properties to have__:
`p { color: blue; }`

So we're going to make all paragraphs have blue text in this example.
You'll notice that there's a special language, or __syntax__ used for CSS, see the diagram below for some of this.
![alt text](https://raw.githubusercontent.com/AndrewSpeed/Web-Development-Fundamentals/master/images/css_syntax.jpg "The syntax can be tricky, so don't worry if you make mistakes.")



###Selectors (thing before the curly braces)
So now that you have a rough overview, we're going to go into a bit more depth.

You select in 4 different ways:
1. elements - select all of a particular element in the page, `p { }` selects all paragraph elements on the page.
2. class - select any elements on the page with that class, `.help { }` selects any elements with the class named 'help'. _("." is how you specify a class name)_
3. id - select the element with the id specified, `#about { }` selects the element with the id 'about', **remember id's should be unique, so it should only be one element selected.** _("#" is how you specify an id name)_
4. position in the document - select the elements contained within one or more other elements.
  ```HTML
  <div id="about">
    <p class="help intro"></p>
    <p class="help"></p>
  </div>
  <p></p>

  #about p {}  <!--Selects any p element inside an element with the id "about"-->
  ```
  The example above selects the first two `<p>` elements, but not the third as it's outside the `<div>` with the id "about"

####Things to watch out for with id's and classes
In CSS, if you select an element using `#help` you'll get only the element with the id "help". 
If you select using a class `.help` you'll select all elements with the class help, including those with other classes.



###Declarations (what we want to change)
CSS defines all properties of an element that you can change (unfortunately using the American spelling), for example:
* `font`
* `color`
* `background-color`
* `border`

Each property has a set of values that can be applied, examples below:
* `font: 12px normal Verdana, sans-serif;` - sets to 12 pixels and font style
* `color: #123;` - set as colour value matching the hexadecimal value 123
* `background-color: red;` - set as system colour red
* `border: 1px solid rgb(193, 193, 193);` - sets the solid border as 1 pixel thick with colour of rgb value 193, 193, 193.

Properties come in a variety of granularity, meaning how much fine detail control you have over them. For example the border example above is high granularity, as you can set the color, and width of each side of a border individually, but we set all 4 at once.

`border: 1px solid #000;` is the same as
```CSS
  border-width: 1px;
  border-style: solid;
  border-color: #000;
  ```

The shorthand used above must happen in that particular order, so if you can't remember it (which no one expects you to) either search for it in Google, or use the longhand version.

Using granularity, we can change specific parts of an element's style
```CSS
p { border: 1px solid red; }
p.intro { border-color: blue; }
```
This gives us a `<p>` with a 1px solid red border, but all `<p class="intro">` have a blue border.



###Units of measurement
We need to talk briefly here about the units used by CSS for determining elements relative size. Obviously we can't use anything like centimeters, as the browser has no way of telling what size monitor you're using.

Instead CSS uses _absolute_ and _relative_ units of measurement.

####Absolute
Absolute units use units that are always the same size, in this case pixels `px`.


####Relative
Relative units such as `em` and `%` are calculated relative to other characteristics.

* `em` - always relative to the current value of font-size, `2em` sets size to twice current font size.
* `%` - relative to different things in different contexts
  * `width: 50%;` - 50% of the available width
  * `font-size: 50%` - 50% of the current font size

For example
```CSS
body { font-size: 12px; }
h1 { font-size: 200%; }
h1 a { font-size: 75%; }
```
This sets body's font size to 12 pixels, the h1 header's font size to twice body's font-size, giving us 24 pixels, and all links inside h1 to 75% of h1's font size, giving 18 pixels.


####Typography (optional)
Additional information on where `em` comes from can be found [here](http://en.wikipedia.org/wiki/Em_(typography)).

Font's are dependent on the fonts available on the Operating System of the computer browsing your web page, generally sans-serif fonts are better for web pages.



###Putting the Cascade into Cascading Style Sheets
It's called Cascading Style Sheets for a reason, and that is because style is applied in the order you define it, meaning the last style defined is the one that takes effect.

There is a catch to this, that last _most specific_ selector is the one that takes effect, this is defined by a points system.

| selector | points value |
| -------- |  ----------- |
| element  |       1      |
|  class   |      10      |
|    id    |     100      |

Some examples of this are:
* `p a {}` = 2 points (2 elements)
* `p.intro a {}` = 12 points (element, class, element)
* `#about p.intro a {}` = 112 points (id, element, class, element)


CSS also has what's known as __inheritance__, this means if we define an attribute for an element, all elements inside it also __inherit__ that property, unless overridden.

Unfortunately, this only applies to text-related properties such as colour, font, alignment, visibility etc. It doesn't apply to layout-related properties like borders, padding, background, etc.


###Layouts
Here we're going to discuss 4 different types of layout used in CSS, and how they affect the positioning of elements on a page.

####Box Model
This is the easiest to understand model, and comprises of _content_, _padding_, _border_, and _margin_. Every box has these properties

The diagram below displays each of these attributes around a box. The box contains the _content_ of the element, and around this is the _padding_, the _border_ surrounds this and then the _margin_ is on the outermost layer. If you set the background on a box element, this will go inside all attributes except the margin.
![alt text](https://raw.githubusercontent.com/AndrewSpeed/Web-Development-Fundamentals/master/images/box_model.png "The box model.")

When settings attributes on the box model using shorthand, defining `CSS margin: 1em 2em;` would set the top and bottom as 1em, and left and right as 2em.

Where as if we define it as `margin: 1em 2em 3em 4em;` this will set the top to 1em, right to 2em, bottom to 3em and left to 4em. This always starts with the top and goes clockwise.

####Display
The two most commonly used attributes of display are _inline_ and _block_.
_Inline_ boxes can appear next to one another, think of this like boxes are represented by words  in a sentence, each word is followed by another.

_Block_ boxes take up an entire line, forcing other boxes onto the next line down.

####Position
This defines where the elements will be displayed in relation to all other objects and will be covered in the exercise later. The only thing you need to know right now is that there are 4 values:
1. static (the default)
2. relative
3. absolute
4. fixed

####Float
Like position, this is best seen in practice as it can be confusing, so we'll cover it in the exercise.


###Recap
So we've seen a lot of stuff, don't worry if you don't remember it all, that's what Google is for! You should hopefully understand the basic concepts of cascading effects and the points system for specifying elements, those are the most important parts.

There are 3 different specifications for CSS, with CSS3 adding some cool new effects which you can go and look up if you want, or you can go straight to the exercise.



CSS Exercise
----------------------------
