A Hyper Text Markup Language.

<h2><center> Basic </center></h2>

## What is HTML?

- [HTML]: the basic building block of the Web. It defines the meaning and the structure of web content through elements such as tags. 
	
- The word in **Hyper Text** in HTML refers to a "Link" that connect the web pages from one to another, either in a single website or between websites. 
	
- HTML uses **markup** to annotate text, images, an other content for display in Web Browser. (ex: </head>, </title> )
	
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

- [HTML Attributes]: An HTML attribute is a property named used to provide supplementary information about HTML elements. Some common examples of HTML attributes are id, class, align, etc. Many attributes are defined globally and are applied to any element, whereas we use some of them only for specific HTML elements.
	
- Syntax: `<element_name attribute_name="value"> .... </element_name>`
	
- #Note: Names of attributes and their values are not case-sensitive. But according to the World Wide Web Consortium (W3C), it is recommended to use lowercase names and values. The value defines the value which you want to assign to the property and is set within quotations.