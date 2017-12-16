---
layout: post
title:      "What the Bleep is Specificity???  "
date:       2017-12-16 23:41:04 +0000
permalink:  what_the_bleep_is_specificity
---


**So, this is so much more complicated than the order of operations in math class.**  

In CSS, cascading style sheets, you can style the heck out of your HTML and if you don't take specificity in to account you are going to end up with a hella mess on your hands.  

**First there is CSS Syntax**

Selector {property: value} where everything inside the curly brackets is a declaration.  

**Second you need to understand External, Internal CSS Stylesheets and Inline Styles **

1. **External Stylesheets**-  This is a .css file that you link your website to.  When you change your .css sheet it will affect every page of your website.  (Great for Global site changes so you don't have to make changes in every single page of code) 

2. **Internal Stylesheet**- This holds the CSS code for your webpage in the < head > section of your file.  (Great for applying styles like classes or id's so you can reuse the code) Unfortunately changes in this stylesheet only affect the page the code is actually on.  

3.  **Inline Styles**-  Styles that are specific to the tag itself.  (THESE ARE NOT RECOMMENDED) Every change made to that tag will change every tag that has the inline style applied to it.  So, this is only good to use on one specific CSS change and not used throughout your website.  

So obviously this is why we have an html code file and we have a css code file.  We then link our web pages to our .css styling by putting a link in the head of each page.  The person viewing the web page won't see this, but it will allow us to style the pages of our website.  (This is using an External Stylesheet)  

**What is a Selector?  **

HTML has < tags >.  CSS has SELECTORS.  We use the tags in our HTML to change the style of a specific type of element.  

Your < p > tag for a paragraph can be used as a selector to determine attributes or styling we want to give to our HTML.  

For each Selector {you have properties and values here} 

**Properties can be:  **

*Text and Fonts*


*Colors and Backgrounds*


*The Box Model: margins, padding, and borders*


*Visual Formatting: dimensions, display, and positioning*


*Generated Content and Lists*


*Tables*


*Media*


*Transitions*


*Transformations*


*Miscellaneous*

For a detailed list of properties and their selectors check out:  [http://www.htmldog.com/references/css/properties/]




**Let's Compare Selectors**

A SELECTOR is the element that is linked to a particular style.  

                          selector {property:value}

A CLASS SELECTOR is a selector that uses a defined lass. (MULTIPLE PER PAGE)  

                          . selector {property:value}

An ID SELECTOR is a selector that uses an individually assigned identifier. (ONE PER PAGE)

                          #selector {property:value}
													
An ATTRIBUTE SELECTOR matches elements which have a specific attribute or its value.

                          [selector] {property:value}
													
A PSEUDO CLASS SELECTOR is a special class that is used to define the behavior of an HTML element.  These are                                                                       used to add special effects to some selectors.  

                          : selector {property:value}
													
A PSEUDO ELEMENT SELECTOR is a way to assign style to content that does not exist in the source document.  
                                                                    This is a specific, unique part of an element that can be used to generate content
																																		"on the fly", like automatic numbering and lists.  
													
													: special selector {property:value} 
													

**Here are 31 examples of Selectors---you can skip these if you just want to look at a pretty chart**

1.  **TYPE SELECTORS**-  select elements by their type.  Type means a type of HTML tag like < div >, < p >, < ul >. 
If you want to change the property of one of these elements/tags you use the CSS syntax and change it for every one of those elements.  

Let’s say you wanted to change every paragraph to the color green.  

*HTML*     < div class= "main">
                           < p > This is a paragraph of writing in HTML folder < /p >
							   </div>


*CSS *        p {color: green} 


So everywhere you have a paragraph in your linked HTML pages the paragraph would be the color green. 


2. **CHOOSING from MULTIPLE TYPE SELECTORS**--you will have any type selectors in your html if you have a nice web page.  

Let’s say you wanted to change only the second paragraph to the color blue.  

*HTML*     < div class= "main">
                           < p1 > 1st paragraph < /p1 >
													 < p2 > 2nd paragraph< /p2 >
													 
							   </div>

*CSS *        p2 {color: blue} 

This would make any paragraph you labeled p2 in your linked HTML pages the color blue.  

3.  **ID SELECTORS**--An ID attribute is used to specify a style for a single, UNIQUE element. No two ID attributes can have the same value.    A CSS ID selector must contain a "#" symbol followed by the ID value, which must be an identifier.   

Let’s say you wanted to change only the first paragraph to the color yellow.  

*HTML*     < div class= "main">

                           < p id ="fancy" > fancy paragraph < /p >  
													 < p > second paragraph < /p >  
													 < p >third paragraph < /p >
													 
							   </div>

*CSS *        #fancy {color: yellow} 

This would make the first paragraph with the id fancy in your linked HTML pages the color yellow.  

4. **Descendant Selectors**--selects all elements that are inside of the specified element.  

Let’s say you wanted to select only the image inside the paragraph to have a border.  

*HTML*     < div class= "main">
                           < h1 > header < /h> 
                           < p > paragraph with an image <img src="an image" alt="inside"> inside of it. < /p >
													 < p > paragraph < /p>  
													 <img src="An image not inside a paragraph" alt="image outside paragraph">
									
							       </div>

*CSS *        p img {border:1px}

This would make a border around the image only inside of the paragraph not the image that is outside the paragraph.

5. **Combine the Descendant & ID Selector**-- You can combine the #id selector with the descendant selector to choose something within the id.  

Let’s say you wanted to select only the image inside the paragraph with the id "fancy"  to have a border.  

*HTML*     < div class= "main">
                           < h1 > A header <img src="an image" alt="inside"> with an image inside of it. < /h> 
                           < p id="fancy" A fancy paragraph with an image <img src="an image" alt="inside"> inside it. < /p >
													 < p > This is another paragraph < /p>  
												   <img src="image " alt="image">
							       </div>

*CSS *        #fancy img {border:1px}

This would make a border around the image only inside of the paragraph with the id of "fancy" not the image that is outside the paragraph or the image inside the header. 

6.  **Class Selector**--You can select all elements by their class attribute.  Elements can have many classes but only one id.  

Let’s say you wanted to select only the images of the "unicorn" class to have a border.  

*HTML*     < div class= "main">
                           <img src="image" alt= image"> 
                           <img class="unicorn" src="image" alt="image">
                           < p > A paragraph <img class="unicorn" src="an image" alt="an image"> with an image inside. < /p >
													 < p > paragraph < /p>  
								
							       </div>

*CSS *      .unicorn {border:1px}

This would make a border around the images of the class "unicorn" not the image without the label of that class. 

7.   **Combine Class Selector with Type Selector**--You can select all elements that have a class and id selector.  

Let’s say you wanted to select only class=tiny that are also type a for link.  You want the links that are in class tiny to be the color fuchsia.  

*HTML*     < div class= "main">
                           <img src="image" alt="image">
													 <img class="unicorn" src="image" alt="image">
													 < h1 > <a class="tiny" href="tiny link">< /h1 >
													 < p > A paragraph with a link <a href="a link "> < /p > 
													 < p > A paragraph with tiny link <a class="tiny" href="tiny link ">< /p> 
													 
													 
							       </div>

*CSS *        a.small {color: fuchsia}

This would make all the links <a that also have the class "tiny" be the color fuchsia.  The tiny link in the h1 tag and the tiny link in the last paragraph would both be fuchsia. 

8. **Combine Class and Descendant Selectors **  

Let’s say you wanted to select only class=tiny that are also type links and are inside a h1 header.  So you want the links that are in class tiny to be the color gray.  

*HTML*     < div class= "main">
                           < h1> <a href="a link "> /h1>
													 <a href="link ">
													 *< h1> <a class="tiny" href="tiny link "> /h1 >*
													 < h1> <img class="tiny" src="tiny image" alt="tiny image"> /h1 >
													 *< h1> <a class="tiny" href="tiny link "> /h1 >*
													 
													 
							       </div>

*CSS *     h1 a.small {color: gray}

This would make all small class links that are within a h1 tag the color gray.  The third link and the last link would be gray.  The other links and images wouldn't be affected.  


8.  **Combine Selectors with Commas**--You can select as many elements as you want with commas.   

Let’s say you wanted to select the paragraphs and headers with everything inside them only.  When you select the paragraph and header you are selecting everything inside it.  You do this by selecting paragraph then use a comma and header.  

*HTML*     < div class= "main">
                           < pre class="tiny">tiny preformatted text < /pre >
                           <pre> preformatted text < /pre>
													 < p > A paragraph with preformatted text <pre> preformatted text < /pre> inside it.  < /p > 
											     < h1 > A header with preformatted text <pre> preformatted text < /pre > inside it. < /h1 >
													 < p > A paragraph with preformatted text <pre> preformatted text < /pre> inside it.  < /p > 
													 <pre> preformatted text < /pre>
													 < pre class="tiny"> tiny preformatted text < /pre >
													
							       </div>

*CSS *       p, h1 {color: blue}

This would make all your paragraphs and headers and everything inside them blue but would not affect the preformatted text outside the paragraphs or headers.  


9.  **Universal Selector**--You can just select everything which will select every single element.     

Let’s say you want it all to be black.   

*HTML*     < div class= "main">
                           <img src="image" alt="image">
													 < p > paragraph with a link <a href="a link "> < /p >
													 < h1> header < /h1 >
													 < h1 > header with a link <a href="a link">< /h1 inside. >
													 < p id ="fancy" > fancy paragraph < /p >
													 
							       </div>

*CSS *       * {color: black}

This would make everything black.  

10.  **Combine Universal & Type Selector**--You can just select everything that is one type.
  
Let’s say you wanted all paragraphs and everything in them to be red.   

*HTML*     < div class= "main">
                           < p id ="fancy" > This is a fancy paragraph <a href="a link">with a link in it. < /p >
													 < p > Just a paragraph with preformatted text <pre> preformatted text < /pre> inside it.   < /p >
													 <img class="tiny" src="a tiny image" alt="tiny image">
													 < p > Just a paragraph with an image <a href="a link "> < /p >
												
							       </div>

*CSS *       p * {color: red}

This would make everything inside the paragraph tags red.  

11.  **Adjacent Sibling Selectors**--You can select an element that directly follows another element using the + sign.   
Let’s say you wanted all the images that directly followed a paragraph to have a border.    

*HTML*     < div class= "main">
                          < h1 > A header <img class="tiny" src="tiny image" alt="tiny image"> inside of it. < /h> 
													< p > A paragraph < /p>
													*<img class="tiny" src="a tiny image" alt="tiny image">*
													< p > A paragraph < /p>
												*	<img src="image" alt="image">*
													<img class="tiny" src="a tiny image" alt="tiny image">
													<img class="tiny" src="a tiny image" alt="tiny image">

							       </div>

*CSS *       p + img {border:1px}

This would make every image that follows directly behind a paragraph have a border whether they are assigned to a class or not.  

12.  **General Sibling Selector**--You can select all siblings of an element that follow directly behind an element using a ~ tilde symbol.  

You choose the preformatted text that follows directly behind the header and make it white.  

*HTML*     < div class= "main">
                                <pre> preformatted text < /pre>
																< h1 > header with a link <a href="a link"> inside< /h1 >
																< pre class="tiny"> this is tiny preformatted text < /pre >
																<pre> preformatted text < /pre>
																< p > A paragraph with <pre> preformatted text < /pre> inside it.  < /p >
																< p > A paragraph with < pre class="tiny"> tiny preformatted text < /pre > inside it.  < /p > 
                                

							       </div>

*CSS *       h1 ~ pre {color:  white}

This would make the two preformatted text groups white that follow directly behind the h1 header.  

13. **Child Selectors**--You can select direct children of an element using a > symbol.    

You can select a child element that is nested directly in another element.  Anything nested deeper than that are called descendant elements instead of child elements.  

*HTML*     < div class= "main">
                                < p >
																      < h1 > A header <img src="an image" alt="inside"> with an image inside of it. < /h>
																< /p >
																< p > paragraph with <img src="an image" alt="inside"> image inside. < /p >
																< p > paragraph < /p >
																<img src="an image" alt="inside">
																<img class="tiny" src="a tiny image" alt="tiny image">

							       </div>

*CSS *       p > img {border:1px}

This would make a border around the image directly inside the paragraph.  Notice that the image inside the header that is nested inside the first paragraph is not selected because it is not a child but a descendant of the element p.  

14. **Pseudo-selector First Child**--You can select a first child element inside of another element.  This is an element that is directly nested in another element.  We use the :first-child symbol for this.  

You can select the first child image that is inside the paragraph.  

*HTML*     < div class= "main">
                                < h1 > header < /h1 >
																< p > paragraph < /p >
																< p > <img src="image 1" alt="inside">
																           <img src="image 2" alt="inside">
																					 <img src="image 3" alt="inside">
																< /p >
																< pre class="tiny" > tiny preformatted text < /pre >

							       </div>

*CSS *       img:first-child  {border:1px}

This would make a border around the first image which is the first child.  

15. **Pseudo-selector Only Child**--You can select an element that are the only element inside of another one.  We use the :only-child  symbol for this one.  

You can select the selectors with just one child.  

*HTML*     < div class= "main">
                               < p > paragraph with <img src="an image" alt="image"> image inside. < /p >
															 < p > A paragraph with <pre> preformatted text < /pre> inside it.  < /p >
                               < h1 > header with <pre> preformatted text < /pre> inside it.  < /h1 >
                               < p > <img src="small image" alt="small image">
																          <img src="image 2" alt="image">
																< /p >
                                < pre class="tiny" > tiny preformatted text < /pre >

							       </div>

*CSS *      p img, p pre:only-child  {border:1px}

This would make a border around the only child image inside a paragraph and the only child preformatted text inside a paragraph.  The reason why the images in the paragraph are not selected is because there are two children instead of an only child.  The reason why the last tiny preformatted text was not selected was because they were not inside anything else so they are not a child.  The header was not selected but if you wanted to select the header you would put h1 pre:only-child.  

16.  **Pseudo Selector Last Child**--You can select the last element inside of another element.  Select the last child element inside of another one.  We use the :last-child symbol here.  

It is important to remember that where there is only one element it will be considered a first-child, only-child, and last-child.    

*HTML*     < div class= "main">
                               < p id="fancy" A fancy paragraph with an image <img src="image" alt="image"> inside. < /p >
															 < p > paragraph < /p> 
															 < p > <a class="tiny" href="a tiny link">	
															            <a href="a link">
															 < /p >
															 < pre class="tiny" > tiny preformatted text < /pre >
														
							       </div>

*CSS *      img, pre:last-child  {border:1px}

This will select the last child of images and preformatted text. This would put a border around the image inside the fancy paragraph and the tiny preformatted text that is not nested inside anything else.  The reason this is selected is because it is the one element and is considered a first, only, and last child.   If you wanted to include links you would write img, pre, a:last-child.  

17.  **Pseudo Selector Nth Child**--You can select an element by its order inside another element.  

If you typed :nth-child(3) it will select every third child that is inside another element.    If we want to access the third child which is the third paragraph and make the text aqua, we need to use the :nth selector. 

*HTML*     < div class= "main">
                              < p > paragraph < /p> 
															< p > paragraph < /p> 
															< p > paragraph < /p> 
															< p id="fancy" A fancy paragraph < /p >

							       </div>

*CSS *      :nth-child(3)  {color: aqua}

This will change the third paragraph or third child to aqua.  If you wanted the fourth fancy paragraph you would type :nth-child(4).  

18.  **Last Child Nth Selector**--You can select an element by its order in another element, counting from the back forward.  

If you typed :nth-last-child(2) it will select every 2nd child that is inside another element counting backwards from the end.   If you want to make the second header in the list below cream colored you could use the :nth-last-child selector.

*HTML*     < div class= "main">
                              < p > paragraph < /p> 
														  *< h1 > header < /h1 > *
															< p >
															      <a href="1 link">
																		<a href="2 link">
																		<a href="3 link">
															< /p> 
													    < h1 > header < /h1 > 

							       </div>

*CSS *      h1:nth-child(3)  {color: cream}

This will change the header that is third from the back to a cream color.  If you did not include the h1 tag before the :nth-last-child you would end up with the header and the third from the back  1 link inside the paragraph.  

19.  **First of a type Selector**--You can select the first element of a type within another element using :first-of-type.  

If want to select the first image in an element and give it a border you could use this selector.  

*HTML*     < div class= "main">
                              <a class="tiny" href="tiny link">
															<img src="image" alt="image">
															<img class="tiny" src="tiny image" alt="image">
															<img src="image" alt="image">
															<img class="tiny" src="tiny image" alt="image">
															< p >
															      <a class="tiny" href="tiny link">
																		<a href="link">
															< /p> 
													    
							       </div>

*CSS *      img:first-of-type {border:1px}

This will select the first image that it comes too no matter what class it is a part of.  If you wanted to select the first link you would type a:first-of-type.  

20.  **Nth of a Type Selector**--You can select a specific element based on its type and order in another element.  You can select all the evens or odds of that element.  You can select all the 2nd instances of that element.  

If you want to select all the even paragraphs and make them orange you can use the :nth-of-type( ). 

*HTML*     < div class= "main">
                              < p > paragraph < /p>
															< p > paragraph < /p>
															< p > paragraph < /p>
															< p > paragraph < /p>
															< p class="fancy" > fancy paragraph < /p>
															< p > paragraph < /p>

							       </div>

*CSS *     :nth-of-type(even) {color:orange}

This will select the 2nd, 4th, & 6th paragraphs to be orange.    

21.  **Nth-of-type Selector with Formula**--You can select every nth element starting the count at a specific instance of that element.  

If you want to select the third and the fifth paragraph purple you would use the :nth-of-type(nth + #).  

*HTML*     < div class= "main">
                              < p > paragraph < /p>
															< p > paragraph with < pre class="tiny" > tiny preformatted text < /pre > inside < /p>
															< p > paragraph with <img class="tiny" src="tiny image" alt="image"> inside < /p>
															< p > paragraph < /p>
															< p > paragraph with <img src="image" alt="image"> inside < /p>
															< p > paragraph < /p>

							       </div>

*CSS *    p:nth-of-type(2n+3) {color:purple}

This will select every 2nd instance starting from and including the 3rd instance.  It will select the third paragraph and skip the fourth and select the fifth and skip the sixth...if there were a seventh paragraph is would have selected that one too.  

22. **Only Of Type Selector**--You can select elements that are the only ones of their type within another element.  

If you want to select the image that is the only image inside a paragraph.  The paragraph with two images will not be selected if you use the :only-of-type selector. 

*HTML*     < div class= "main">
                             < p class="fancy" > fancy paragraph 
														           <img class="tiny" src="tiny image" alt="image">
																			 <img src="image" alt="image">
														 < /p>
                             < p > paragraph with <img class="tiny" src="tiny image" alt="image"> inside < /p>
														 < p > paragraph with < pre > preformatted text < /pre > inside < /p>
                              
							       </div>

*CSS *    img:only-of-type {border:1px}

This will select the only image inside of the paragraph.  The paragraph with two images will not be selected because it is not the only image in the paragraph.  

23. **Last Of Type Selector**--You can select the last element of a specific type.  

If you want to select the last image and the last link in this group you can use the :last-of-type selector.  

*HTML*     < div class= "main">
                             <a class="tiny" href="tiny link">
														 <a class="tiny" href="tiny link">
														 < pre > preformatted text < /pre >
														 < pre > preformatted text < /pre >
														 <img class="tiny" src="tiny image" alt="image">
														 <img class="tiny" src="tiny image" alt="image">
                            
							       </div>

*CSS *   a:last-of-type, img:last-of-type {color:blue}

This will select the last of the links and images.  If you wanted to select the last of all types you could just type :last-of-type.  

24.  **Empty Selector**--You can select the elements that are empty.  

If you want to select the empty headers you can use the :empty selector.  

*HTML*     < div class= "main">
                             < h1> header < /h1 >
														 < h1> header < pre > preformatted text < /pre > < /h1 >
														 < p > paragraph < /p > 
														 < h1> header < /h1 >

							       </div>

*CSS *   h1:empty {color:green}

This will select the empty headers and make them green.  

25.  **Pseudo-class Negation**--You can select all the elements that do not match the negation selector.    

If you want to select the images that are not tiny you can use the :not selector.  

*HTML*     < div class= "main">
                            < p class="fancy" > fancy paragraph <img class="tiny" src="tiny image" alt="image"> < /p>
														< p > paragraph with <img src="image" alt="image"> inside. < /p > 
														< img src="image" alt="image" >
														< p > paragraph with <a class="tiny" href="tiny link"> inside. < /p > 
														< pre class=tiny> tiny preformatted text < /pre >
																			
							       </div>

*CSS *   img:not(.tiny) {border:1px}

This will select the images that are not tiny.  

26.   **Attribute Selector**--You can select all elements that have a specific attribute.  Some attributes are blank.     

If you want to select all the attributes that are FOR so for="name" you can use them with [attribute] selector.  

*HTML*     < div class= "main">
                           < h1 > header with <img class="tiny" src="tiny image" alt="image"> inside < /h2 >
													 < img for="Eva" src="image" alt="image" >
													 < p for="Ali" > paragraph with < pre > preformatted text < /pre > inside < /p > 
													 < h1 for="Cha" > header with <a href="link">   inside < /h2 >
													 < pre > preformatted text < /pre >
													 
							       </div>

*CSS * [for] {border:1px}

This will select everything with a for="whatever" inside it.  The for is the attribute selected.  

27. **Attribute Selector A[attribute]**--You can combine the attribute selector with another selector by adding it to the end. 

If you want to select all the attributes that are FOR so for="name" that are inside paragraphs, you can sue the A[attribute] selector.  

*HTML*     < div class= "main">
                           < p for="Solo" > paragraph with < pre > preformatted text < /pre > inside < /p >
													 < p for="Luke" > paragraph with <img src="image" alt="image"> inside < /p > 
													 < p > paragraph < /p > 
													 < h1 for="Leia" > header with <a href="link">   inside < /h2 >

							       </div>

*CSS *   p[for] {color:yellow}

This will select any paragraph with a for="whatever" inside it.   It will not choose the empty paragraph or the header with a for="whatever" inside it.  It will only select paragraphs with for inside.  

28. **Attribute Value Selector**--You can select all elements that have a specific attribute value.  These are case sensitive and must match exactly.  

If you want to select the element with BB8 in it you would use the [attribute="value"] to find it exactly.  

*HTML*     < div class= "main">
                          <img for="R2D2" src="image" alt="image">
													< h1 for="C3PO" > header with <img src="image" alt="image"> inside < /h1 > 
													< h1 for="BB8" > header with <a href="link">   inside < /h2 >
													< pre > preformatted text < /pre >
													
							       </div>

*CSS * [for="BB8"] {color:white}

This will select the header that has a link inside it because it has the attribute of for and the value of BB8.  If we did not match it exactly it would not select it.  

29. **Attribute Starts With Selector**--You can select all elements with an attribute value that starts with a specific set of characters.  

If you want to select the attribute value that starts with "Star" you should use the [attribute^="value"].  

*HTML*     < div class= "main">
                          < p for=Star Wars> paragraph < pre > preformatted text < /pre > < /p >
													< h1 for="Star Trek" > header with <img class="tiny" src="tiny image" alt="image"> inside < /h1 > 
													< h1 for="Firefly" > header with <a href="link">   inside < /h2 >
                
							       </div>

*CSS * [for^="Star"] {color:orange}

This will select the paragraph with the Star Wars attribute value and the header with the Star Trek attribute value since both start with the attribute value of Star.  

30.   **Attribute Ends With Selector**--You can select all elements with an attribute value that ends with a specific set of characters.  

If you want to select the attribute value that ends with "" you should use the [attribute$="value"].  

*HTML*     < div class= "main">
                          <img class="tiny" src="tiny image" alt="image">
													< h1 for="Unicorn" > header < pre > preformatted text < /pre > < /h1 >
													< img for="Kitten" src="image" alt="image" >
													< p for="Horn" > paragraph with <a href="link"> inside. < /p >
													< pre class=tiny> tiny preformatted text < /pre >
													
							       </div>

*CSS * [for$="orn"] {color:red}

This will select the header with Unicorn attribute value and the paragraph with the Horn attribute value since both end with the attribute value of orn.  

31.  **Attribute Wildcard Selector**--You can select all elements with an attribute value that contains a specific set of characters anywhere in the html.  This can be used if you can identify a common pattern in classes, tags, and other attributes.  

If you want to select the attribute value that contains the letter "h"  you should use the [attribute*="value"].  

*HTML*     < div class= "main">
                         < h1 for="Shark"> header with <img src="image" alt="image"> inside. < /h1 >
												 < h1 for="Turtle" > header with < pre > preformatted text < /pre > inside < /h1 >
												 < h1 for="Whale" > header with <a href="link"> inside < /h1 >

							       </div>

*CSS * [for*="h"] {color:navy}

This will select the header with Shark attribute value and the header with the Whale attribute value since both have the letter h inside their attribute value.  Turtle does not have an h so it would not be selected.  


**How about a bit more clarity because that was a lot of selecting?**

**Name of Selector         What it Selects                                                            Notation         Example**

Type                                all elements of a type                                                         A { }                   p{ }   all paragraphs 

ID                                      the element with a specific ID                                        #id{ }                 #star{ }  id="star"

Descendant                    selects all descendants inside an element                 A B{ }                 p img{ }  img in a p

Descendant + ID           selects all elements inside of element with id          #id A{ }             #star p{ } id="star" in a p

Class                               selects all elements with that class attribute           .class{ }             .cat{ }  all class="cat" 

Class + Type                 selects elements with the class and id both            #id.class{ }       #star.cat{ }  class="cat" & id="star"

Comma Combo           selects any combination with commas                      selector, selector, selector, selector{ }

Universal                        selects everything                                                              A *                       p *{ } everything inside a p
      
Adjacent Sibling          selects element that directly follows another         A + B                   p + img{ } img directly after p

General Sibling             selects all siblings of an element that follow           A ~ B                   p ~ img{ } all img after p

Child                                 selects element nested directly in parent                A > B                   p > img{ } img direct nest in p

1st Child Pseudo        selects the first child directly nested in parent       :first-child          img p:first-child{ } 1st img in p

Only Child Pseudo      selects the elements that are only child in it           :only-child          img p:only-child{ } p with 1 img

Last Child Pseudo      selects the last element inside another                    :last-child            img p:last-child{ } last img in p

Nth Child Pseudo        selects elements by order inside another               :nth-child(#)        :nth-child(3){ } chooses the 3rd 

Nth Last Child Po        selects elements by order backwards                      :nth-last-child(#) :nth-last-child(2){ } 2nd to last

First of Type                  selects the first of a type                                                :first-of-type       p:first-of-type{ } 1st paragraph

Nth of Type                   selects element by type by order                               :nth-of-type(#)    p:nth-of-type(3){ } 3rd paragraph

Nth of Type with          selects every nth element starting at a                   :nth-of-type(An+B)     p:nth-of-type(6n+2){ }
Formula                          specific instance of the type                                        selects every 6th p starting from 2nd instance

Only of Type                  selects elements that are only ones of a type       :only-of-type       p img:only-of-type{ } 
                                                                                                                                              any p with only one img inside 

Last of Type                  selects each last element of a type                            :last-of-type        p img:last-of-type{ }
                                                                                                                                               any last img with a p 

Empty                              selects all empty elements                                            :empty                   div:empty  all empty div tags

Negation Pseudo        selects all elements don't match negation              :not(X)                    :not(.small) all not class small 

Attribute                         selects an attribute that is inside a tag                      [attribute]             < tag attribute="value" >

                                                                                                                                              for="music"  [for] selects attributes of for
																																																																							
																																																																							p[for] will select any p with a for attribute

Attribute Value             selects elements with a specific attribute value    [attribute="value"]   < p for="movies" > 
                                                                                                                                              selects any p with for="value" inside
																																																																							
Attribute Start w/        chooses all attribute values that start with this      [attribute^="value"]  [for^="m"]
                                                                                                                                               chooses all values that start with letter m
																																																																							 for="music"  for="movies" for="maps"
																																																																							 
Attribute Ends w/        chooses all attribute values that end with this        [attribute$="value"]  [for$="s"]
                                                                                                                                               chooses all values that end with letter s
																																																																							 for="movies" for="maps" for="kittens"
																																																																							 
Attribute WildCard     chooses all attribute values that have this inside   [attribute*="value"]  [for*="t"]
                                                                                                                                               chooses all values that have a letter t inside
																																																																							 for="temperatures" for="mint" for="kittens"
																																																																							 

You can also practice these in a fun game at http:flukeout.github.io


**Now that you understand Selectors you need to understand SPECIFICITY**

Just like in math class certain things are done in certain orders.  Some styling in CSS will take a higher ranking then others causing some styling to work over others.  You may have assigned a paragraph's text to be blue but in another place green.  Specificity determines which one will trump the other.  

1.  We break selectors into these main categories:  Inline Styles, ID's, Classes, Attributes, and Elements. 

2.  If two selectors are applied to the same element the one with the higher specificity will win.  

3.  If two EQUAL selectors are applied to the same element the last one applied will win.

4.  ID selectors have a higher specificity than attribute selectors.  

5.  When things are styled directly in the HTML they will have a higher specificity then the CSS selectors.  Inline Styles           are the highest ranked Specificity.  

6.  The universal selector always has a Specificity of zero....  score is 0,0,0,0.  

7.  Specificity can be scored, and this is a Specificity Calculator:  https://specificity.keegan.st/


**There is a Specificity Hierarchy:**

**01 INLINE STYLES** (Worth 1000 points each)
      (attached directly to the element in your html document)
**02 ID's or the # of ID Selectors** (Worth 100 points each)
      (an identifier from your page elements ex. #p for paragraph)
**03 CLASSES, ATTRIBUTES, PSEUDO-CLASSES** (Worth 10 points each)
      (includes .classes, [attributes] and pseudo classes like :hover, :focus, etc)
**04 ELEMENTS & PSEUDO-ELEMENTS** (Worth 1 point each)
      (includes the number of element type selectors like :before or :after) 
			
          ****Examples****


           a universal                                                                     * { }                                     = 0000  
					 
           1 element                                                                      li { }                                     = 0001
					 
           2 elements                                                               ul li { }                                     = 0002
					 
					 1 element + 1 pseudo element           li:first-line { }                                     = 0002
					 
					 3 elements                                                         ul ol+li { }                                     = 0003
					 
					 1 attribute + 1 element                   h1 + *[rel=up] { }                                      =0011
					 
           1 class + 3 elements                                ul ol li.red { }                                     = 0013
					 
           2 elements + 2 class                          ul li.red.level { }                                      = 0022
					 
					 1 inline styling                                                   style=""                                        =1000
					 
					 1 id selector                                                           #sith                                         = 0100
					 
					 2 html selectors + 1 class                       div p.sith { }                                      = 0012
					 
					 1 html + 1 id + 1 class + 1 html    body #darkside.sith p { }                      = 0112
					 

**Important things to remember about Specificity**

1.  Use ID to make a rule more specific.  

         ex.  You can replace the a.highlight with ul#blogroll a.hightllight.    
				          class + element  = 0011 to element + id + class + element = 0112 
									
2.  Minimize your number of Selectors.  You should use the least number of selectors to style an element. 
      You should try and use the ones worth more points over many lower point selectors.  
			

**Selectors are complicated, and Specificity is really important when you are using CSS**

Just do what I did and google it.  There are some funny videos and some serious ones.  There are a ton of resources on this topic because there is a lot of depth here.  I hope this blog post helped you understand this subject a little bit better.  
Please contact me via email if you think I need to update or change any of the information provided here.  

Send to Charla:  ceansky@gmail.com  and have a specifically great day.  

			


				   



																																																																																							 
																																																																																							 
																																																																																							





 
  






