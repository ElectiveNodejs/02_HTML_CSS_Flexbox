# 02_HTML_CSS_Flexbox
Day 2 - Introduction to frontend technologies



## Part 1: HTML5  `<Basics>`

1999, Switzerland: Tim Berners-Lee created a network of documents, written in a language called the HyperText Markup Language (aka HTML), which made these documents available and recognizable by this network, which we commonly know under the name of the World Wide Web or WWW.

HTML was created with the aim of being human-readable and easy to understand.
Code editing at the time when HTML was invented had less of a stylistic purpose, rather more of an informational one.

HTML’s specifications evolved through time and changed under new emerging standards. Today, the most up-to-date and complex version of it is HTML5, which is constantly regulated by the W3C - WWW Consortium.

HTML5 is an instrumental technology for building the most important blocks that make up the Internet today: web apps.

Elements of HTML5 documents:

1. The document type declaration: `<!DOCTYPE html>` 

2. The Document Object Model (DOM): a description of the webpage 
  Understanding the DOM is fundamental!
  Abstraction: The DOM is not actually the written code, rather the output of it, the result in the browser.
  One of the cool things about the DOM is that it can be manipulated after it has been rendered in the browser by using JavaScript.

3. The Tags & Elements: sub-elements of the DOM

	Multiple nesting levels possible: **parents & children**

	Tags on the same level: **siblings**



	Tags are extremely important for CSS as well.

	**HTML Tags**

	The “sandwich”:
	  `<tag>`
		 `content… `
	  `</tag>`

	Start with the content you have in mind, and then wrap the corresponding tag around it

		E.g.: a paragraph: “Hello, there! How are you?” (the content)
			 in the HTML: `<p> Hello, there! How are you? </p>`

	Tags can have attributes, which are key-value pairs that define some of the propertiesand functionality of that particular tag.

	E.g.: `<a href=”http://somepage.com” … </a>`

		a => anchor tag

		href => attribute

		http://somepage.com => value of the href attribute

	Some tags may be more ambiguous: `span`, `div`

	Headings: `<h1>`, …, `</h6>` - very important for Search Engine Optimization (SEO)

	Lists: `<ul>`, `<ol>`, `<li>` - unordered list, ordered list, list item

	Images: `<img src=”www.img.org” alt=”picture of a dog”>` - the image tag, with the `src` attribute and `alt`, which represents the 	fallback of the img, if it cannot be loaded (also matters for SEO)

	Division: `<div>`



4. Semantics: the usage of appropriate elements or tags

	Respecting semantics makes it easy:
	* To understand the code and context of it
	* For the markup to be device-agnostic (recognized in the same way by multiple devices)

	Applying the usage of common conventions: enhances effective communication in teams, for instance, and across the WWW.

	Regarding tags, semantics tell us that we should use the tag that best describes the content that we’re marking up.

	E.g.: navigation items should go under the `<nav>...</nav>` tag

	Some HTML5-specific tags:
	`<header>`
	`<footer>`
	`<section>`
	`<article>`
	`<nav>`
	`<figure>`

	Others:
	`<form>`
	`<input>`
	`<select>`
	`<textarea>`
	`<button>`

	Check out this [HTML5 cheatsheet](https://websitesetup.org/HTML5-cheat-sheet.pdf) for a complete list.

## Part 2: CSS {Basics}
CSS is a stylesheet language, used for applying different styles to the HTML elements that we add to the DOM.

CSS is the one that does a very important job in making webpages usable. HTML has a very minimal range of control over the style, and CSS appeared due to the need to better separate the concerns of the two: function and form.


CSS-specific rules & tools:
1. How to apply CSS rules: inline, embedded, external.

	* Inline

		E.g.: `<p style=”color: red;”>This is a styled paragraph.</p>`

	* Embedded

		Between the `<style> </style>` tags in the head of the HTML document.	

	* External 

		Linking to an external `.css` file, containing all the appropriate styles - the link is added in the head of the HTML doc: 

		<link rel="stylesheet" href="style.css">

	Read:	[https://www.thoughtco.com/types-of-css-styles-3466921](https://www.thoughtco.com/types-of-css-styles-3466921)

2. Style declarations

	`selector {`

	  `property: value;`

	`}`



	CSS stands for Cascading Style Sheets - and the “cascade” in it refers to the fact that:

	a) One simple style can affect multiple elements, so all of the targeted elements will have applied the same set of rules. In the 	  same fashion, it is possible to link the same stylesheet to multiple pages, so that all will have the same styles applied to them.

	E.g.: change the style of all paragraphs by targeting p and all the paragraph elements will have their styles changed


	b) One HTML tag can be affected by many styles.

	E.g.: if the same element is targeted from 2 different stylesheets, or in 2 different ways, both styles will try to apply the 		rules to the element.


	c) The last rule overrides them all. And specificity matters a lot! 

	E.g.: targeting `#box1 { … }` is more specific (refers to only one element) than saying `div { … }`


	Read [https://developer.mozilla.org/en/docs/Web/CSS/Specificity](https://developer.mozilla.org/en/docs/Web/CSS/Specificity)


3. Selectors - used to identify specific HTML documents in order to give them the style wanted. 

	You can simply select an element by its name.


	E.g.: 
		HTML: `<p> Hello </p>`
	        
	      CSS: p { styles... }


	In order to better target these elements, we can add two special attributes, called `id` and `class`.

	E.g.: `<a href=”#” id=”btnId”>Home</a>`
     
     	     `<a href=”#” class=”btnClass”>Home</a>`


	The way they are targeted in the CSS is like this:

	`#btnId { styles }`

	`.btnClass { styles }`

	The main difference between the 2 types of selectors is that the id is meant to be used for a unique element and an element should have only one id, whereas a class is meant to cover an entire category of multiple elements, and one element can have multiple classes.

	Read: [https://developer.mozilla.org/en-US/docs/Web/CSS/Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)


4. Specificity

	Overruling cascading styles by specifying clearly which element is targeted.

	HTML:
	`<article>`
		`<p> This is a paragraph inside an article. Let’s target this element. </p>`
	`</article>`

	CSS:

	// before:  `p {color: red;} p{color: blue;}` - the paragraph will take the color blue

	// after: `article  p{color: red;} p{color: blue;}` - the paragraph inside `<article>` will take the color red.


	This happens because the declaration with `article p` is more specific than the second one.

	Specificity calculator: [https://specificity.keegan.st/](https://specificity.keegan.st/)




5. Positioning 

	**Static** - default; elements with this position cannot be moved using directional properties (`left`, `right`, `top`, `bottom`)

	**Fixed** - these elements are going to remain in a fixed position, rendered at the exact directional property values given to it, from the top-left corner of the window

	**Relative** - elements whose position is going to be relative to where they are normally rendered

	**Absolute** - elements that are rendered at the absolute direction values given, but don’t stay in a fixed position (this applies inside its nearest parent)




6. Display Types




7. Centering and placing elements in the DOM
