# Testing

Throughout the building process of the website I have been checking Developer tools to ensure that the website is responsive on different devices as well as running my code through W3C CSS and HTML validators.

### Hero Image Cover text:

Whilst using developer tools I noticed that the cover text and divider were not responsive on the Hero image, to fix this I added in the below media queries for mobile view for the cover text ID.

```
{
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
}
```

When checking ami-responsive the white divider was overlapping the cover text background so I added the below media query to reduce the size of the divider for ipad:

```
{
@media screen and (min-width: 768px) {
  .divider-white {
      width: 300px;
  }
}
}
```

### Navbar Hamburger Menu:

Due to removing the Bootstrap styling from the navbar the hamburger icon disappeared. To fix this I added in a fontawesome icon to the span class "navbar-toggler-icon". The navbar wasn't centered so I added in CSS styling 'padding-top: 5px;" which fixed this.
I have clearly mentioned in my [CSS stylesheet](https://www.example.com) where I have overwritten some of the bootstrap styling to achieve this.

### Lighthouse:

Throughout the building process I checked my website's performance using lighthouse in the developer tools. To improve SEO and best practices I looked at the google suggestions on how to improve these.

#### SEO

Lighthouse returned the error of "Tap targets not sized properly" I improved the seo to 100% by increasing the size and adding padding to the Icons for the Social media links in thre footer.
After doing this to all pages and rerunning lighthouse SEO was at 100% for SEO.

#### Best Practices

For Best practices lighthouse returned the error of 'Display images with correct aspect ration" for the roots-logo in the navbar. To fix this I decreased the size of the logo and updated this on all pages.

#### Accesability

In order to improve the Accesability across all pages lighthouse suggested to add "rel="noopener" or rel="norefer" to all of my 'a' elements.

#### Performance

In order to improve performance, lighthouse suggested to compress all images. I compressed my images using [Tinypng](https://tinypng.com/)

### File paths:

When deploying my website to github I noticed that some of my images were not displaying. With the help of my mentor we discovered the issue was the file paths used. The image's in the style.css sheet were corrected by adding '/roots-cafe/' and images hosted on the page were fixed by removing the '/'.

#### WS3 Validator:

Throughout the building process of each section of the Roots cafe website I ran my code through the WS3 HTML & CSS validators. When running the 'Contact us' page through it returned the below errors:
![Input Field Error](/roots-cafe/assets/readme/ws3-code-validator-contact-us-issue.png)

This was fixed by removing "type="text-area"" from the element.

Contact us also returns the below error:
![Section Error](/roots-cafe/assets/readme/ws3-code-validator-contact-us-issue-section.png)

This error will still return if this code is run through the validator as it is intentional to not have a header as the H1 sits in the banner section above the form.

When running my code through the CSS validator no errors were found:
![CSS Code Validator](/roots-cafe/assets/readme/ws3-code-validator-contact-us-issue-section.png)

### User stories tested: