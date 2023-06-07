# Agency Project

The goal of this project was to build an agency website for our team. The main requirements focussed on creating an accessible website that could be navigated with just a keyboard and which worked as expected with a screen reader by writing in semantic HTML.

## 1. Structure a site using semantic HTML to aid accessibility

Structuring a website using semantic HTML helps improve accessibility by providing meaningful structure and context to assistive technologies and users with visual impairments.
By using semantic HTML elements like `<header>`, `<nav>`, `<main>`, and `<footer>`, the website becomes more navigable, making it easier for screen readers and other assistive devices to understand and interpret the content.

```html <h2 class="sub-title center">How to get in touch</h2>
    <section id="contact" class="center">
      <h2 class="contact-title">Do you want to have a chat?</h2>
      <h3 class="contact-sub-title">Leave us your contact details below</h3>
      <!-- When click this button will open a new tab with a form -->
      <button id="contactButton" class="btn-contact center" role="button">
        Contact us
      </button>
    </section>
    <button class="btn-top">Top</button>
```

This code snippet shows the 'contact' section from the website.

   - The top-level `<section>` element helps to group related content together, providing a clear delineation of the section.
   - The headings `<h2>` and `<h3>` are used appropriately to convey the hierarchy and structure of the content.
   - The id attribute is used for unique identification of the contact section, which can be useful for navigation or scripting purposes.
   - The `role="button"` attribute is unnecessary for the <button> elements, as <button> elements are already considered interactive elements by default.

## 2. Ensure a web page is readable for screen readers
  
  ```html
    <button
        id="burger"
        class="burger-menu column"
        onclick="menuOnClick()"
        aria-label="burger"
      >
        <span class="burger-menu-line"></span>
        <span class="burger-menu-line"></span>
      </button>
  ```
This snippet shows the burger menu which is displayed on small screens.
  
  - The <button> element is used to create a button, indicating interactive content to assistive technologies.
  - The aria-label attribute provides an alternative label for the button, allowing screen readers to announce the purpose of the button.

## 3. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably
  
To ensure sufficient color contrast in our UI, we used colour contrast checking tools to verify that the foreground and background colours met the WCAG (Web Content Accessibility Guidelines) standards, making it easier for all users to perceive and read the content comfortably. Additionally, we avoided colour as the sole means of conveying information and used alternative methods such as labels or icons to further enhance accessibility for individuals with visual impairments.

## 4. Use various tools to check that our website meets accessibility criteria

 I used Lighthouse in Chrome Dev Tools to generate accessibility reports, one of which can be seen below. I also navigated the page using screen readers and keyboards to check that everything worked as expected.
  
  ![screenshot of a  lighthouse report](https://github.com/sgroi-l/FAC-Portfolio/assets/74066857/066cfd52-3f38-4204-9a94-3994e626584b)
## 5. Use CSS media queries to ensure our content is always presented effectively on screens of different sizes

## 6. Demonstrate a mobile-first approach to building a website


## 7. Use CSS variables to apply repeated colours to HTML elements

## 8. Use CSS Flexbox to style children in a single-direction layout (ie a row or a column)

## 9. Use CSS Grid to style children in two-direction layout

## 10. Ensure our Git commit history tells a coherent story

## 11. Use the appropriate input types in HTML forms for gathering different types of information
