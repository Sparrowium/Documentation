A Cascading Style Sheet Language.

<h2><center> Basic </center></h2>

## What is CSS? 

- [CSS]: Abbreviated as Cascading Style Sheets and describes how HTML elements need to be displayed and rendered when represented in a web page format or other media such as **HTML** or **XML**. 
	
- Intended for enabling the separation of appearance with content, which includes layout, coloring, and font styles.
	
- Benefits:
	
	- Compatible with old versions.
		
	- Simple yet independent: CSS is created using tiny modules that compose the application more straightforward and more comfortable to exercise.
		
	- View and change friendly: Because its concepts have been broken down into tiny chunks or modules, it has become easier to alter the elements individually with out particularly disturbing the remaining components.
		
	- Rapid Development since it is not dependent.
		
	- Eye catching backgrounds.
		
	- Images and animations.
		
	- Easier in testing thanks to smaller modules.
	
- File extension: `.css`
## How to create and write CSS code?

- Step 1: Open a text editor.
	
- Step 2: Write CSS code.
	
- Step 3: Save the file with the **.css** extension. This will make the file a CSS Document.

## CSS Syntax

- [CSS Syntax]: consists of three parts, a selector, a property, and a value. However at the fundamental level of CSS, it only has two building blocks that defines how the code perform.
	`property` : Are identifiers that point to different stylistic characteristic.
	`values` : Alter the stylistic characteristic within the web page.
	`{ property: value; }`
	
- [CSS Block Declaration]: are block of declaration wrapped within curly braces `{}`.  Semicolons are used to distinct declaration within a block. It is also recommended to use semicolons on the last declaration to prevent unknown error.
	`class_name { declaration; }`
	
- [Comments]: Comments are written within `/* ... */`
	
- [White Spaces in CSS]: Makes your style sheet more readable or constructive.

## Types of CSS

- [Inline CSS]:
	
	- Are CSS style written inside HTML elements.
		`<elements style=""> ... </elements> `
		
	- Time consuming when it comes to styling multiple HTML elements.
	
- [Embedded CSS]: Are CSS that are embedded into HTML document with the use of `<style>`.
	`<style> /* CSS Code */ </style>`
	
- [External CSS]: 
	
	- Are Style sheets that are implemented into the HTML document through file linking.
		
	- Steps:
		
		- Build CSS by typing CSS code in a plain text files and save it with `.css` file extension.
			
		- Link the Style Sheet into HTML through `<link href=""></link>` element.

<h2><center> Glossary </center></h2>
## CSS Selectors

- [CSS Selectors]: 
	
	- Are used for selecting the substance of your web page you wish to style. These selectors act as the components of the rule set of CSS. CSS Selectors choose elements in HTML based on the class, id, attribute, type, etc.
		
	- Selectors are those names that you give to your different styles.
		
	- In the definition of styles, you define how each selector should work.
		
	- Then, in HTML page, you mention these selectors to implement styles.
	
- [ID Selector]: Can be implemented by writing it with the `#` character, trailing with your desired element's id. It has the highest specificity.
	`#id_name {}`
	
- [Class Selector]: Can be implemented by writing it with the dot `.` character, trailing with the class name. It has the second highest specificity.
	`.class_name {}`
	`element.class_name {}`
	
- [Element Selector]: Can be implemented by using the element name.
	`element_name {}`
	
- [Grouping Selector]: Grouping can be achieved through the usage of comma after each selector's name. Great for code re-usability/organization.
	`selector1, selector2 {}`
	
- [Universal Selector]: Style every single element, implemented by using asterisk `*`. Additionally, there are some properties for Universal selector: `ns|*` match all elements within the namespace ns, `*|*` match simply all elements, `|*` match all element that are without declared namespace.
	`* {}`
	
- [Descendant Selector]: 
	
	- Permits you to add a limitation to any targeted HTML elements, for the one who are offspring or descendants of some other element. Combinators are some concept which is used to explain the association or connection among the selectors.
		
	- [General Sibling Selector]: It is implemented for selecting the element that trails the initial or first selector element and shares the same parent as the first selector element. The general sibling selector is explicitly implemented for choosing a group of elements allocated for the same parent element.
		`element ~ element {}`
		
	- [Descendant Selector]: This selector is implemented to select every child element within the particular tag mentioned in the CSS selector section. The tags may be of the direct child of any specific tag or extremely deep within the particular tag.
		`element element {}`
		
	- [Child Selector]: It is implemented for selecting that particular element that lies within the immediate child of that specific tag. It is more precise or exact than the descendant selector since it chooses only the second selector if it has the first selector element as its parent.
		`element > element {}`
		
	- [Adjacent Sibling Selector]: This selector is implemented for selecting all those elements, which are the contiguous or neighboring siblings of a particular element. 
		`element + element {}`
	
- [Attribute Selector]:
	
	- A particular type of selector that is implemented to select the HTML elements with a specific attribute and/or attribute(s) having any specified value associated with it.
		
	- CSS [Attribute] Selector:  This form of attribute selector is implemented for choosing all of its elements which have the particular attribute, where it applies the CSS property for that attribute.
		`element[attribute] {}`
		
	- CSS [Attribute="value"] Selector: This selector chooses the HTML element having a specific attribute and value.
		`element[attribute=...] {}`
		
	- CSS [Attribute~="value"] Selector: This attribute selector chooses all the elements with an attribute value as a list of space-separated values or a specific word.
		`[attribute=...] {}`
		
	- CSS [Attribute|="value"] Selector: This attribute selector is implemented for choosing elements having a specified attribute that starts with the particular value.
		`[attribute|=...] {}`
		
	- CSS [Attribute^="value"] Selector: This selector is implemented for choosing elements that have their attribute value starts with a particular value.
		`[attribute^=...] {}`
		
	- CSS [Attribute$="value"] Selector: This type of attribute selector is implemented for choosing elements that have attribute value ending with a specific value.
		`[attribute$=...] {}`
		
	- CSS [Attribute*="value"] Selector: This type of attribute selector is implemented for choosing elements having attribute value containing a specified value.
		`[attribute*=...] {}`
	
- [CSS Pseudo Classes]: Pseudo-classes in CSS act as conditions for applying styles to HTML elements. These styles are triggered when certain conditions are met, such as an element's position in the document, its state (like being hovered over), or based on the user's interaction history (like visiting links).
	`selector:pseudo-class { property: value; }`
	
- [Dir Pseudo Class]: Implemented to match HTML elements, depending on the direction of the content contained in them.
	`:dir(direction) {}`
	`selector[dir=direction] {}`

## CSS Properties

- [Color Property]: Used to define colors for HTML elements. Supporting colors format are: RGB, HEX, HSL, RGBA, HSLA.
	`selector {background-color: ... ;}`: Background color for HTML element.
	`selector {color: ... ;}`: HTML text color.
	`selector {border: #FFFFFF ;}`: Border color.
	`selector {color: rgb(0, 0, 0, n) ;}`: Transparency factor `n`. 
	
- [Background Property]: Properties that gives background effects.
	`selector {background-color: ... ;}`: Background Color.
	`selector {background-image: url() ;}`: Background image.
	`selector {background-repeat: repeat-x/y ;}`:Repeat image.
	`selector {background-attachment: ... ;}`: Specify whether the background is `fixed` or `scroll`.
	`selector {background-position: ... ;}`: Define your background position. Either `center`, `bottom`, `left`, `right`, and `top`.
	
- [Font Property]: Defines the font property for your HTML element or your web page.
	`selector {font-family: ... ;}`: Defines the font family.
	`selector {font-style: ... ;}`: Defines the font style.
	`selector {font-size: ... ;}`: Defines the font size in `px`, `em`, `rem`.
	`selector {font-weight: ... ;}`: Defines the shape of your font.
	`selector {font-variant: ... ;}`: Defines whether font should be small caps or not.
	
- [Text Property]: Defines Text property.
	`selector {color: ... ;}`: Defines text color.
	`selector {text-align: ... ;}`: Defines text alignment.
	`selector {text-decoration: ... ;}`: Defines text decorations.
	`selector {text-transform: ... ;}`: Defines the cases of your text.
	`selector {text-indent: ... ;}`: Defines text indentation.
	`selector {line-height: ... ;}`: Defines spaces between lines.
	`selector {letter-spacing: ... ;}`: Defines spaces between letters.
	`selector {text-shadow: ... ;}`: Defines text shadows.
	
- [Padding Property]: 
	
	- Defines padding value either in percentage `%`, length `px pt cm etc`, or `inherit` from parent element.
		
	- [Short Hand Padding]: Specify padding property in a single property. ex: `padding: 30px, 45px, 65px, 90px`.
		4 values: top `30px`, right `45px`, bottom `65px`, left `90px`.
		3 values: top `30px`, right and left `45px`, bottom `65px`.
		2 values: top and bottom `30px`, right and left `45px`.
		1 value: all are `30px`.
		
	- [Padding with Width]: Padding is included with element total width.
	
- [Margin Property]: 
	
	- Defines margin value either in `automatic`, percentage `%`, length `px pt cm etc`, or `inherit` from parent element.
		
	- [Short Hand Margin]: Specify margin property in a single property. ex: `margin: 30px, 45px, 65px, 90px`.
		4 values: top `30px`, right `45px`, bottom `65px`, left `90px`.
		3 values: top `30px`, right and left `45px`, bottom `65px`.
		2 values: top and bottom `30px`, right and left `45px`.
		1 value: all are `30px`.
		
	- [Margin value Auto]: Used to center HTML element horizontally in its containers. Syntax: `margin: auto`
		
	- [Margin value Inherit]: Inherit margin from parent element.
	
- [Border Property]: Defines border property.
	`border-color`: Defines border color.
	`border-style`: Defines border style.
	`border width`: Width/thickness of the border.
	`border: value style color`: Border shorthand Property.
	`border-radius`: Rounded border.







