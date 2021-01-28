# Horiseon Code Refactor Challenge
## Description
In this challenge, I was tasked with refactoring HTML and CSS code to make it more accessible and searchable for users, increase readability for developers, and reduce redundancies in code for greater efficiency.

I accomplished this by replacing generic HTML tags with semantic tags, adding white space and comments to the HTML and CSS files, and consolidating duplicate declarations in multiple selctors in to singular ones (examples shown below in *Summary of Refactor Changes*).

In addition to refactoring the code, I also added some functionality to the webpage and fixed syntax and bugs (summarized in *Gotcha Moments*).

## Summary of Refactor Changes
### HTML
* added comments that separate main sections of the webpage as well as smaller subsections of the main content
* 

### CSS
* added comments that separated code into sections for portion of the webpage, and then reorganized code to its approriate commment header
* reorganized redundant code with multiple selectors under a new selector that still targeted the all the disered elements:
    Original code targeted each 
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
    Was revised to:
    ```
    .benefits div {
    margin-bottom: 32px;
    color: #ffffff;
}
    ```

### Gotcha Moments
* removed extraneous closing img tag from Cost Management within the Benefit section
* added an `id="search-engine-optimization"` to the search-engine-optimzation div allowing the nav link to direct to the section of the page
* added a favicon to the address bar
* added a meta desription for the webpage, just in case this ever gets published ;)

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
    * refactor html basic elements to semantic elements
    * ensure structure of hyml follows logical order
    * image elements contain relevant alt attributes
    * heading attributes fall in sequential order
    * title in title elemetn in concise and descriptive
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