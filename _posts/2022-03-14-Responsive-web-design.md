---
layout: post
title: Responsive web design
published: true
---
Fundamental of responsive web design...

# Basic HTML and HTML5

In this Responsive Web Design Certification, you'll learn the languages that developers use to build webpages: HTML (Hypertext Markup Language) for content, and CSS (Cascading Style Sheets) for design.

First, you'll build a cat photo app to learn the basics of HTML and CSS. Later, you'll learn modern techniques like CSS variables by building a penguin, and best practices for accessibility by building a web form.

Finally, you'll learn how to make webpages that respond to different screen sizes by building a Twitter card with Flexbox, and a complex blog layout with CSS Grid. 

----

### **Create a Text Field**

Now let's create a web form.

`input` elements are a convenient way to get input from your user.

You can create a text input like this:

```html
<input type="text">
```

Note that `input` elements are self-closing.

### **Add Placeholder Text to a Text Field**

Placeholder text is what is displayed in your `input` element before your user has inputted anything.

You can create placeholder text like so:

```html
<input type="text" placeholder="this is placeholder text">
```

**Note:** Remember that `input` elements are self-closing.



### **Create a Form Element**

You can build web forms that actually submit data to a server using nothing more than pure HTML. You can do this by specifying an `action` attribute on your `form` element.

For example:

```html
<form action="/url-where-you-want-to-submit-form-data">
  <input>
</form>
```



### **Add a Submit Button to a Form*

Let's add a `submit` button to your form. Clicking this button will send the data from your form to the URL you specified with your form's `action` attribute.

Here's an example submit button:

```html
<button type="submit">this button submits the form</button>
```

------

Add a button as the last element of your `form` element with a type of `submit`, and `Submit` as its text.



### **Use HTML5 to Require a Field**

You can require specific form fields so that your user will not be able to submit your form until he or she has filled them out.

For example, if you wanted to make a text input field required, you can just add the attribute `required` within your `input` element, like this: `<input type="text" required>`



### **Create a Set of Radio Buttons**

You can use radio buttons for questions where you want the user to only give you one answer out of multiple options.

Radio buttons are a type of `input`.

Each of your radio buttons can be nested within its own `label` element. By wrapping an `input` element inside of a `label` element it will automatically associate the radio button input with the label element surrounding it.

All related radio buttons should have the same `name` attribute to create a radio button group. By creating a radio group, selecting any single radio button will automatically deselect the other buttons within the same group ensuring only one answer is provided by the user.

Here's an example of a radio button:

```html
<label> 
  <input type="radio" name="indoor-outdoor">Indoor 
</label>
```

It is considered best practice to set a `for` attribute on the `label` element, with a value that matches the value of the `id` attribute of the `input` element. This allows assistive technologies to create a linked relationship between the label and the related `input` element. For example:

```html
<input id="indoor" type="radio" name="indoor-outdoor">
<label for="indoor">Indoor</label>
```

We can also nest the `input` element within the `label` tags:

```html
<label for="indoor"> 
  <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
</label>
```



### **Create a Set of Checkboxes**

Forms commonly use checkboxes for questions that may have more than one answer.

Checkboxes are a type of `input`.

Each of your checkboxes can be nested within its own `label` element. By wrapping an `input` element inside of a `label` element it will automatically associate the checkbox input with the label element surrounding it.

All related checkbox inputs should have the same `name` attribute.

It is considered best practice to explicitly define the relationship between a checkbox `input` and its corresponding `label` by setting the `for` attribute on the `label` element to match the `id` attribute of the associated `input` element.

Here's an example of a checkbox:

```html
<label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
```



### **Use the value attribute with Radio Buttons and Checkboxes**Passed

When a form gets submitted, the data is sent to the server and includes entries for the options selected. Inputs of type `radio` and `checkbox` report their values from the `value` attribute.

For example:

```html
<label for="indoor">
  <input id="indoor" value="indoor" type="radio" name="indoor-outdoor">Indoor
</label>
<label for="outdoor">
  <input id="outdoor" value="outdoor" type="radio" name="indoor-outdoor">Outdoor
</label>
```

Here, you have two `radio` inputs. When the user submits the form with the `indoor` option selected, the form data will include the line: `indoor-outdoor=indoor`. This is from the `name` and `value` attributes of the "indoor" input.

If you omit the `value` attribute, the submitted form data uses the default value, which is `on`. In this scenario, if the user clicked the "indoor" option and submitted the form, the resulting form data would be `indoor-outdoor=on`, which is not useful. So the `value` attribute needs to be set to something to identify the option.



### Check Radio Buttons and Checkboxes by Default**

You can set a checkbox or radio button to be checked by default using the `checked` attribute.

To do this, just add the word `checked` to the inside of an input element. For example:

```html
<input type="radio" name="test-name" checked>
```



### **Nest Many Elements within a Single div Element**

The `div` element, also known as a division element, is a general purpose container for other elements.

