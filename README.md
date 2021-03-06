# Horiseon Code Refactor Challenge
  - [Description](#description)
  - [Summary of Refactor Changes](#summary-of-refactor-changes)
    - [HTML](#html)
    - [CSS](#css)
    - [Gotcha Moments](#gotcha-moments)
  - [Demo](#demo)
  - [Test Conditions and Grading Criteria](#test-conditions-and-grading-criteria)
    - [User Story](#user-story)
    - [Acceptance Criteria](#acceptance-criteria)
    - [Summary of Grading Requirements](#summary-of-grading-requirements)

## Description
In this challenge, I was tasked with refactoring HTML and CSS code to make it more accessible and searchable for users, increase readability for developers, and reduce redundancies in code for greater efficiency.

I accomplished this by replacing generic HTML tags with semantic tags, adding white space and comments to the HTML and CSS files, and consolidating duplicate declarations in multiple selctors in to singular ones (examples shown below in *Summary of Refactor Changes*).

In addition to refactoring the code, I also added some functionality to the webpage and fixed syntax and bugs (summarized in *Gotcha Moments*).

## Summary of Refactor Changes
### HTML
* Added comments that separate main sections of the webpage as well as smaller subsections of the main content:  
    `<!-- content section -->`  
    `<!-- search engine optimization article -->`
* Revised inner HTML of the `<title>` element to `Horiseon - Social Solutions Services`
* Replaced (most) `<div>`s with the appropriate `<header>`, `<nav>`, `<section>`, `<article>`, and `<footer>` semantic tags:
    ```
    <div class="footer">
    ...
    </div>
    ```
    Was replaced with:
    ```
    <footer>
    ...
    </footer>
    ```
    Each visual partitions of the webpage are separated into a `<main>` element and a `<section>` element. `<div>`s within `<main class="content">` were replaced with `<article>` tags because there content seemed like the most relevant on the page and therefor I wanted them to stand out from the rest of the content on the page. `<div>`s in the `<section class="benefits">` were left as `<div>`s because they lacked specificity and therefor fit well with the basic `<div>` tag.
* Added alt attributes to all images:  
    Images within the `.content` section were given descriptions in their alt attribute because it was relevant(ish) to the understanding of the material:  
    ```
    <img src="./assets/images/social-media-marketing.jpg" class="float-left"
        alt="employees working at conference table with laptops and media image cutouts" />
    ```
    Images with `.benefits` section had alt attributes with no value associated because their sole function was inonography:  
    `<img src="./assets/images/lead-generation.png" alt="" />`

### CSS
* Added comments that separated code into sections for portion of the webpage, and then reorganized code to its approriate comment header:  
    `/* styles for header section */`
* Reorganized redundant code with multiple selectors under a new selector that still targeted the all the desired elements:  
    Original code targeted each div in the `.benefits` section individually, but with all the same styles:
    ```
    .benefit-lead {
        margin-bottom: 32px;
        color: #ffffff;
    }

    .benefit-brand {
        margin-bottom: 32px;
        color: #ffffff;
    }

    .benefit-cost {
        margin-bottom: 32px;
        color: #ffffff;
    }
    ```
    By targeting the `<div>`s within the parent `.benefits`, we accomplish the same goal with less code:
    ```
    .benefits div {
        margin-bottom: 32px;
        color: #ffffff;
    }
    ```
* Removed redundant or unneccessary selectors from rule-sets:  
    This selector targets the `.seo` class within `<h1>` elements within elements with the `.header` class:
    ```
    .header h1 .seo {
        color: #d9dcd6;
    }
    ```
    However, selecting just the `.seo` class is cleaner and does not decrease funtionality because the `.seo` class is liekly to only be used for this single styling:
    ```
    .seo {
        color: #d9dcd6;
    }
    ```
* Revised selectors in CSS to match changes in of HTML basic elements to semantic elements:  
    ```
    .footer h2 {
        font-size: 20px;
    }
    ```
    Was revised to:
    ```
    footer h2 {
        font-size: 20px;
    }
    ```
* Removed extraneous properties from rule-sets that did not actually affect the style:  
    ```
    .benefits {
        margin-right: 20px;
        padding: 20px;
        clear: both;
        float: right;
        width: 20%;
        height: 100%;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        background-color: #2589bd;
    }
    ```
    `clear: both` and `height: 100%` have no bearing on the styles based on the other styling properties, so they were removed:
    ```
    .benefits {
        margin-right: 20px;
        padding: 20px;
        float: right;
        width: 20%;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        background-color: #2589bd;
    }
    ```
* Removed rule-sets altogether that did not have any bearing on styles:  
    ```
    p {
        font-size: 16px;
    }
    ```
    Since `<p>` elements default to 16px, this rule-set was removed for redundancy


### Gotcha Moments
* Removed extraneous `</img>` tag image in `<div class="benefit-cost">`
* Added an `id="search-engine-optimization"` property to the `<article class="search-engine-optimization">` allowing the `<a href="#search-engine-optimization">Search Engine Optimization</a>` nav link to direct to the section of the page
* Added a favicon to the address bar
* Added a meta desription for the webpage, just in case this ever gets published ;)
* Added `<a href="#>` to Horiseon header which links to the top of the page, making future edits to the application easier if more pages are added

## Demo
A link to the most up-to-date version of the project can be found here: [Horiseon - Social Solution Services](https://glendonintendo.github.io/challenge1-horiseon-accessibility/).  

I have also provided a screen shot of the launched webpage below:
![Image](assets/images/horiseon-webpage-screenshot.png)

## Test Conditions and Grading Criteria
### User Story
>AS A marketing agency  
I WANT a codebase that follows accessibility standards  
SO THAT our own site is optimized for search engines

### Acceptance Criteria
>GIVEN a webpage meets accessibility standards  
WHEN I view the source code  
THEN I find semantic HTML elements  
WHEN I view the structure of the HTML elements  
THEN I find that the elements follow a logical structure independent of styling and positioning  
WHEN I view the image elements  
THEN I find accessible alt attributes  
WHEN I view the heading attributes  
THEN they fall in sequential order  
WHEN I view the title element  
THEN I find a concise, descriptive title

### Summary of Grading Requirements
#### Technical Acceptance Criteria: 40%
- [x] Satisfies all preceding acceptance criteria
    * refactor HTML basic elements to semantic elements
    * ensure structure of HTML follows logical order
    * image elements contain relevant alt attributes
    * heading attributes fall in sequential order
    * title in title element is concise and descriptive
- [x] Application's links all function properly
- [x] Application's CSS selectors and properties are consolidated and organized to follow semantic structure
- [x] Application's CSS file is properly commented
#### Deployment: 32%
- [x] Application deployed at live URL
- [x] Application loads with no errors
- [x] Application GitHub URL submitted
- [x] GitHub repo contains applicable code
#### Application Quality: 15%
- [x] Application resembles screenshots provided in challenge instructions
#### Repository Quality: 13%
- [x] Repository has unique name
- [x] Repository follows best practices for file structure and naming conventions
- [x] Repository follows best practices for class/id naming conventions, indentation, quality comments, etc.
- [x] Repository contains multiple descriptive commit messages
- [x] Repository contains quality README file with description, screenshot, and link to deployed application