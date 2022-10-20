<label>Lecture 01 - 2022/10/04</label>
# Introduction
Outline,
	1. Internet, its history and its functionality
	2. Protocols
	3. IP addresses

# Internet Fundamentals
Internet It is a worldwide network of computer networks.
	- Follow standard communication rulesets. *Ex: RSS, HTTP, HTTPS, WSS, SMTP*
	- It is designed to interconnect all types of networks.
	- No one controls or owns the internet, but to connect to is you need a machine that obeys the protocols.

Internet vs WWW?
	- Internet is a network and www is a service inside it. There are many other services running on top of the internet, like Mail services etc.
	- The internet is just a wide spread network of devices, services that run on top of it may vary in nature.

## How the internet works
It is based on a client server model. In this model,
	- Each computer is given a unique address to be identified with.
	- Both the client and server computers follow the same protocol to communicate data.

Two technologies commonly followed in the client server model,
	- Pull technology,
		Client initially requests the desired data and the server provides it.
	- Push technology,
		Client initially requests the desired data and the server establish some sort of autonomous data retrieval method so that the server can push data to the client freely.
			- This is normally done by running some sort of service worker on the client device.
			- It is widely used to keep real time communications up and running.

## Internet Protocols
What is a protocol? A set of rules that govern the data communication over a network.

What is the internet protocol suite? A set of communication protocols used in the internet and similar computer networks.
	1. TCP  : Provides reliable transmission with slower speeds.
		- Checks for errors
		- Acts as a transport layer
		- It is connection oriented
		- Used at reliability is needed over speed.
	2. UDP  : Faster transmissions but it is not reliable.
		- It is not connection oriented
		- Used for VOIP (Voice over IP), Streaming and cases where speed matters over security.
	3. IP   : 
	4. HTTP : 
	5. SMTP : 
	6. WAP  : 
	7. POP3 : 

## Evolution of the internet
Internet was based on the idea that there would be multiple independent networks of rather arbitrary design, beginning with the ARPANET as the pioneering packet switching network, but soon to include packet satellite networks, ground-based packet radio networks and other networks.
	- Department of defense developed USA ARPANET.
	- Late 1980s' US National Science foundation started exploring ways to enable access of their supercomputer to researchers.
	- [Tim Berners Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee) created the WWW in 1990
	- At first WWW was a house of documents to store information

***

<label>Lecture 02 - 2022/10/14</label>
# Introduction to HTML
HTML (Hyper Text Markup Language) is a language for specifying how text and graphics appear on web page, it is primarily responsible for structuring content in a webpage. Browsers render HTML to a presentable form. An HTML file is a text file containing small markup tags ending with the `.html` file extension.

## Structure of a HTML document
An HTML document is composed of many embedded HTML elements, following a similar syntax to XML (A data serialization format).

An HTML element is defined by wrapping a specific tag in `<>` symbols, once a tag is opened it must be closed to embed content into the tag. Some tags do not require a closing tag, but as a modern coding standard when opening a tag that has no closing tag it is closed within the end of the opening tag itself. 

Browsers use tag attributes specified in the HTML to implement certain behaviors to the content by tweaking how the browser engine render the elements. Comments in HTML is written inside `<!-- COMMENT -->` tags.

```html
<tag>content</tag>
<tag attribute-name="attribute-value">content</tag>

<tag /> <!-- Closing a tag with no closing tag -->
```

The document can be divided to 2 main sections,
	1. Head
		The HTML head mostly contains meta related to the page, external style sheets or external sources and other major components that the rest of the page depend on, as it is loaded first and is not rendered to the client. (It is rendered by there is no visual presence of it)
	2. Body
		The body is everything that the user visually interprets and contains the page content.

## Basic Structure of a HTML document

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="..."/>
		
		<title>Page title</title>
		
		<link rel="stylesheet" src="index.css" />
		<script src="index.js"></script>
	</head>
	
	<body>
		<header>
			<h1>Page header</h1>
			<nav>
				<a href="#about-us">About Us</a>
			</nav>
		</header>
		
		<main>
			<section>
				<h2>Title</h2>
				<p>Content</p>
			</section>
			
			<article>
				<h2>Artivle title</h2>
				<p>Article title</p>
			</article>
		</main>

		<footer>
			<p>Somecompany all rights reserved @2022</p>
		</footer>
	</body>
</html>
```

## Several HTML tags and Usage

1. HTML tag: The HTML tag enclosed all the other HTML tags and associated text within your document.
2. Head tag: Comes after the html tag, it is not rendered to the users screen.
3. Body tag: Comes after the head tag, it contains all the content that is rendered for the user to consume.

```html
<html lang="en">
	<head></head>
	<body></body>
</html>
```

4. Heading tags: There are 6 heading sizes and 6 heading tags respectively. 

>[!WARNING] Proper use of heading tags effect the page's SEO performance.
>Sub-headings must be followed by a main-heading, following the hierarchy of heading sizes.

```html
<h1>Main Heading</h1>
<p>Content</p>

<h2>Sub Heading</h2>
<p>Content</p>
```

5. Paragraph tag: This tag is used to indicate paragraphs.
6. Line Break tag: Used to indicate line breaks.
7. Horizontal Rule tag: Used to draw an horizontal line across the x axis, useful at times where text, sections need to be separated.

>[!WARNING] White spaces and line-breaks
Browsers ignore extra white space within the document, trailing whitespaces do not effect on how the DOM is rendered. Browsers ignore extra line and paragraph breaks, line breaks must explicitly be declared by using the `<br />` tag.

```html
<p>
	Name: Someone <!-- Line break won't be picked up by the browser -->
	Age : 00
</p>

<hr />

<p>
	Name: Someone
	<br /> <!-- Line break is rendered by the browser -->
	Age : 00
</p>
```

8. Preformatted Text tag: This tag can be used instead of the paragraph at places where it requires total control over spacing and line breaks.
	This tag is normally used for presenting code blocks or poems etc. where line spacing and line wrapping and second hand manipulation of text may heavily alter the contents intended use.
	
```html
<pre>
	import time
	print("Time right now:", time)
</pre>
```

9. Character Formatting tags
	There are several tags that can be used to format text, their use is self explanatory.
	
	- Boldface tag
	- Italics tag
	- Underline tag
	- Subscript tag
	- Superscript tag
	- Small tag
	- Big tag
	- Strong tag

```html
<p>
	<b>Used to render bold text</b>
	<i>Used to render italic text</i>
	<u>Used to underline text</u>
	
	<sub>Used to render subscript text</sub>
	<sup>Used to render superscript text</sup>
	
	<small>Used to render small text</small>
	<big>Used to render big text</big>
	<strong>Used to render strong text with higher font weights</strong>
	<!-- The small and big tags alter the font-size while the strong tag alters the font-weight -->
</p>
```

10. Font tag: Used to change the font face/family of the text that is render. It's functionality is replaced by CSS.

***