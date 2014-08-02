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


###Recap
In this section we've looked at some of the common HTML elements and how they should be used for the type of content to be displayed, and never because of how they appear in the browser.
