# "Markdown recap", a panorama of Markdown's features


<div class="chapo-markdown">

**The formatting capabilities offered by the Markdown syntax are numerous. They deserved a detailed inventory.**

You can use this page as a cheatsheet or paste [the source of this page](https://framagit.org/roneo/roneo.frama.io/-/raw/master/content/page/markdown-recap-overview-test-hugo-showcase.md) wherever you want to test the support and styling of Markdown.
</div>


<div class="boxInfo"> <strong>You are new to Markdown?</strong>

Discover the key features in the [Markdown Guide](https://www.markdownguide.org/getting-started/) and practice the basics online with this [interactive tutorial](https://commonmark.org/help/tutorial/). See also [this second one](http://markdowntutorial.com/).
</div>



<div class="toc">

**Table of Contents**

- [Basic formatting](#basic-formatting)
- [Blockquotes](#blockquotes)
- [Lists](#lists)
- [Paragraphs & breaks](#paragraphs--breaks)
- [Links](#links)
- [Code formatting](#code-formatting)
- [Images](#images)
- [Task list / checkboxes](#task-list--checkboxes)
- [Tables](#tables)
- [Footnotes](#footnotes)
- [Definition List](#definition-list)
- [Headings](#headings)
- [Further reading](#further-reading)

</div>

## Basic formatting

### **Bold** text

You can use `**two asterisks**` →  **two asterisks**

or `__two underscores__` →  __two underscores__

### *Italic*

Use `*single asterisk*` → *single asterisk*

or `_single underscore_` → _single underscore_

### ***Bold and italic***

Three stars for `***bold and italic***` → ***bold and italic***

### ~~Strikethrough~~

Use `~~two tildes~~` →  ~~two tildes~~



## Blockquotes

**Syntax:**

    > blockquote

**Output**:

> blockquote

### Nested blockquotes

**Syntax:**

    > First level
    >
    >> Second level

**Output:**

> First level
>> Second level    

### Markdown in blockquotes

```
> **Markdown** can be used *inside quotes*
>
> 1.   This is the first list item.
> 1.   This is the second list item.
> 
> ~~strikethrough~~
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");
```

**Output:**

> **Markdown** can be used *inside quotes*
> 1. This is the first list item.
> 1. This is the second list item.
> 
> ~~strikethrough~~
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");


## Lists


### Unordered list

Cant be marked with `-`, `+` or `*`

```markdown
- First item
- Second item
- Third item
```

```markdown
+ First item
+ Second item
+ Third item
```

```markdown
* First item
* Second item
* Third item
```

**Output:**

- First item
- Second item
- Third item

+ First item
+ Second item
+ Third item

* First item
* Second item
* Third item

### Ordered lists

Incrementation is automatic, you can simply use `1.` everywhere

```
1. First item
1. Second item
1. Third item
```

**Output:**

1. First item
1. Second item
1. Third item



### Nested list

```
- First item
- Second item
- Third item
  1. Indented item
  1. Indented item
- Fourth item
```

**Output:**

- First item
- Second item
- Third item
  1. Indented item
  1. Indented item
- Fourth item


## Paragraphs & breaks

**If you hit enter just once** between two lines, both lines will be joined into a single paragraph.

But, if you **leave a blank line between them**, they will split into two paragraphs.

**Demonstration**:

```
This text is a paragraph.
This won't be another paragraph, it will join the line above it.

This will be another paragraph, as it has a blank line above it.
```

**Output**

This text is a paragraph. This won't be another paragraph, it will join the line above it.

This will be another paragraph, as it has a blank line above it.

### Line breaks

To force a line break, **end a line with two or more whitespaces**, and then type return.

```
This is the first line.··
Second line
```

**Output:**

This is the first line.  
Second line

### Horizontal lines

Can be inserted with four `*`, `-` or `_`

```
----

****

____
```

**Output:**

----

****

____




## Links


### Basic links

```
[Semantic description](https://roneo.org)
<address@example.com>  
<https://example.org> works too. Must be used for explicit links.
```

**Output:**

[Semantic description](https://roneo.org)  
<address@example.com>  
<https://example.org> works too. Must be used for explicit links.


### Links using text reference

```
[I'm a link][Reference text]

[This link] will do the same as well. It works as the identifier itself.


[reference text]: https://example.org
[this link]: https://roneo.org
```
**Output:**

[I'm a link][Reference text]

[This link] will do the same as well. It works as the identifier itself.


[reference text]: https://example.org
[this link]: https://roneo.org

**Note:** The reference text is *not* case sensitive


### Link with a title on hover

```
[Random text][random-identifier].  
Hover the mouse over it to see the title.

Several syntaxes are accepted:
[One](https://example.org "First site")
[Two](https://roneo.org 'Second site')
[Three](https://debian.org (Third site))

[random-identifier]: https://roneo.org "This example has a title"
```

**Output:**

[Random text][random-identifier]. Hover the mouse over it to see the title.

Several syntaxes are accepted:
[One](https://example.org "First site")
[Two](https://roneo.org 'Second site')
[Three](https://debian.org (Third site))

[random-identifier]: https://roneo.org "This example has a title"


### Links with Markdown style

To ***emphasize*** links, add asterisks before and after the brackets and parentheses.  

    I love supporting the **[EFF](https://eff.org)**.
    This is the *[Markdown Guide](https://www.markdownguide.org)*.

To denote links as `code`, add backticks *inside* the brackets:

    See the section on [`code`](#code).

**Output:**

I love supporting the **[EFF](https://eff.org)**.  
This is the *[Markdown Guide](https://www.markdownguide.org)*.  
See the section on [`code`](#code).


### Atribute a custom anchor to a heading

Anchors are automatically generated based on the heading's content. You can customize the anchor this way:

    ### Heading {#custom-id}

**Output:**

#### Heading {#custom-id}



## Code formatting {#code}


### Inline

Wrap with single backticks to highlight as`` `code` `` → `code`

### Codeblocks

Create a code block with three backticks `` ``` `` before and after your block of code.

**Output:**


```
sudo apt hello
cat /etc/apt/sources.list
```

Also possible with a tabulation or four empty spaces at the beginning of the lines:

**Tabulation**

	sudo apt hello
	echo "hi"

**Four whitespaces**

    sudo apt hello

Let's test the wrapping of a long line:

	apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test 

### Codeblocks with syntax highlighting

Set the language right after the first backticks (for example `` ```html  ``) to get syntax highlighting

#### Samples:


#### HTML

```html
<!DOCTYPE html>
<html lang="fr" itemscope itemtype="http://schema.org/WebPage">
  <head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
```

#### CSS

```css
/* Comment */
.blog-post h2, h3 {
  margin-top: 1.6em;
  margin-bottom: 0.8em;
}
```

#### Bash

```bash
# Comment

if [[ ! $system =~ Linux|MacOS|BSD ]]; then
	echo "This version of bashtop does not support $system platform."

sudo apt install test
```

#### Diff

```diff
- red
+ green
! test
# gray
```

### Escaping with backslashes

Any ASCII punctuation character may be escaped using a single backslash.

Example:

    \*this is not italic*

**Output:**

\*this is not italic*



## Images

### Basic syntax

```
![Semantic description of the image](/img/ok.png)
```

![Semantic description of the image](/img/ok.png)

<div class="boxInfo"><strong>The text inside the square brackets is important:</strong>

this generates the image attribute called `ALT`, which stands for _alternative text_.

Including **descriptive** alt text [helps maintain accessibility](https://webaim.org/techniques/alttext/) for every visitor and should always be included with an image. When you add alt text be sure to describe the content and function of the picture.  
In addition to the accessibility benefits, `ALT` is useful for SEO, and is displayed when, for some reason, that image is not loaded by the browser.
</div>


### Image with title and caption

```
![Semantic description](/img/ok.png "Your title")*Your caption*
```
![Semantic description](/img/ok.png "Your title")*Your caption*


### Clickable images

For clickable images, simply wrap the image markup into a [link markup](#links):

```
[![Semantic description](/img/ok.png "Your title")](http://roneo.org)
```

**Output:**

[![Semantic description](/img/ok.png "Your title")](http://roneo.org)



### Image with an identifier

You can call the image with an identifier as we do for [links](#links)

```
![Semantic desc.][image identifier]

Lorem ipsum dolor sit amet consectetur adipisicing elit [...]

[image identifier]: /img/ok.png "Title"
```

![Semantic desc.][image identifier]

[image identifier]: /img/ok.png "Title"


## Task list / checkboxes

```
- [X] Write the press release
- [ ] Update the website
```

- [x] Write the press release
- [ ] Update the website

## Tables


```
| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |
```

or

```
| Syntax | Description |
| - | --- |
| Header | Title |
| Paragraph | Text|
```

will render the same way:

| Syntax | Description |
| - | --- |
| Header | Title |
| Paragraph | Text|


### Text alignment in tables


```
| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |
```
See the way the text is aligned, depending on the position of `':'`

| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |


<div class="boxInfo"> <strong>Need a Table generator?</strong>

You can generate Markdown tables with ease using this [Table Generator](https://www.tablesgenerator.com/markdown_tables)
</div>



## Footnotes

```
Here's a sentence with a footnote[^1].
(see the result at the bottom of the page)

[^1]: This is the first footnote.
```

**Output:**

Here's a sentence with a footnote[^1].  
(see the result at the bottom of the page)

[^1]: This is the first footnote.

### Long footnote

```
Here's a longer one.[^bignote]
(see the result at the bottom of the page)

[^bignote]: Here's one with multiple paragraphs and code.
	
	Indent paragraphs to include them in the footnote.
	
	`{ my code }`
	
	Note that you can place the footnote anywhere you want in your article
```

**Output:**

Here's a longer one.[^bignote]
(see the result at the bottom of the page)

[^bignote]: Here's one with multiple paragraphs and code.
	
	Indent paragraphs to include them in the footnote.
	
	`{ my code }`
	
	Note that you can place the footnote anywhere you want in your article



## Definition List

```
term
: definition

second term
: meaning
```

**Output:**

term
: definition

second term
: meaning

## Headings

Add `##` at the beginning of a line to set as Heading.  
You can use up to 6 `#` symbols for the corresponding Heading levels


```
## Heading 1
[...]

###### Heading 6
```

<div class="boxInfo"><strong>You should not use single `#` headings inside your pages:</strong>

Headings begining with a single `#` give a top level heading (***h1***) in HTML. Such heading is already displayed on every page as its main title.

If you use a second `h1` on the same page, you’re creating confusion for users with a screen reader or for a search engine scrapping your page, which can hurt your precious SEO.

Moreover, `h1` headings in the body of a page will not show in some readers, like [Wallabag](https://wallabag.org).
    
**Conclusion**: always begin a heading with at least two `##`!
</div>

## Heading 2



<div class="toc">

**Table of Contents**

- [Basic formatting](#basic-formatting)
- [Blockquotes](#blockquotes)
- [Lists](#lists)
- [Paragraphs & breaks](#paragraphs--breaks)
- [Links](#links)
- [Code formatting](#code)
- [Images](#images)
- [Task list / checkboxes](#task-list--checkboxes)
- [Tables](#tables)
- [Footnotes](#footnotes)
- [Definition List](#definition-list)
- [Headings](#headings)
- [Further reading](#further-reading)

</div>

## Basic formatting

### **Bold** text

You can use `**two asterisks**` →  **two asterisks**

or `__two underscores__` →  __two underscores__

### *Italic*

Use `*single asterisk*` → *single asterisk*

or `_single underscore_` → _single underscore_

### ***Bold and italic***

Three stars for `***bold and italic***` → ***bold and italic***

### ~~Strikethrough~~

Use `~~two tildes~~` →  ~~two tildes~~



## Blockquotes

**Syntax:**

    > blockquote

**Output**:

> blockquote

### Nested blockquotes

**Syntax:**

    > First level
    >
    >> Second level

**Output:**

> First level
>> Second level    

### Markdown in blockquotes

```
> **Markdown** can be used *inside quotes*
>
> 1.   This is the first list item.
> 1.   This is the second list item.
> 
> ~~strikethrough~~
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");
```

**Output:**

> **Markdown** can be used *inside quotes*
> 1. This is the first list item.
> 1. This is the second list item.
> 
> ~~strikethrough~~
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");


## Lists


### Unordered list

Cant be marked with `-`, `+` or `*`

```markdown
- First item
- Second item
- Third item
```

```markdown
+ First item
+ Second item
+ Third item
```

```markdown
* First item
* Second item
* Third item
```

**Output:**

- First item
- Second item
- Third item

+ First item
+ Second item
+ Third item

* First item
* Second item
* Third item

### Ordered lists

Incrementation is automatic, you can simply use `1.` everywhere

```
1. First item
1. Second item
1. Third item
```

**Output:**

1. First item
1. Second item
1. Third item



### Nested list

```
- First item
- Second item
- Third item
  1. Indented item
  1. Indented item
- Fourth item
```

**Output:**

- First item
- Second item
- Third item
  1. Indented item
  1. Indented item
- Fourth item


## Paragraphs & breaks

**If you hit enter just once** between two lines, both lines will be joined into a single paragraph.

But, if you **leave a blank line between them**, they will split into two paragraphs.

**Demonstration**:

```
This text is a paragraph.
This won't be another paragraph, it will join the line above it.

This will be another paragraph, as it has a blank line above it.
```

**Output**

This text is a paragraph. This won't be another paragraph, it will join the line above it.

This will be another paragraph, as it has a blank line above it.

### Line breaks

To force a line break, **end a line with two or more whitespaces**, and then type return.

```
This is the first line.··
Second line
```

**Output:**

This is the first line.  
Second line

### Horizontal lines

Can be inserted with four `*`, `-` or `_`

```
----

****

____
```

**Output:**

----

****

____




## Links


### Basic links

```
[Semantic description](https://roneo.org)
<address@example.com>  
<https://example.org> works too. Must be used for explicit links.
```

**Output:**

[Semantic description](https://roneo.org)  
<address@example.com>  
<https://example.org> works too. Must be used for explicit links.


### Links using text reference

```
[I'm a link][Reference text]

[This link] will do the same as well. It works as the identifier itself.


[reference text]: https://example.org
[this link]: https://roneo.org
```
**Output:**

[I'm a link][Reference text]

[This link] will do the same as well. It works as the identifier itself.


[reference text]: https://example.org
[this link]: https://roneo.org

**Note:** The reference text is *not* case sensitive


### Link with a title on hover

```
[Random text][random-identifier].  
Hover the mouse over it to see the title.

Several syntaxes are accepted:
[One](https://example.org "First site")
[Two](https://roneo.org 'Second site')
[Three](https://debian.org (Third site))

[random-identifier]: https://roneo.org "This example has a title"
```

**Output:**

[Random text][random-identifier]. Hover the mouse over it to see the title.

Several syntaxes are accepted:
[One](https://example.org "First site")
[Two](https://roneo.org 'Second site')
[Three](https://debian.org (Third site))

[random-identifier]: https://roneo.org "This example has a title"


### Links with Markdown style

To ***emphasize*** links, add asterisks before and after the brackets and parentheses.  

    I love supporting the **[EFF](https://eff.org)**.
    This is the *[Markdown Guide](https://www.markdownguide.org)*.

To denote links as `code`, add backticks *inside* the brackets:

    See the section on [`code`](#code).

**Output:**

I love supporting the **[EFF](https://eff.org)**.  
This is the *[Markdown Guide](https://www.markdownguide.org)*.  
See the section on [`code`](#code).


### Atribute a custom anchor to a heading

Anchors are automatically generated based on the heading's content. You can customize the anchor this way:

    ### Heading {#custom-id}

**Output:**

#### Heading {#custom-id}



## Code formatting


### Inline

Wrap with single backticks to highlight as`` `code` `` → `code`

### Codeblocks

Create a code block with three backticks `` ``` `` before and after your block of code.

**Output:**


```
sudo apt hello
cat /etc/apt/sources.list
```

Also possible with a tabulation or four empty spaces at the beginning of the lines:

**Tabulation**

	sudo apt hello
	echo "hi"

**Four whitespaces**

    sudo apt hello

Let's test the wrapping of a long line:

	apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test 

### Codeblocks with syntax highlighting

Set the language right after the first backticks (for example `` ```html  ``) to get syntax highlighting

#### Samples:


#### HTML

```html
<!DOCTYPE html>
<html lang="fr" itemscope itemtype="http://schema.org/WebPage">
  <head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
```

#### CSS

```css
/* Comment */
.blog-post h2, h3 {
  margin-top: 1.6em;
  margin-bottom: 0.8em;
}
```

#### Bash

```bash
# Comment

if [[ ! $system =~ Linux|MacOS|BSD ]]; then
	echo "This version of bashtop does not support $system platform."

sudo apt install test
```

#### Diff

```diff
- red
+ green
! test
# gray
```

### Escaping with backslashes

Any ASCII punctuation character may be escaped using a single backslash.

Example:

    \*this is not italic*

**Output:**

\*this is not italic*



## Images

### Basic syntax

```
![Semantic description of the image](https://roneo.org/img/ok.png)
```

![Semantic description of the image](https://roneo.org/img/ok.png)

<div class="boxInfo"><strong>The text inside the square brackets is important:</strong>

this generates the image attribute called `ALT`, which stands for _alternative text_.

Including **descriptive** alt text [helps maintain accessibility](https://webaim.org/techniques/alttext/) for every visitor and should always be included with an image. When you add alt text be sure to describe the content and function of the picture.  
In addition to the accessibility benefits, `ALT` is useful for SEO, and is displayed when, for some reason, that image is not loaded by the browser.
</div>


### Image with title and caption

```
![Semantic description](https://roneo.org/img/ok.png "Your title")*Your caption*
```
![Semantic description](https://roneo.org/img/ok.png "Your title")*Your caption*


### Clickable images

For clickable images, simply wrap the image markup into a [link markup](#links):

```
[![Semantic description](https://roneo.org/img/ok.png "Your title")](http://roneo.org)
```

**Output:**

[![Semantic description](https://roneo.org/img/ok.png "Your title")](http://roneo.org)



### Image with an identifier

You can call the image with an identifier as we do for [links](#links)

```
![Semantic desc.][image identifier]

Lorem ipsum dolor sit amet consectetur adipisicing elit [...]

[image identifier]: https://roneo.org/img/ok.png "Title"
```

![Semantic desc.][image identifier]

[image identifier]: https://roneo.org/img/ok.png "Title"


## Task list / checkboxes

```
- [X] Write the press release
- [ ] Update the website
```

- [x] Write the press release
- [ ] Update the website

## Tables


```
| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |
```

or

```
| Syntax | Description |
| - | --- |
| Header | Title |
| Paragraph | Text|
```

will render the same way:

| Syntax | Description |
| - | --- |
| Header | Title |
| Paragraph | Text|


### Text alignment in tables


```
| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |
```
See the way the text is aligned, depending on the position of `':'`

| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |


<div class="boxInfo"> <strong>Need a Table generator?</strong>

You can generate Markdown tables with ease using this [Table Generator](https://www.tablesgenerator.com/markdown_tables)
</div>



## Footnotes

```
Here's a sentence with a footnote[^1].
(see the result at the bottom of the page)

[^1]: This is the first footnote.
```

**Output:**

Here's a sentence with a footnote[^1].  
(see the result at the bottom of the page)

[^1]: This is the first footnote.

### Long footnote

```
Here's a longer one.[^bignote]
(see the result at the bottom of the page)

[^bignote]: Here's one with multiple paragraphs and code.
	
	Indent paragraphs to include them in the footnote.
	
	`{ my code }`
	
	Note that you can place the footnote anywhere you want in your article
```

**Output:**

Here's a longer one.[^bignote]
(see the result at the bottom of the page)

[^bignote]: Here's one with multiple paragraphs and code.
	
	Indent paragraphs to include them in the footnote.
	
	`{ my code }`
	
	Note that you can place the footnote anywhere you want in your article



## Definition List

```
term
: definition

second term
: meaning
```

**Output:**

term
: definition

second term
: meaning

## Headings

Add `##` at the beginning of a line to set as Heading.  
You can use up to 6 `#` symbols for the corresponding Heading levels


```
## Heading 1
[...]

###### Heading 6
```

<div class="boxInfo"><strong>You should not use single `#` headings inside your pages:</strong>

Headings begining with a single `#` give a top level heading (***h1***) in HTML. Such heading is already displayed on every page as its main title.

If you use a second `h1` on the same page, you’re creating confusion for users with a screen reader or for a search engine scrapping your page, which can hurt your precious SEO.

Moreover, `h1` headings in the body of a page will not show in some readers, like [Wallabag](https://wallabag.org).
    
**Conclusion**: always begin a heading with at least two `##`!
</div>

## Heading 2

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.


### Heading 3 ##################################

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.

#### Heading 4

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.

##### Heading 5

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.

###### Heading 6

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.





## References

- Source : [roneo.org/markdown](https://roneo.org/markdown)
- [Basic Syntax | Markdown Guide](https://www.markdownguide.org/basic-syntax)
- [Extended Syntax | Markdown Guide](https://www.markdownguide.org/extended-syntax)
- [Daring Fireball: Markdown Syntax Documentation](https://daringfireball.net/projects/markdown/syntax)
- [Markdown Guide at Gitlab.com](https://about.gitlab.com/handbook/markdown-guide/)
- [CommonMark Spec](https://spec.commonmark.org/0.29/)

This website uses [Hugo](https://gohugo.io/), which implements [the Goldmark](https://github.com/yuin/goldmark) markdown parser. Goldmark adheres to the [CommonMark specification.](https://spec.commonmark.org/) ([Source](https://discourse.gohugo.io/t/markdown-mixed-with-html-stops-links-from-being-rendered/27993/6))

## Further reading

- [CommonMark Discussions](https://talk.commonmark.org/)
- [A clever way to style Images With Markdown](https://www.xaprb.com/blog/how-to-style-images-with-markdown/)

## Footnotes