The `div` element is probably the most commonly used HTML element of all.

Just like any other non-self-closing element, you can open a `div` element with `<div>` and close it on another line with `</div>`.

### **Declare the Doctype of an HTML Document**

The challenges so far have covered specific HTML elements and their uses. However, there are a few elements that give overall structure to your page, and should be included in every HTML document.

At the top of your document, you need to tell the browser which version of HTML your page is using. HTML is an evolving language, and is updated regularly. Most major browsers support the latest specification, which is HTML5. However, older web pages may use previous versions of the language.

You tell the browser this information by adding the `<!DOCTYPE ...>` tag on the first line, where the `...` part is the version of HTML. For HTML5, you use `<!DOCTYPE html>`.

The `!` and uppercase `DOCTYPE` is important, especially for older browsers. The `html` is not case sensitive.

Next, the rest of your HTML code needs to be wrapped in `html` tags. The opening `<html>` goes directly below the `<!DOCTYPE html>` line, and the closing `</html>` goes at the end of the page.

Here's an example of the page structure. Your HTML code would go in the space between the two `html` tags.

```html
<!DOCTYPE html>
<html>

</html>
```



### **Define the Head and Body of an HTML Document**

You can add another level of organization in your HTML document within the `html` tags with the `head` and `body` elements. Any markup with information about your page would go into the `head` tag. Then any markup with the content of the page (what displays for a user) would go into the `body` tag.

Metadata elements, such as `link`, `meta`, `title`, and `style`, typically go inside the `head` element.

Here's an example of a page's layout:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta />
  </head>
  <body>
    <div>
    </div>
  </body>
