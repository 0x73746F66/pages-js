[logo]: https://raw.github.com/chrisdlangton/pages.js/master/logo.png "PagesJS Logo"
[1]: http://pagesjs.chrisdlangton.com/
[2]: http://chrisdlangton.com/

[PagesJS JavaScript Micro-Framework][1]
========

![PagesJS Logo][logo]

[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=chrisdlangton&url=https://github.com/chrisdlangton/pages.js&title=PagesJS&language=&tags=github&category=software)

# Official Website
[pagesjs.chrisdlangton.com][1]

Full usage documentation of features always running on the latest dev version of PagesJS.

# What is PagesJS

PagesJS is a small JavaScript Framework originally built as an experiment in designing single page applications. 

As PagesJS evolved it aimed to solve the common problems associated with writing this new style of application. It became clear early on that PagesJS was well suited for building simple single page applications without the requirement of heavier libraries or frameworks to perform simple DOM related functions.

PagesJS tries to achieve this by providing a small 'core' framework and an ever-growing list of methods for specific functionality. The core is a simple selector API familiar to jQuery that allows the developer to switch between your single page web app 'pages' seamlessly in the most minimal way possible.

PagesJS is not a solution for every JavaScript application or problematic situation. It is a solution for small single page apps using no framework and also some larger applications using one or more frameworks, to have a simple interface that allows the developer to bring in and hide from view 'page' elements while allowing each 'page' to be bookmark-able and seamless to the end user.

# Why PagesJS

The name came from the single-page application experiment.

In the modern age of super-fast browsers and user expectations about the responsiveness and perceived speed of web applications - single page AJAX applications have become the rage (GMail for example.) Furthermore, instead of just fetching full HTML and rendering it asynchronously, fetching raw data (JSON) and rendering on the client side has not only become possible - it's actually very common.

_Pages.js has no dependencies - It is a pure JavaScript Library._

### PagesJS provides;

* A simple API.
* No dependencies.
* Well documented methods.
* Browser history support for all device and browser versions.
* Bookmarking.
* Meta data updating per page, contributing to Social Media optimisation.
* SEO - Google indexing conformance.
* Google Analytics and ReInvigorate page view reporting.
* Optimises performance on newer browser using the latest functionality with fall-backs for older browsers.
* Page change event binding, executed specific to individual pages.
* Uses a namespace to prevent conflicts.
* Object constructor preventing multiple instances.
* Contextual targeting of DOM elements and their manipulation.
* Object literals to pass optional arguments to most methods.
* Optional user-defined function call-back when using the navigation method to apply additional custom logic automatically and instantly after navigation.

PagesJS was originally built alongside Knockout.js as the only other JavaScript library present and therefore doesn't include any of the MVVM features or binding which would have overlapped with that particular library, but it does however share a lot of common functionality to jQuery which was not present in the experiment application but the functionality was required so I built it into PagesJS instead of having jQuery as a dependency.

# How does it work?

PagesJS will listen for the browser onhashchange event if it is supported (FF3.6+, IE8+, Chrome 5+, Safari 5+, Opera 10.6+) or it will fallback to pooling the window.location on an interval to check if hash value changed. 

# How to use PagesJS

## Installation:

Download the latest PagesJS or Pages.min.js file from this repository and upload it to your public javascripts directory. 

Include the script in your html body after all the content (at the bottom of the body element) like so;

```html
<script src="javascripts/Pages.js/Pages.min.js" type="text/javascript" charset="utf-8"></script>
```

Each 'page' element needs to be defined with the custom attribute 'page' with a value defined that will be used as the hash bang (#!) tag in your url for navigation.

```html
<div class="container" page="home">
    site home page content
</div>
<div class="container" page="about" page-title="All About Me">
    about me page content
</div>
<div class="container" page="contact">
    contact us page content
</div>
```

## Basic Usage:

As long as each page attribute is defined and PagesJS included, you can navigate to any one of these 'pages' using the hash bang (#!) in your url.

For example type in http://myappdomain/#!contact will show you the element with the page attribute equal to the hash bang (#!) value 'contact' and hide all other elements with a page attribute defined that do not equal the hash bang (#!) value 'contact', i.e. 'home' and 'about' will be hidden.

Alternatively it is likely that your application will have a menu to navigate each page. Set the href for each anchor to the hash bang (#!) value, like so;

```html
<a href="#!home">Home</a>
<a href="#!about">About me</a>
<a href="#!contact">Contact me</a>
```

Then clicking each will navigate through the pages appropriately.

## Using the selector:

The selector is similar to the jQuery implementation, where you can select by element ID or class name but also includes a selector for 'page' attribute value.

* Hash ( # ) is used to select by ID. 
* Period ( . ) is used to select by class name. 
* Underscore ( _ ) is used to select by the page attribute value.

_Note: the selector expects the ID and Page references to be unique and will therefore select only the first instance of the reference, where as the class name selector returns all element nodes matching the class name reference and you will then need to run them through the .forEach() method or one of the prototype methods that support multiple nodes in the selector._

Examples:

```javascript
p('#main'); // returns nothing because there is no element with ID 'main'
p('_about'); // returns the single element with the attribute value equal to 'about'
p('.container'); // returns all three elements that have the class 'container'
```

# Documentation

A full guide to PagesJS is made avaialble at: [pagesjs.chrisdlangton.com][1]

## Change Log

#### Version: 1.0 Latest (Feb 22 2013)

* Project offical name now PagesJS, code comments and log text updated.
* page() namespace now p() only.
* All code in now within the page namespace
* New basic setup requirements initilisation and &lt;head&gt; elements
* .init() prototype method
* prevent init being used multiple times
* Selector updated to provide functionality to .init() prototype method
* hash property added and references changed
* canonical property added and references changed
* page_title property added and references changed
* .nav() updated to take properties, currently only 'title' has functionality.
* 'page-title' custom element attribute sets the webpage title upon navigation.
* .title() prototype method
* .hasClass() prototype method
* .change() prototype method
* exist() and nav() chain fix for init() method
* fix for document.title issues in Opera and Mozilla
* hashchange fallback for popstate
* Included property for callback function in .nav() prototype method

#### Version: 0.9 (Feb 11 2013)

* slight code restructure removing redundant components
* .capitalize() prototype method
* .inverse() prototype method
* .reverse() prototype method
* .contains() prototype method
* .clear() prototype method
* .camelCase() prototype method
* .ltrim() prototype method
* .rtrim() prototype method

#### Version: 0.8 (Feb 10 2013)

* Canonical URL updating per Google Webmaster instructions
* Hash bang (#!) URLs per Google Webmaster instructions

#### Version: 0.7 (Feb 09 2013)

* Google Analytics Page Visit Tracking
* ReInvigorate Page Visit Tracking
* Update page <title> to include (append) the hash value
 
#### Version: 0.6 (Feb 07 2013)

* .goTo() prototype method
* document readystate fix

#### Version: 0.5 (Feb 05 2013)

* page() element class selector
* .getElementsByClassName fix
* .forEach fix
* .forEach() prototype method
* .trim() prototype method
* .stringify() prototype method
* .parse() prototype method
* .append() prototype method
* .prepend() prototype method

#### Version: 0.4 (Jan 22 2013)

* .disable() prototype method
* .enable() prototype method
* .remove() prototype method
* .empty() prototype method
* .html() prototype method
* .val() prototype method

#### Version: 0.3 (Jan 20 2013)

* .indexOf fix
* .exist() prototype method
* .toggle() prototype method
* .style() prototype method
* .addClass() prototype method
* .removeClass() prototype method

#### Version: 0.2 (Jan 17 2013)

* page() element page attribute selector
* hash and page attribute controls
* document readystate navigation for bookmarking
* .attr() prototype method
* .addPage() prototype method
* .removePage() prototype method
* .hide() prototype method
* .show() prototype method

#### Version: 0.1 (Jan 07 2013)
 
* page() element id selector
* .nav prototype method
