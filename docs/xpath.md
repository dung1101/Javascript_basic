# XPath
> XPath is a major element in the XSLT standard. XPath can be used to navigate through elements and attributes in an XML document.


#### Syntax
```
<body>
	<h3>Book</h3>
	<div id="main">
		<div class="book">
		  <h3 class="title">Harry Potter</h3>
		  <p class="price">29.99</p>
		  <a href="/books/harry_potter">Detail</a>
		</div>
		<div class="book">
		  <h3 class="title">Learning XML</h3>
		  <p class="price">39.95</p>
		  <a href="/books/learning_xml">Detail</a>
		</div>
	</div>
	<div class="order" >
			<input name="discount">
			<input type="submit">
	</div>
</body>
```

##### Descendant selectors

Expression | js selector |Description
-|-|-
//h3 | h3 | select `h3` tag 
//div//p | div p | select `p` tag in `div`
//div/p | div > p | select `p` tag is children of `div`
//div/* | div > * | select all in `div`
/ | :root | select root
/body | :root > body | select body is children of root


##### Attribute selectors

Expression | js selector |Description
-|-|-
//*[@id="main"]	| #id | select all element that id is "main"
//*[@class="book"] | .class | select all element that class is "book"
//input[@type="submit"] |  input[type="submit"] | select input that type is "submit"
//a[@id="abc"][@for="xyz"]|a#abc[for="xyz"] | select
//a[@rel]	 | a[rel] | select
//a[starts-with(@href, '/')] | a[href^='/'] | select
//a[ends-with(@href, '.pdf')]|a[href$='pdf']	| select
//a[contains(@href, '://')]	 | 	 a[href*='://']	| select
//a[contains(@rel, 'help')] | a[rel~='help']	| select
