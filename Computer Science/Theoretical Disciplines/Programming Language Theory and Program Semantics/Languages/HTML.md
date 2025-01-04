A Hyper Text Markup Language.

<h2><center> Basic </center></h2>

## What is HTML?

- [HTML]: the basic building block of the Web. It defines the meaning and the structure of web content through elements such as tags. 
	
- The word in **Hyper Text** in HTML refers to a "Link" that connect the web pages from one to another, either in a single website or between websites. 
	
- HTML uses **markup** to annotate text, images, an other content for display in Web Browser. (ex: <!head>, <!title> )
	
- An HTML element is set off from other text in a document by **tags**, which consist of the element name surrounded by `<` and `>` . The name in the tags are case-insensitive. Which means that I can be written as lower case, upper case but lower case is preferred for normal convention.

## How to create and write HTML code?

- Step 1: Open a text editor.
	
- Step 2: Write HTML code.
	
- Step 3: Save the file with the **.html** extension. This will make the file a HTML Document
	
- Step 4: Run the HTML page in your browser via open the file in your browser.

## What is a HTML DOCTYPE?

- [HTML Doctype Declaration]: a reference to a Document Type Definition (DTD). A DTD refers to an **XML** (extensible markup language) document format representing allowed elements in a web page. It informs the web browser the HTML version and standard in which the current page is written; this helps different web browsers to parse the web page correctly. The Doctype Declaration is neither a tag or an element in HTML, its a null element with no closing tag.
	
- It should be on the first line at the top of all other content on the web page.
	
- Syntax: `<!DOCTYPE html>`

## HTML Tags

- [HTML Tags]: Are hidden keywords or commands incorporated in HTML, which can be define how your browser will display the content and format of the page. Most HTML tag have 2 sections: **Opening** ( < ... > ) and **Closing** ( </ ... > ), and any text written in between the tags will carry the tags effects upon them. 
	
 - [HTML Document]:
	
	- All HTML documents begin with `<!DOCTYPE html>` 
		
	- The HTML document begins with `<html>` and ends with `</html>`.
		
	- HTML code that is written inside the `<head>` and `</head>` tags of an HTML document are not visible in the web browser. 
		
	- Only the content inside the `<body>` and `</body>` are displayed in the browser
	
- [HTML Tag]: `<html> ... </html>` 
	
- [HEAD Tag]: `<head> ... </head>` used to add the header in HTML. It is also used to give various additional information about the web page along with description, configuration and title to your page, which gets display in the title bar or acts as an indicator of what information to use or on which page you are currently in. The Title Tag `<title> ... </title>` is also in written within the `<head>` tag.
	
- [BODY Tag]: the `<body> ... </body>` tag is used to display information of the HTML document. All formatting and writing of content are done in this section within the `<body>` and the `</body>`. If your HTML code does not have it, the code will still run but nothing will be displayed. Noted that, `<body>` needs to be inside the `<html>` tag.

## HTML Elements

- [HTML Element]: A combination of HTML tags and content within the opening and closing tags.
	
- [Nested HTML Elements]: HTML elements can be nested by writing another element before closing the previous element.
	
- [Heading Elements or `<hn>` Elements]: HTML has 6 different sizes heading ranging from 1 -> 6. In addition, Web browser will automatically add one line prior/following to make it look neat.

## HTML Attributes

^3881c6

- [HTML Attributes]: An HTML attribute is a property named used to provide supplementary information about HTML elements. Some common examples of HTML attributes are id, class, align, etc. Many attributes are defined globally and are applied to any element, whereas we use some of them only for specific HTML elements.
	
- Syntax: `<element_name attribute_name="value"> .... </element_name>`
	
- #Note: Names of attributes and their values are not case-sensitive. But according to the World Wide Web Consortium (W3C), it is recommended to use lowercase names and values. The value defines the value which you want to assign to the property and is set within quotations.
	
- [Core Attributes]: 
	
	- [ID Attributes]: Assign a unique identity to an element. 
		`<p id="..."></p>`
		
	- [Title Attributes]: Gives a recommended title for your element.
		`<h3 title="..."></h3>`
		
	- [Class Attributes]: This attribute is implemented by combining an element through a stylesheet (CSS) and identifying its class element.
		`<p class="..."></p>`
		
	- [Style Attributes]: This attribute gives you a chance for specifying the rules for Cascading Style Sheet (CSS) in your element.
		`<p style="..."></p>`

## HTML Formatting

- Formatting can be defined as the appearance of your documentation or presentation of your HTML code in a meaningful and more beautiful way.
	
