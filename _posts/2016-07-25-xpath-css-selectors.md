---
layout: post
title: Xpath & CSS Selectors
---

In this blogpost I will try to show how you can target and select different html elements using XPath or CSS selectors. This skill is really handy if you want to extract information from any given webpage to use in your data science projects.

My recommendation is to copy and paste the *Example HTML* below and open it up in your favorite browser. Open the developer tools and use the console to try out the statements below.

Let’s start.

First we need to know how we can ”target” specific html sections and then from there we need to learn how to combine CSS or XPath statements to start extracting what we want.

Using the console in the web browser you can try out the XPath and CSS selector statements below.

In the console prepend the statements with:

XPath: 
```
$X(”…statement…”)
```

Css-selector:
```
$$(”…statement…”) 
```

*Example HTML*

```html

<!DOCTYPE html>

<html>
<Head>
</Head>
<body>
	<h1>First Heading</h1 >
	<div class="first_class">
	  <p id="firstname">My name is Trevor.</p>
	  <p> paragraph with no id </p>
	  <p> another paragraph with no id </p>
	</div>
	<h1>Second Heading</h1>
	<div class="list">
		<ul id="List_of_friends">
			<li>Goofy</li>
			<li>Mickey</li>
			<li>Daisy</li>
			<li>Pluto</li>
		</ul> 
	</div>	
	<div>
		<p> this is inside a div with no class or id <p/>
		<p> this is also inside the a div with no class or id <p/>	
	<div/>
	
</body>
</html>
```

### General targeting

#### Direct child

All <p> elements where the parent is a <div> element.

XPath: 
    ```html
    //div/p
    ```

Css:
    ```html
    div > p
    ```

#### Child or subchild

All <p> elements that are inside a <div> element.

XPath:
    ```html
    //div//p
    ```

Css:
    ```html
    div p
    ```


#### Id

All <p> elements with an id attribute value equal to ”firstname”

XPath:
    ```html
    //p[@id=’firstname’]
    ```

Css:
    ```
    #firstname
    ```
#### Class

All elements with class=”first_class”

XPath:
    ```html
    //div[@class=’first_class’]
    ```

Css:
    ```html
    .first_class
    ```

### Start walking the elements

By combining xpath and/or Css selectors we can start walking the html elements and really focusing in on the parts that we are after.

#### Class

Grab the second <p> within the target class ”first_class”

XPath:
    ```html
    //div[@class=”first_class”]/p[1]
    —> 'paragraph with no id'
    ```

Css:
```html
.first_class > p:nth-child(2)
—> 'paragraph with no id'
```

So first we target the class and from there we grab the 2nd <p> tag (note that XPath are zero based and css selectors are not).

#### Id

Let’s get the 2nd element from the list with id of ”List_of_friends”

XPath:
    ```html
    //ul[@=’List_of_friends’]/li[2]
    —> 'Mickey'
    ```

Css:
    ```html
    #List_of_friends li:nth-of-type(2)
    —> ’Mickey’
    ```


*to be cont…*
















