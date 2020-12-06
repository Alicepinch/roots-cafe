# Testing

During the building process of this website I was regularly checking Developer tools and the WS3 code validators to test the responsiveness and perfomrance of the website. Below is all the testing I ran and all of the changes that I made to improve on any issues that I encountered. 

### Hero Image Cover text:

---

Whilst using developer tools I noticed that the cover text and divider were not responsive on the Hero image, to fix this I added in the below media queries for mobile view for the cover text ID.

Code: 

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

When doing furthur checks on ami-responsive I noticed the white divider was overlapping the cover text background. To fix this I added the below media query to reduce the size of the divider for ipad:

Code: 

```

@media screen and (min-width: 768px) {
  .divider-white {
      width: 300px;
  }

```

### Hero Image
---
When testing mobile view, I noticed the style of image that I had used for the hero image didnt respond great in mobile as there was a lot of blank space and wasn't the best UX. 
In order to fix this I added in a Mobile hero image section to my code, this is clearly outlined in my comments in my [index.html](index.html) code. I then hid the original Hero Image section for mobile view and did the same for the mobile view section for larger screen sizes. 

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
When in phone view I noticed that the layout for the about us section wasn't the best UX. 
In order to fix this I wanted a different layout for when customers were in mobile view. To achieve this I duplicated the Sustainable Coffee Container and added in a Mobile coffee section. This is clearly commented out in my [index.html](index.html) file. 

In the CSS I set the original container "id="sustainable-coffee-container" for smaller screen sizes as "display: none;" 
So that in smaller screen sizes the new section "id="mobile-coffee-container"" would show. 
I then made sure that on larger screen size the "mobile-coffee-container" would not show.

Code: 

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

When building the Navbar using bootstrap. I removed the bootstrap styling as I wanted to style this in my own way. This made the hamburger menu in mobile view disappear. To fix this I added in a fontawesome icon to the span class "navbar-toggler-icon". The navbar wasn't centered so I added in CSS styling 'padding-top: 5px;" which fixed this.
I have clearly mentioned in my [CSS stylesheet](assets/css/style.css) where I have overwritten some of the bootstrap styling to achieve this.

### Lighthouse:

---

Throughout the building process I checked my website's performance using lighthouse in the developer tools. To improve SEO and best practices I looked at the google suggestions on how to improve these.

#### SEO

Lighthouse returned the error of "Tap targets not sized properly" I improved the SEO to 100% by increasing the size and adding padding to the Icons for the Social media links in the footer.
After doing this to all pages and re-running lighthouse SEO was at 100%.

#### Best Practices

For Best practices lighthouse returned the error of 'Display images with correct aspect ration" for the roots-logo in the navbar. To fix this I decreased the size of the logo and updated this on all pages.

#### Accessibility

In order to improve the Accessibility across all pages lighthouse suggested to add "rel="noopener" or rel="norefer" to all of my 'a' elements.
On the Contact us page to improve Accessibility google suggested to add labels to all of my form input fields. In my design I didn't want the form labels being displayed, so to improve accessibility with keeping the desired design I addeed in some CSS to hide the form labels. This was taken from [Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/forms/labels/#:~:text=this%20section%20Close-,Hiding%20label%20text,everyone%20better%20understand%20its%20purpose.&text=The%20label%20can%20be%20hidden,reader%20and%20speech%20input%20users) I have clearly commented out in my [CSS Style Sheet](assets/css/style.css) the copied code. 

#### Performance