- [Formatting Tags]: Refer to [HTML W3C](https://www.w3.org/TR/WD-html40-970708/index/attribs.html)

## HTML Comments

- Provide the details of what is written in the HTML source code. HTML comment tags are completely ignored to display by the browsers.
	
- Syntax: `<! -- ... -->`

## CSS in HTML

- Cascading Style Sheets (CSS) describes web content's visual presentation and layout.
	
- Ways to implement CSS into HTML: 
	
	- [Inline CSS]: Include the style attribute in the relevant element and specify any CSS property. Useful for making quick changes to the appearance of individual elements
		
	- [Internal CSS]: Styling a single HTML document without affecting other pages. To add internal CSS, insert a `<style>` tag in your HTML page's `<head>` section. Within the `<style>` tag, you can declare CSS rules that apply only to that page. It is more efficient than inline CSS because it allows you to style multiple elements on a page with a single CSS rule.
		
	- [External CSS]: To add external CSS, link to a separate CSS file using the HTML `<link>` element in each HTML page's `<head>` section. Useful for styling multiple pages because it allows you to make changes to the CSS in one place and have those changes reflected on all of your pages.

<h2><center> Glossary </center></h2>

## HTML Tag

- `<head>` Tag: The `<head>` tag in HTML is a container for metadata (information about the document, such as its title, scripts, and style sheets) that is not directly related to the page's content.
	```<head> ... </head>```
	
- `<meta>` Tag: Meta tags are text snippets in the form of data that depict the content of your page. Their value do not emerge on the web page you create but  can be seen in the source code of your HTML page. Meta tags act as small content descriptors that allow you to convey to search engines what your web page is about and what keywords it contains It is to be noted that the HTML `<meta>` tag comes within the `<head>` tag.
	`<meta> ... </meta>`
	
- `<body>` Tag: Defines the main content of an HTML document. It encloses all of the content displayed in the web browser when the page is loaded, including text, images, links, and other HTML elements. It can also have HTML Attributes.
	`<body> ... </body>`
	
- `<hn>` Tag: These tags are used to create headings and subheadings in an HTML document ranging from 1 -> 6. The headings are hierarchical, with the main heading being the largest and the subheadings getting progressively smaller.
	`<hn> ... </hn>`
	
- `<a>` Tag: The Anchor tag in HTML can be defined as a means to create a hyperlink that can link your current page on which the text is being converted to hypertext via `<a>` (anchor tag) to another page. This anchoring from one page to another is made possible by the attribute `href`, which can be abbreviated (hypertext reference). They change color based on certain situations, such as unvisited, clicked, visited, etc.
	`<a href=""> ... </a>`
	
- `<img>` Tag: Used to add images into our web page. Noted, `<img>` is an empty tag (no ending tag). In addition, `<img>` tag comes with 2 default attributes called `src` and `alt`. `src` attribute instruct your web browser from which location it should fetch the picture, `alt` defines an alternative text in case your browser failed to load the image.
	`<img src="http://example.com/wallpaper.jpg" alt="Wallpaper">
	
- `<ol>, <ul>, <dl>` Tag: These are listing with `<ol>` stands for ordered list, `<ul>` stands for unordered list, `dl` stands for definition list. These tags also offers `type= ...` attribute to customize your list. In addition, listing elements `<li>` are used in `<ol>` and `<ul>`, `<dt>` and `<dd>` are used in `<dl>`.
	`<ol> ... </ol>`
	`<ul> ... </ul>`
	`<dl> ... </dl>`
	
- `<table>` Tag: An HTML table is a way of displaying data in rows and columns. The table comprises three main tags: `<table>`, `<tr>,` and `<td>`. The `<table>` tag defines the table, the `<tr>` tag defines the table rows, and the `<td>` tag defines the table cells. In addition, the `<th>` tag is used within the `<table>` tag for defining the heading for your table data. Finally, `<table>` supports attributes and nesting.
	`<table> ... </table>`
	
- `<div>` Tag: Known as division tag and it is used for creating content segmentation in a web page. It can be used to replace almost all block-level tags while note affecting the context of the layout of the document. 
	`<div> ... </div>`
	
- Phrases Tag: Phrase tags are unique purpose tags designed to use indefinite cases.
	`<em>` : Emphasizes the text.
	`<mark>` : Highlight the text.
	`<strong>` : Makes the text becomes bold.
	`<abbr>` : Create an abbreviation when hovering on the text.
	`<dfn>` : Defines a new term and display it in Italic.
	`<blockquote>` : used to add a quote to a passage from a different source.
	`<q>` : add a double quote to your text.
	`<code>` : visualize the text as mono-spaced font (programming font)
	`<kdb>` : defines the text as input from the keyboard by highlighting it.
	`<address>`: used to specify a set of text that is an address.
	
- `<blockquote>` Tag: Tag that display long quotes. It is recommended to use the `cite=` attribute to create a citation. It also supports attributes
	`<blockquote cite=""> ... </blockquote>`
	
- `<button>` Tag: Creates a clickable button in the web page. The content's images and text can reside inside that `<button>` tag. In addition, there are various `<button>` tag attributes.
	`<button type=""> ... </button>`
	`type=` : Declare a specific type of button.
	`name=` : Specifies a name for the button.
	`value=` : Specifies a default value.
	`disabled=` : Disable the button.
	`onClick=` : Specifies a special attribute when clicking the button.
	`form=` : Specifies the form that the button belongs to.
	
- `<textarea>` Tag: creates a multi-line text input field for users to enter long text into a web page. It also supports attributes to further customize the tag.
	`<textarea rows="" cols==""> ... </textarea>` 
	
- `<link>` Tag: Establishes a link between the current document and an external resources. The `<link>` tag comes with 2 default attributes, `rel=` specifies the relationship of the documents, `href=` refers to the location of the linked resource.
	`<link rel="" href=""> ... </link>`
	
- 