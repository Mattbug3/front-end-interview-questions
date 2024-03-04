# Interview Questions

###### 1. What is HTML?

<details><summary><b>Answer</b></summary>
HTML, which stands for Hypertext Markup Language, is the standard markup language used to create and design web pages. It provides the structure and layout for content on the internet by using various elements and tags to define different parts of a webpage, such as headings, paragraphs, images, links, and more. HTML works in conjunction with other technologies like CSS (Cascading Style Sheets) and JavaScript to create visually appealing and interactive web experiences
</details>

---

###### 2. What is the purpose of the DOCTYPE in HTML?

<details><summary><b>Answer</b></summary>

The `<!DOCTYPE>` declaration is placed at the very beginning of an HTML document, before the `<html>` tag, and it is not an HTML tag itself. It helps the browser to determine how to parse and render the content of the document. Different versions of HTML have different `<!DOCTYPE>` declarations, and using the correct one ensures that the document is interpreted and displayed correctly by the browser.

Example:

```html

<!-- HTML5 -->
<!DOCTYPE html>

<!-- HTML 4.01 Strict -->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">


<!-- HTML 4.01 Transitional -->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">


<!-- HTML 4.01 Frameset -->
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">


<!-- XHTML 1.0 Strict -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">


<!-- XHTML 1.0 Transitional -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<!-- XHTML 1.0 Frameset -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
```

</details>

---

###### 3. Explain the difference between HTML and XHTML.

<details><summary><b>Answer</b></summary>
HTML and XHTML are both markup languages for structuring web content:

- HTML is more forgiving in syntax and widely supported by browsers.
- XHTML follows stricter rules similar to XML, ensuring well-formed documents.
- HTML is flexible and widely used, while XHTML is more precise and suitable for XML-based environments.
</details>

---

###### 4. What are the new features in HTML5 compared to HTML4?

<details><summary><b>Answer</b></summary>

#### 1. Semantic Elements: 
HTML5 introduced semantic elements like `<header>`, `<footer>`, `<nav>`, `<article>`, <section>, and <aside>, which provide clearer structure and meaning to web content.

#### 2. Audio and Video Support: 
HTML5 introduced native support for embedding audio and video content using the `<audio>` and `<video>` elements, eliminating the need for third-party plugins like Flash.

#### 3. Canvas: 
HTML5 introduced the `<canvas>` element, which allows for dynamic, scriptable rendering of 2D shapes and bitmap images, enabling rich visualizations and interactive graphics without the need for plugins.

#### 4. Form Input Types and Attributes: 
HTML5 introduced new input types such as `<input type="date">`, `<input type="email">`, `<input type="url">`, and attributes like required and pattern, making form validation easier and more powerful.

#### 5. Local Storage: 
HTML5 introduced the `localStorage` and `sessionStorage` APIs, allowing web applications to store data locally on the user's device, providing a way to persist data between sessions and improving performance.

#### 6. Geolocation: 
HTML5 introduced the `Geolocation API`, which enables web applications to access the user's geographic location, allowing for location-aware features and services.

#### 7. Web Workers: 
HTML5 introduced the `Web Workers API`, enabling web applications to run scripts in background threads, improving performance and responsiveness by offloading tasks from the main execution thread.
</details>

---

###### 5. What is the purpose of the `<meta>` tag?

<details><summary><b>Answer</b></summary>

The purpose of the `<meta>` tag is to provide metadata about the HTML document. Metadata includes information like character encoding, viewport settings, authorship, keywords, and description.

Example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="This is a brief description of the web page.">
    <meta name="keywords" content="HTML, CSS, JavaScript, web development">
    <meta name="author" content="John Doe">
    <title>Sample Page</title>
</head>
<body>
    <!-- Content of the web page goes here -->
