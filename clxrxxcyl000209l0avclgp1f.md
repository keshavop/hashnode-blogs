---
title: "Github Markdown CheatSheet"
seoTitle: "Github Markdown CheatSheet"
seoDescription: "Master GitHub Markdown with our ultimate cheat sheet! Learn essential formatting, advanced features, and best practices to enhance your GitHub projects. Per"
datePublished: Sun Jun 23 2024 19:27:13 GMT+0000 (Coordinated Universal Time)
cuid: clxrxxcyl000209l0avclgp1f
slug: github-markdown-cheatsheet
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1719170783241/89bcf378-bfc3-4b2e-8a45-c38c9c9ab013.webp
tags: github, markdown, git, cheatsheet

---

# [**Introduction**](https://www.rhrits.online/blog/github-markdown#introduction)

The following markdown cheatsheet is adapted from: [**https://guides.github.com/features/mastering-markdown/**](https://guides.github.com/features/mastering-markdown/)

# [**What is Markdown?**](https://www.rhrits.online/blog/github-markdown#what-is-markdown)

Markdown is a way to style text on the web. You control the display of the document; formatting words as bold or italic, adding images, and creating lists are just a few of the things we can do with Markdown. Mostly, Markdown is just regular text with a few non-alphabetic characters thrown in, like `#` or `*`.

# [**Syntax guide**](https://www.rhrits.online/blog/github-markdown#syntax-guide)

Here’s an overview of Markdown syntax that you can use anywhere on GitHub.com or in your own text files.

## [**Headers**](https://www.rhrits.online/blog/github-markdown#headers)

```sql
# This is a h1 tag ## This is a h2 tag #### This is a h4 tag
```

# [**This is a h1 tag**](https://www.rhrits.online/blog/github-markdown#this-is-a-h1-tag)

## [**This is a h2 tag**](https://www.rhrits.online/blog/github-markdown#this-is-a-h2-tag)

#### [**This is a h4 tag**](https://www.rhrits.online/blog/github-markdown#this-is-a-h4-tag)

## [**Emphasis**](https://www.rhrits.online/blog/github-markdown#emphasis)

```sql
_This text will be italic_ **This text will be bold** _You **can** combine them_
```

*This text will be italic*

**This text will be bold**

*You* ***can*** *combine them*

## [**Lists**](https://www.rhrits.online/blog/github-markdown#lists)

### [**Unordered**](https://www.rhrits.online/blog/github-markdown#unordered)

```sql
- Item 1- Item 2  - Item 2a  - Item 2b
```

* Item 1
    
* Item 2
    
    * Item 2a
        
    * Item 2b
        

### [**Ordered**](https://www.rhrits.online/blog/github-markdown#ordered)

```sql
1. Item 11. Item 21. Item 3   1. Item 3a   1. Item 3b
```

1. Item 1
    
2. Item 2
    
3. Item 3
    
    1. Item 3a
        
    2. Item 3b
        

## [**Images**](https://www.rhrits.online/blog/github-markdown#images)

```sql
![GitHub Logo](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)Format: ![Alt Text](url)
```

![GitHub Logo](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png align="left")

## [**Links**](https://www.rhrits.online/blog/github-markdown#links)

```sql
http://github.com - automatic![GitHub](http://github.com)
```

[**http://github.com**](http://github.com/) - automatic! [**GitHub**](http://github.com/)

## [**Blockquotes**](https://www.rhrits.online/blog/github-markdown#blockquotes)

```sql
As Kanye West said: > We're living the future so> the present is our past.
```

As Kanye West said:

> ***We're living the future so the present is our past.***

## [**Inline code**](https://www.rhrits.online/blog/github-markdown#inline-code)

```sql
I think you should use an`<addr>` element here instead.
```

I think you should use an `<addr>` element here instead.

## [**Syntax highlighting**](https://www.rhrits.online/blog/github-markdown#syntax-highlighting)

Here’s an example of how you can use syntax highlighting with [**GitHub Flavored Markdown**](https://help.github.com/articles/basic-writing-and-formatting-syntax/):

````sql
```js:fancyAlert.jsfunction fancyAlert(arg) {  if (arg) {    $.facebox({ div: '#foo' })  }}```
````

And here's how it looks - nicely colored with styled code titles!

```sql
function fancyAlert(arg) {  if (arg) {    $.facebox({ div: "#foo" });  }}
```

## [**Footnotes**](https://www.rhrits.online/blog/github-markdown#footnotes)

```sql
Here is a simple footnote[^1]. With some additional text after it. [^1]: My reference.
```

Here is a simple footnote[**<sup>1</sup>**](https://www.rhrits.online/blog/github-markdown#user-content-fn-1). With some additional text after it.

## [**Task Lists**](https://www.rhrits.online/blog/github-markdown#task-lists)

```sql
- [x] list syntax required (any unordered or ordered list supported)- [x] this is a complete item- [ ] this is an incomplete item
```

* list syntax required (any unordered or ordered list supported)
    
* this is a complete item
    
* this is an incomplete item
    

## [**Tables**](https://www.rhrits.online/blog/github-markdown#tables)

You can create tables by assembling a list of words and dividing them with hyphens `-` (for the first row), and then separating each column with a pipe `|`:

```sql
| First Header                | Second Header                || --------------------------- | ---------------------------- || Content from cell 1         | Content from cell 2          || Content in the first column | Content in the second column |
```

| **First Header** | **Second Header** |
| --- | --- |
| Content from cell 1 | Content from cell 2 |
| Content in the first column | Content in the second column |