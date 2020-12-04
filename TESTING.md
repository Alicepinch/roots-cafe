# Testing

Throughout the building process of the website I checked the Developer tools to ensure that the website is responsive on different devices. I also run my code through W3C CSS and HTML validators.

### Hero Image Cover text:

---

Whilst using developer tools I noticed that the cover text and divider were not responsive on the Hero image, to fix this I added in the below media queries for mobile view for the cover text ID.

```

@media screen and (max-width: 480px) {
  .divider-white {
    width: 200px;
    margin: 0 auto;
    border-top: 2px solid rgb(255, 255, 255);
  }

  #cover-text {
    height: 150px;
    width: 100%;
  }

  #cover-text h1 {
    padding-top: 15px;
  }
}

```

When checking ami-responsive the white divider was overlapping the cover text background so I added the below media query to reduce the size of the divider for ipad:

```

@media screen and (min-width: 768px) {
  .divider-white {
      width: 300px;
  }

```

### Hero Image
---
Due to the style of image that I used for the hero image, in phone view there was a lot of blank space. 

In order to fix this I added in a Mobile hero image section to my code, this is clearly outlined in my comments. I then hid the original Hero Image section for mobile view and did the same for the mobile view section for larger screen sizes. 

- [Before](/docs/testing/hero-image-before-fix.jpg)
- [After](/docs/testing/hero-image-mobile-view.png)

Code:

``` {
@media screen and (min-width: 768px) {
  #hero-image {
    display: none;
  }
}

  ```

  ``` {
@media screen and (max-width: 767px) {
  #hero-image-mobile {
      display: none;
  }

  ```

### About us section 
---
When in phone view I noticed that the layout didnt look great for the about us section. 
To fix this I duplicated the "id="sustainable-coffee-container" and added in a Mobile coffee section which would only show in mobile view. This is clearly commented out in the [index.html](index.html) file. 

In the CSS I set the original section "id="sustainable-coffee-container" for smaller screen sizes as "display: none;" 
So that in smaller screen sizes the new section "id="mobile-coffee-container"" would show. 

I then made sure that on larger screen sized the "mobile-coffee-container" would not show.

``` {
@media screen and (min-width: 768px) {
  #coffee-mobile-container {
    display: none;
  }
}

  ```

  ``` {
@media screen and (max-width: 767px) {
  #sustainable-coffee-container {
    display: none;
  }

  ```

### Navbar Hamburger Menu:

---

Due to removing the Bootstrap styling from the navbar the hamburger icon disappeared. To fix this I added in a fontawesome icon to the span class "navbar-toggler-icon". The navbar wasn't centered so I added in CSS styling 'padding-top: 5px;" which fixed this.
I have clearly mentioned in my [CSS stylesheet](https://www.example.com) where I have overwritten some of the bootstrap styling to achieve this.

### Lighthouse:

---

Throughout the building process I checked my website's performance using lighthouse in the developer tools. To improve SEO and best practices I looked at the google suggestions on how to improve these.

#### SEO

Lighthouse returned the error of "Tap targets not sized properly" I improved the seo to 100% by increasing the size and adding padding to the Icons for the Social media links in thre footer.
After doing this to all pages and rerunning lighthouse SEO was at 100% for SEO.

#### Best Practices

For Best practices lighthouse returned the error of 'Display images with correct aspect ration" for the roots-logo in the navbar. To fix this I decreased the size of the logo and updated this on all pages.

#### Accesability

In order to improve the Accesability across all pages lighthouse suggested to add "rel="noopener" or rel="norefer" to all of my 'a' elements.

#### Performance

In order to improve performance, lighthouse suggested to compress all images so I compressed all images using [Tinypng](https://tinypng.com/)

#### Reports 

- [Menu Page lighthouse results](/docs/testing/menu-lighthouse-report.png)
- [Contact Us page lighthouse results](/docs/testing/-lighthouse-report.png)
- [Homepage lighthouse results](/docs/testing/index-lighthouse-report.png)
- [Visit us page lighthouse results](/docs/testing/visit-us-lighthouse-report.png)

Performance is still lower than the others, I tried the recommendations from lighthouse on how to improve these by converting all my images to webp files, however this was not supported in safari so I reverted these back. 
I also tried to decrease the sizing of my images to the exact sizing of the components however they lost their quality. 

### File paths:

When deploying my website to github I noticed that some of my images were not displaying. With the help of my mentor we discovered the issue was the file paths used. The image's in the style.css sheet were corrected by adding '/roots-cafe/' and images hosted on the page were fixed by removing the '/'.

### Social Links:

When doing final link checks for my project I noticed that the social links were going through to 404. To fix this I checked the URL's and they were missing : from "http://."
These links are now fixed. 

#### WS3 Validator:

Throughout the building process of each section of the Roots cafe website I ran my code through the WS3 HTML & CSS validators.

When running the 'Contact us' page through it returned the below error for the text-area:
![Input Field Error](/docs/testing/ws3-code-validator-contact-us-issue.png)

This was fixed by removing "type="text-area"" from the element.

Contact us returned the below error for Headings:
![Heading Error](/docs/testing/ws3-contact-form-heading-issue.png)
In order to fix this, I moved the h1 from the form section into the parent section. 

The below error will still return if this code is run through the validator as it is intentional to not have a header as the H1 sits in the banner section above the form.
![Section Error](/docs/testing/ws3-code-validator-contact-us-issue-section.png)


When running my code through the CSS validator no errors were found:
![CSS Code Validator](/docs/testing/ws3-css-validator.png)

All other pages passed when running through the WS3 code validator, the only errors which returned were in regards to the comments in my code. 

### Browsers & Screen sizes:
---

This website has been cross checked on all different browsers to ensure that it works the same.

I also ran the website through [Ami Responsive](http://ami.responsivedesign.is/) and had family and friends check on their desktops and phones to check that everything performed correctly.

I also checked Developer tools throughout the building process however found that this could sometimes be buggy. 

- Above I have mentioned how when testing in different screen sizes I encountered some issues and how I fixed these for the Hero Image and the cover text.

### User stories tested:
---