</body>
</html>
```
</details>

---

###### 6. Explain the difference between `<div>` and `<span>`.

<details><summary><b>Answer</b></summary>

- `<div>` is a block-level element, meaning it takes up the entire width available and starts on a new line. It's typically used to group and style larger sections of content, like sections or containers.

- `<span>` is an inline element, meaning it only takes up the space necessary for its content and does not start on a new line. It's often used to apply styles to smaller parts of text within a block-level element, like applying different colors or formatting to specific words or phrases.

In summary, `<div>` is used for larger sections or containers, while `<span>` is used for smaller, inline elements within those sections.
</details>

---

###### 7. How do you create a hyperlink in HTML?

<details><summary><b>Answer</b></summary>

We use `<a></a>`(anchor) tag to create a hyperlink html.

Example:

```html
<a href = 'https://example.com' target='_blank'></a>
```
</details>

---

###### 8. How do you embed an image in HTML?

<details><summary><b>Answer</b></summary>

To embed an image in HTML, we use the `<img>` tag, which is a self-closing tag. The `src` attribute specifies the URL of the image, which can be a local path or a web URL. The `alt` attribute provides alternative text for the image, which is displayed if the image fails to load or for accessibility purposes.

Example:

```html
<img src = './example.jpeg' alt="example image"/>
```
</details>

---

###### 9. What is the purpose of the `<header>` element?

<details><summary><b>Answer</b></summary>

The `<header>` element in HTML is used to define introductory or navigational content for its nearest ancestor `<article>`, `<aside>`, `<nav>`, or `<section>` element. It typically contains headings, logos, navigation menus, search bars, and other introductory content for a webpage or a section of a webpage.
</details>

---

###### 10. Explain the purpose of the `<footer>` element in HTML.

<details><summary><b>Answer</b></summary>

The `<footer>` element in HTML is used to define the footer of a document or a section. It typically contains information about the author, copyright information, links to related documents, or contact information. It appears at the bottom of the page or section and provides closure or additional context to the content above it.
</details>

---

###### 11. What is the role of `nav` element in HTML?

<details><summary><b>Answer</b></summary>

The `<nav>` element in HTML represents a navigation menu, typically containing links to other pages or sections within the website.
</details>

---

###### 12. How do you create an ordered list in HTML?

<details><summary><b>Answer</b></summary>

Using `<ol></ol>`(ordered list) tag with `<li></li>`(list item) for each item
</details>

---

###### 13. How can you add comments in HTML?

<details><summary><b>Answer</b></summary>
Using <!-- Comment text here --> to add comments in HTML.
</details>

---

###### 14. What is the purpose of the HTML `<article>` tag?

<details><summary><b>Answer</b></summary>

The `<article>` tag in HTML is used to define independent, self-contained content within a document. It's typically used for content that can stand alone and be syndicated, such as blog posts, news articles, forum posts, or comments.
</details>

---

###### 15. How do you create a line break in HTML?

<details><summary><b>Answer</b></summary>
We can use `<br>` tag to create a line break in HTML.
</details>

---

###### 16. What is the purpose of the HTML `<section>` tag?

<details><summary><b>Answer</b></summary>

The `<section>` tag in HTML is used to group related content together within a document. It helps to organize the content into distinct sections, making it easier to understand the structure of the webpage and improving accessibility.
</details>

---

###### 17. Explain the concept of HTML entities.

<details><summary><b>Answer</b></summary>
HTML entities are special characters represented by code, such as &lt; for `<` and &nbsp; for a non-breaking space.
</details>

---

###### 18. How do you create a table in HTML?

<details><summary><b>Answer</b></summary>
We can create a table using the `<table>` tag with `<tr> for table rows, `<td>` for table cells, and `<th>` for header cells.
</details>

---

###### 19. What is the purpose of HTML `<aside>` element?

<details><summary><b>Answer</b></summary>

The `<aside>` element in HTML is used for content that is related but not central to the main content of a webpage, such as sidebars, pull quotes, or related links.
</details>

---

###### 20. How do you create an external link that opens in a new tab?

<details><summary><b>Answer</b></summary>
We can use the `<a></a>`(anchor) tag with attribute `target = '_blank'` to create an external link that opens in a new tab.
</details>

---
