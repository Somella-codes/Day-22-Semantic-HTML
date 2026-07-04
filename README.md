# Day-22-Semantic-HTML 🧠

Today I learned why `<div>` soup is bad and why meaning matters more than looks.

## **1. Why Should You Care About Semantic HTML?**

Semantic HTML uses tags that describe *what the content is*, not just how it should look.

### Why it matters:
1.  **Accessibility**: Screen readers use semantic tags to navigate
2.  **SEO**: Google understands your content structure better
3.  **Maintainability**: Other devs can read your code faster
4.  **Built-in behavior**: Some tags have keyboard + browser features by default

#### **Bad Example: Non-Semantic**
```html
<div class="header">
  <div class="logo">MySite</div>
</div>
<div class="navigation">
  <div>Home</div>
  <div>About</div>
</div>
```

#### **Good Example: Semantic**
```html
<header>
  <h1>MySite</h1>
</header>
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
  </ul>
</nav>
```
A screen reader knows exactly what `<header>` and `<nav>` are. It has no idea what `<div class="header">` means.

---

## **2. Why is it Important to Have Good Structural Hierarchy?**

Hierarchy is how you organize headings and sections. Think book chapters.

### **The Rules**
1.  Only 1 `<h1>` per page
2.  Don't skip heading levels: `h1 > h2 > h3`
3.  Use headings for structure, not for making text big. Use CSS for styling.

#### **Bad Example: Broken Hierarchy**
```html
<h1>Main Title</h1>
<h4>Subsection</h4>  <!-- Skipped h2 and h3 -->
<p>Content here</p>
```

#### **Good Example: Proper Hierarchy**
```html
<main>
  <h1>Importance of Semantic HTML</h1>
  
  <section>
    <h2>Why Should You Care</h2>
    <p>Accessibility, SEO, and maintainability.</p>
  </section>

  <section>
    <h2>Structural Hierarchy</h2>
    <h3>Heading Rules</h3>
    <p>Only one h1, don't skip levels.</p>
  </section>
</main>
```
Screen reader users navigate by jumping between `h2` and `h3`. Good hierarchy = good navigation.

---

## **3. What Is the Difference Between Presentational and Semantic HTML?**

Presentational = "make it look this way"  
Semantic = "this content means this"

| Presentational | Semantic | Why Semantic is Better |
| --- | --- | --- |
| `<b>Bold</b>` | `<strong>Important</strong>` | Screen readers stress "strong" text |
| `<i>Italic</i>` | `<em>Emphasis</em>` | "em" means emphasis, not just italics |
| `<div class="header">` | `<header>` | Built-in meaning for browser + SEO |
| `<div class="footer">` | `<footer>` | Same reason |

#### **Code Example**
```html
<!-- Presentational Only -->
<p><b>Warning:</b> <i>Do not click this</i></p>

<!-- Semantic + Accessible -->
<p><strong>Warning:</strong> <em>Do not click this</em></p>
```
Both look the same, but the second one tells assistive tech that "Warning" is important and "Do not click this" has emphasis.

---

## **Other Important Semantic Tags**

```html
<article>   <!-- Self-contained content like a blog post -->
<section>   <!-- Thematic grouping of content -->
<aside>     <!-- Side content, related but not main -->
<figure>    <!-- Image + caption group -->
  <img src="chart.png" alt="Sales chart">
  <figcaption>Q1 Sales increased 20%</figcaption>
</figure>
<time datetime="2026-04-26">April 26, 2026</time>
<address>   <!-- Contact information -->
```

---

## **My Takeaway Today**
I used to think HTML was just to "make things appear on screen". 
Today I learned code talks to 3 people: 
1.  **The Browser** - to render it
2.  **Google** - to understand it for SEO
3.  **Other Developers** - to maintain it later

Writing `<header>` instead of `<div class="header">` takes the same effort but gives 10x more value. 
From today, no more div-soup for me 😤