For performance, lighthouse suggested to compress all images to save on loading time so I compressed all images using [Tinypng](https://tinypng.com/).

#### Reports 

- [Menu Page lighthouse results](/docs/testing/menu-lighthouse-report.png)
- [Contact Us page lighthouse results](/docs/testing/contact-us-lighthouse-report.png)
- [Homepage lighthouse results](/docs/testing/index-lighthouse-report.png)
- [Visit us page lighthouse results](/docs/testing/visit-us-lighthouse-report.png)

Please note that performance is still lower than the others, I tried the recommendations from lighthouse on how to improve these by converting all my images to webp files, however this was not supported in safari when running tests in different browsers so I reverted these back to jpg files. 
I also tried to decrease the sizing of my images to the exact sizing of the components however they lost their quality. 

### File paths:

When deploying my website to github I noticed that some of my images were not displaying. With the help of my mentor we discovered the issue was the file paths used. The image's in the style.css sheet were corrected by adding '/roots-cafe/' and images hosted on the page were fixed by removing the '/'. During the building process I did something revert the file paths back so that I could see the images in preview.

### Link Testing:

When doing final link checks for my project I noticed that the social links in the footer were going through to 404. To fix this I checked the URL's and they were missing : from "http://."
These links are now fixed. 

All external links will open in a new tab. 

When testing all of the instagram, twitter, facebook and trip advisor links these all opened in a new tab to the respective homepages. This is expected behaviour for now as the cafe is fictional and does not have its own pages on these platforms. 
The 'Our Supplier' CTA will open in a new tab to https://www.bridgecoffeeroasters.co.uk/wholesale/coffee/.

The 'View our menu' CTA on the homepage opens in the same tab to the menu page as it wouldn't be a great UX for a customer to have a new tab opened for the same website. 

#### WS3 Validator:

Throughout the building process of each section of the Roots cafe website I ran my code through the WS3 HTML & CSS validators.

When running the 'Contact us' page through it returned the below error for the text-area:
![Input Field Error](/docs/testing/ws3-code-validator-contact-us-issue.png)

This was fixed by removing "type="text-area"" from the element.

Contact us returned the below error for Headings:
![Heading Error](/docs/testing/ws3-contact-form-heading-issue.png)
In order to fix this, I moved the h1 from the form section into the parent section. 

The below error will still return if this code is run through the validator as it is intentional to not have a header in this section as the H1 sits in the section above the form.
![Section Error](/docs/testing/ws3-code-validator-contact-us-issue-section.png)


When running my code through the CSS validator no errors were found:
![CSS Code Validator](/docs/testing/ws3-css-validator.png)

All other pages passed when running through the WS3 code validator, the only errors which returned were in regards to the comments in my code. 

#### Form Testing:
---

The contact us form has been tested with different scenarios.

- When an empty form was submitted. The webpage promted me to fill in the first mandatory field. 
- I then filled each form field in one after another then submitted to check that all required form fields were working until a succesful form was submitted. 
   - Whilst testing the form I noticed that the 'textarea' element was not a required field so I fixed this.
- The form was filled in with a invalid email address. (missing ".co.uk") form was not submitted.
- When all form fields were completed correctly the form was submitted.

Please note that when submitting this form it will lead to a 405 error, this is because it isn't linked up to go through to anywhere at the moment and something that would be fixed in a future scope. 


#### Usability Testing:
---

This website has been cross checked on Safari, Chrome and Firefox and works in all of them. 

This has also been run through [Ami Responsive](http://ami.responsivedesign.is/) and checked with developer tools regularly to ensure that the website is responsive.
On top of this I checked on my Iphone directly as I found that the developer tools could sometimes be buggy. 
This was also checked on a larger screen size of 27inches to check the responsiveness.

I also sent this link out to some family and friends to check both the UX and to test that everything was working. 
- Above I have mentioned how when testing in different screen sizes/browsers I encountered some issues and how I fixed these for the Hero Image and cover text and image formats.

### User stories tested:
---

#### New customer:

**User Story:** As a new customer I would want to learn about Roots.
- When a customer lands on the Roots homepage, they can scroll down to the about us section where it tells them a little bit about roots and what they offer.

**User Story:** As a new customer I would like to know the opening times of the cafe.
- A customer can access the opening times by clicking on the 'Visit' page in the fixed navigation.

**User Story:** As a new customer I would like to know where the cafe is located and how to get there.
- A customer can view a map with the written address next to this by clicking on the 'Visit' page in the fixed navigation.

**User Story:** As a new customer I would like to be able to get in contact with the cafe if I had any questions.
- A customer can get in contact through the contact us form linked from the fixed navigation. They will also have access to quick contact details from the footer on the bottom of each page. 

**User Story:** As a new customer I would like some visuals of what to expect from the cafe.
- A customer can view the instagram feed at the bottom of the homepage or the carousel of images on the menu page. The customer will also get a feel for the Cafe through the colour scheme and images used across the site. 

**User Story:** As a new customer I would like to see some reviews from previous customers.
- A customer can view customer reviews via the 'Customer reviews section' on the homepage. This also links through to trip advisor where they could view more if the cafe was real.

#### Existing customer:

**User Story:** As a customer who has already visited Roots cafe before I would like to be able to view the menu to see if anything new has been added/ to plan what I will eat.
- A customer can click through to the menu from the fixed navigation bar at the top of the page. 

**User Story:** As a new customer I would like to be able to get in contact to book a table/ if I have any questions.
- A customer can click through to the contact page from the fixed navitation bar at the top of the page. They are also provided with quick contact details via the footer on each page. 

**User Story:** As a new customer I would like to know the steps being taken to keep up with the current climate.
- If a customer is planning to visit then they can find the covid update when they go to the 'Visit' page in the fixed navigation. 