</html>
```





# Basic css

CSS, or Cascading Style Sheets, tell the browser how to display the text and other content that you write in HTML. With CSS, you can control the color, font, size, spacing, and many other aspects of HTML elements.

Now that you've described the structure of your cat photo app, give it some style with CSS.

---











# Applied Visual design

Visual design is a combination of typography, color theory, graphics, animation, page layout, and more to help deliver your unique message.

In this course, you'll learn how to apply these different elements of visual design to your webpages.

----



### **Create Visual Balance Using the text-align Property**

This section of the curriculum focuses on Applied Visual Design. The first group of challenges build on the given card layout to show a number of core principles.

Text is often a large part of web content. CSS has several options for how to align it with the `text-align` property.

`text-align: justify;` causes all lines of text except the last line to meet the left and right edges of the line box.

`text-align: center;` centers the text

`text-align: right;` right-aligns the text

And `text-align: left;` (the default) left-aligns the text.





### **Adjust the Width of an Element Using the width Property**Passed

You can specify the width of an element using the `width` property in CSS. Values can be given in relative length units (such as `em`), absolute length units (such as `px`), or as a percentage of its containing parent element. Here's an example that changes the width of an image to 220px:

```css
img {
  width: 220px;
}
```



### **Adjust the Height of an Element Using the height Property**Passed

You can specify the height of an element using the `height` property in CSS, similar to the `width` property. Here's an example that changes the height of an image to 20px:

```css
img {
  height: 20px;
}
```



### **Use the strong Tag to Make Text Bold**

To make text bold, you can use the `strong` tag. This is often used to draw attention to text and symbolize that it is important. With the `strong` tag, the browser applies the CSS of `font-weight: bold;` to the element.



### **Use the u Tag to Underline Text**

To underline text, you can use the `u` tag. This is often used to signify that a section of text is important, or something to remember. With the `u` tag, the browser applies the CSS of `text-decoration: underline;` to the element.



### **Use the em Tag to Italicize Text**Passed

To emphasize text, you can use the `em` tag. This displays text as italicized, as the browser applies the CSS of `font-style: italic;` to the element.



### **Use the s Tag to Strikethrough Text**

To strikethrough text, which is when a horizontal line cuts across the characters, you can use the `s` tag. It shows that a section of text is no longer valid. With the `s` tag, the browser applies the CSS of `text-decoration: line-through;` to the element.



### **Create a Horizontal Line Using the hr Element**

You can use the `hr` tag to add a horizontal line across the width of its containing element. This can be used to define a change in topic or to visually separate groups of content.



### **Adjust the background-color Property of Text**

Instead of adjusting your overall background or the color of the text to make the foreground easily readable, you can add a `background-color` to the element holding the text you want to emphasize. This challenge uses `rgba()` instead of `hex` codes or normal `rgb()`.

> rgba stands for:
> r = red
> g = green
> b = blue
> a = alpha/level of opacity

The RGB values can range from 0 to 255. The alpha value can range from 1, which is fully opaque or a solid color, to 0, which is fully transparent or clear. `rgba()` is great to use in this case, as it allows you to adjust the opacity. This means you don't have to completely block out the background.

You'll use `background-color: rgba(45, 45, 45, 0.1)` for this challenge. It produces a dark gray color that is nearly transparent given the low opacity value of 0.1.



### **Adjust the Size of a Header Versus a Paragraph Tag**

The font size of header tags (`h1` through `h6`) should generally be larger than the font size of paragraph tags. This makes it easier for the user to visually understand the layout and level of importance of everything on the page. You use the `font-size` property to adjust the size of the text in an element.



### **Add a box-shadow to a Card-like Element**

The `box-shadow` property applies one or more shadows to an element.

The `box-shadow` property takes values for

- `offset-x` (how far to push the shadow horizontally from the element),
- `offset-y` (how far to push the shadow vertically from the element),
- `blur-radius`,
- `spread-radius` and
- `color`, in that order.

The `blur-radius` and `spread-radius` values are optional.

Multiple box-shadows can be created by using commas to separate properties of each `box-shadow` element.

Here's an example of the CSS to create multiple shadows with some blur, at mostly-transparent black colors:

```css
box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
```



### **Decrease the Opacity of an Element**Passed

The `opacity` property in CSS is used to adjust the opacity, or conversely, the transparency for an item.

> A value of 1 is opaque, which isn't transparent at all.
> A value of 0.5 is half see-through.
> A value of 0 is completely transparent.

The value given will apply to the entire element, whether that's an image with some transparency, or the foreground and background colors for a block of text.



### **Use the text-transform Property to Make Text Uppercase**Passed

The `text-transform` property in CSS is used to change the appearance of text. It's a convenient way to make sure text on a webpage appears consistently, without having to change the text content of the actual HTML elements.

The following table shows how the different `text-transform`values change the example text "Transform me".

|    Value     |                         Result                         |
| :----------: | :----------------------------------------------------: |
| `lowercase`  |                     "transform me"                     |
| `uppercase`  |                     "TRANSFORM ME"                     |
| `capitalize` |                     "Transform Me"                     |
|  `initial`   |                 Use the default value                  |
|  `inherit`   | Use the `text-transform` value from the parent element |
|    `none`    |           **Default:** Use the original text           |



### **Set the font-size for Multiple Heading Elements**

The `font-size` property is used to specify how large the text is in a given element. This rule can be used for multiple elements to create visual consistency of text on a page. In this challenge, you'll set the values for all `h1` through `h6` tags to balance the heading sizes.



### **Set the font-weight for Multiple Heading Elements**Passed

You set the `font-size` of each heading tag in the last challenge, here you'll adjust the `font-weight`.

The `font-weight` property sets how thick or thin characters are in a section of text.



### **Set the font-size of Paragraph Text**

The `font-size` property in CSS is not limited to headings, it can be applied to any element containing text.



### **Set the line-height of Paragraphs**

CSS offers the `line-height` property to change the height of each line in a block of text. As the name suggests, it changes the amount of vertical space that each line of text gets.



### **Adjust the Hover State of an Anchor Tag**

This challenge will touch on the usage of pseudo-classes. A pseudo-class is a keyword that can be added to selectors, in order to select a specific state of the element.

For example, the styling of an anchor tag can be changed for its hover state using the `:hover` pseudo-class selector. Here's the CSS to change the `color` of the anchor tag to red during its hover state:

```css
a:hover {
  color: red;
}
```



### **Change an Element's Relative Position**Passed

CSS treats each HTML element as its own box, which is usually referred to as the CSS Box Model. Block-level items automatically start on a new line (think headings, paragraphs, and divs) while inline items sit within surrounding content (like images or spans). The default layout of elements in this way is called the normal flow of a document, but CSS offers the position property to override it.

When the position of an element is set to `relative`, it allows you to specify how CSS should move it *relative* to its current position in the normal flow of the page. It pairs with the CSS offset properties of `left` or `right`, and `top` or `bottom`. These say how many pixels, percentages, or ems to move the item *away* from where it is normally positioned. The following example moves the paragraph 10 pixels away from the bottom:

```css
p {
  position: relative;
  bottom: 10px;
}
```

Changing an element's position to relative does not remove it from the normal flow - other elements around it still behave as if that item were in its default position.

**Note:** Positioning gives you a lot of flexibility and power over the visual layout of a page. It's good to remember that no matter the position of elements, the underlying HTML markup should be organized and make sense when read from top to bottom. This is how users with visual impairments (who rely on assistive devices like screen readers) access your content.



### **Move a Relatively Positioned Element with CSS Offsets**

The CSS offsets of `top` or `bottom`, and `left` or `right` tell the browser how far to offset an item relative to where it would sit in the normal flow of the document. You're offsetting an element away from a given spot, which moves the element away from the referenced side (effectively, the opposite direction). As you saw in the last challenge, using the `top` offset moved the `h2` downwards. Likewise, using a `left` offset moves an item to the right.

![img](https://cdn-media-1.freecodecamp.org/imgr/eWWi3gZ.gif)





# CSS Flexbox

[A complete guide to flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)



<iframe width="560" height="500" src="https://www.youtube.com/embed/fYq5PXgSsbE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



# CSS Grid

