---
title: html-tips
date: 2021-06-24 09:17:25
tag: 
  - html
categories:
  - html
cover: /2021/06/24/html-tips/html-tips.png
thumbnail: /2021/06/24/html-tips/html-tips.png
---

## HTML Tips

In this article, I will share with you some very useful **HTML tips**. Enjoy! Post will be updated regularly with new tips!

## But first, what is HTML?

Hypertext Markup Language (HTML) is the standard markup language for documents designed to be displayed in a web browser. It can be assisted by technologies such as Cascading Style Sheets (CSS) and scripting languages such as JavaScript.

### Let’s start!

<!--more-->

### 1. The `loading=lazy` attribute

Performance tip. You can use the `loading=lazy` attribute to defer the loading of the image until the user scrolls to them.

```html
<img src='image.jpg' loading='lazy' alt='Alternative Text'>           
```

### 2. Email, call, and SMS links:

```html

<a href="mailto:{email}?subject={subject}&body={content}">
  Send us an email
</a>

<a href="tel:{phone}">
  Call us
</a>

<a href="sms:{phone}?body={content}">
  Send us a message
</a>           
```

### 3. Ordered lists `start` attribute.

Use the `start` attribute to change the starting point for your ordered lists.

![ordered lists start attribute](/images/html-tips/html-tag-start.png)



### 4. The `meter` element

You can use the `<meter>` element to display quantities. No JavaScript/CSS needed.

![meter element](/images/html-tips/html-tag-meter.png)

### 5. HTML Native Search

![](/images/html-tips/html-native-search.png)

### 6. Fieldset Element

You can use the `<fieldset>` element to group several controls as well as labels (`<label>`) within a web form.

![](/images/html-tips/html-fieldset-element.png)

### 7. Window.opener

Pages opened with `target="_blank"` allow the new page to access the original’s `window.opener`. This can have security and performance implications. Include `rel="noopener"` or `rel="noreferrer"` to prevent this.

```html

<a href="https://markodenic.com/" target="_blank" rel="noopener">
	Marko's website
</a>           
```

### 8. Base Element

If you want to open all links in the document in a new tab, you can use `<base>` element:

![](/images/html-tags/html-base-element.png)

### 9. Favicon cache busting

To refresh your website’s favicon you can force browsers to download a new version by adding `?v=2` to the filename.

This is especially helpful in production to make sure the users get the new version.

```html

<link rel="icon" href="/favicon.ico?v=2" />           
```

### 10. The `spellcheck` attribute

Use the `spellcheck` attribute to define whether the element may be checked for spelling errors.

![](/images/html-tips/tag-spellcheck.png)



from:<https://markodenic.com/html-tips/>

