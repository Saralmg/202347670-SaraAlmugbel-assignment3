
# AI Usage Report – Assignment 3

**Student:** Sara Almugbel  
**Student ID:** 202347670  
**Course:** SWE 363 – Web Engineering  
**Project:** Advanced Interactive Personal Portfolio

## 1. Introduction

AI-assisted tools were used during the development of Assignment 3 to extend my existing personal portfolio website from Assignments 1 and 2.

The main objective was to introduce advanced JavaScript functionality, integrate an external API, improve form validation, and enhance the user experience.

ChatGPT assisted with planning, implementation, debugging, code explanations, testing guidance, and documentation.

## 2. AI Tool Used

**Tool:** ChatGPT (OpenAI)

**Purpose:**

- Understanding Assignment 3 requirements
- Planning advanced interactive features
- Generating HTML, CSS, and JavaScript code
- Implementing GitHub API integration
- Developing project sorting functionality
- Combining filtering and sorting
- Improving contact form validation
- Troubleshooting implementation problems
- Explaining JavaScript concepts
- Preparing assignment documentation

## 3. How AI Was Used

### 3.1 Planning and Feature Selection

I used ChatGPT to discuss Assignment 3 requirements and identify suitable features for my existing portfolio.

The selected features included:

- GitHub API integration
- Alphabetical project sorting
- Combined project filtering and sorting
- Advanced contact form validation
- Theme persistence using localStorage
- Responsive design improvements

These features were selected to extend the functionality of the existing website while preserving its original design.

### 3.2 HTML Improvements

ChatGPT assisted with modifying the HTML structure to support the new features.

Examples include:

- Adding a GitHub Projects section
- Adding a sorting dropdown
- Adding a dedicated project container ID
- Organizing project cards inside the correct container
- Adding navigation to the GitHub section
- Adding maximum-length attributes to contact form fields

The final HTML structure separates manually defined project ideas from dynamically loaded GitHub repositories.

### 3.3 CSS Improvements

ChatGPT assisted with CSS improvements, including:

- Styling the sorting dropdown
- Styling GitHub repository cards
- Maintaining the original burgundy color scheme
- Improving responsive layouts
- Ensuring filtered project cards are hidden
- Preserving hover effects and theme transitions

During debugging, I reviewed the project card styling and corrected CSS structure problems.

The final stylesheet includes a rule that hides filtered-out project cards.

### 3.4 JavaScript Implementation

ChatGPT assisted with implementing the main JavaScript features.

**GitHub API Integration:**

An asynchronous function uses fetch() and async/await to retrieve public repositories from the GitHub REST API.

The repository information is displayed dynamically using DOM manipulation.

**Project Sorting:**

JavaScript uses arrays, sort(), and localeCompare() to arrange project cards alphabetically.

The original project order is preserved so users can return to the default order.

**Combined Filtering and Sorting:**

A shared updateProjects() function handles both features.

The function sorts the project cards, applies the selected category filter, and updates the number of visible projects.

**Advanced Contact Form Validation:**

JavaScript validates required fields, minimum lengths, maximum lengths, and basic email formatting.

The form displays error messages or a success confirmation.

**Theme Persistence:**

The existing dark/light mode feature was preserved.

The selected theme is stored using localStorage and restored after refreshing the page.

## 4. Debugging and Problem Solving

Several issues occurred during Assignment 3 development.

### 4.1 Project Sorting Did Not Initially Work

After adding the sorting dropdown and JavaScript logic, selecting alphabetical sorting did not rearrange the project cards as expected.

I used ChatGPT to investigate the problem.

The debugging process included:

- Checking the sorting dropdown
- Inspecting JavaScript behavior in Safari
- Reviewing the HTML project container
- Checking the project card structure

After correcting the HTML structure, alphabetical sorting worked.

### 4.2 Project Filtering Displayed Both Cards

After sorting was fixed, the Campus filter still displayed both project cards.

ChatGPT suggested reviewing the project container and testing the filtering logic.

Several attempts were made to correct the problem.

The issue was resolved after replacing the HTML, CSS, and JavaScript with coordinated versions.

The final JavaScript uses one updateProjects() function for both filtering and sorting.

The CSS explicitly hides cards with the hidden attribute.

### 4.3 CSS Structure Problems

During editing, the project card CSS selector was accidentally moved.

ChatGPT helped identify the misplaced selector and restore the correct CSS rule.

### 4.4 Website Display Problem

At one point, the portfolio appeared as a blank gray page in Safari.

I reopened the local HTML file and confirmed that the website displayed again.

### 4.5 Final Code Revision

After repeated debugging attempts, I requested complete corrected versions of the three main files:

- index.html
- css/styles.css
- js/script.js

ChatGPT generated complete replacement code for each file.

I copied the code into Visual Studio Code, saved the files, and manually tested the functionality.

This approach helped ensure the HTML structure, CSS rules, and JavaScript logic were consistent.

## 5. Understanding the AI Suggestions

The main technical concepts used in Assignment 3 include:

- addEventListener(): Responds to user interactions.
- querySelectorAll(): Selects matching HTML elements.
- dataset: Reads custom data attributes.
- classList.toggle(): Changes CSS classes.
- localStorage: Stores theme preferences.
- preventDefault(): Prevents default form submission.
- sort(): Sorts JavaScript arrays.
- localeCompare(): Compares strings alphabetically.
- appendChild(): Moves existing DOM elements.
- fetch(): Requests external API data.
- async/await: Handles asynchronous operations.
- try/catch: Handles errors.
- textContent: Inserts text into HTML elements safely.

These concepts demonstrate how JavaScript can be used to build an interactive website that retrieves and processes external information.

## 6. Human Review and Modifications

I integrated the AI-assisted code into my project using Visual Studio Code.

I reviewed the website in Safari and tested its interactive features.

During development, I:

- Copied and integrated the suggested code
- Corrected project structure issues
- Checked the project filters
- Tested alphabetical sorting
- Tested filtering and sorting together
- Verified contact form validation
- Confirmed that GitHub repositories appeared
- Tested dark mode persistence after refreshing
- Updated the project documentation

I also retained the Projects section heading:

"My Project Ideas & Future Innovations"

This heading clarifies that the manually defined projects are ideas rather than completed applications.

## 7. Testing and Verification

The following functionality was manually verified:

| Feature | Expected Behavior | Result |
|---|---|---|
| Dark mode | Switch to dark appearance | Passed |
| Theme persistence | Remember theme after refresh | Passed |
| Campus filter | Show Campus Connect only | Passed |
| Productivity filter | Show Smart Study Planner only | Passed |
| All filter | Display both projects | Passed |
| Alphabetical sorting | Rearrange projects by name | Passed |
| Combined filtering and sorting | Both features operate together | Passed |
| Valid contact form | Display success confirmation | Passed |
| GitHub API | Display public repositories | Passed |

Additional edge cases and API failure scenarios have not been fully verified.

## 8. Responsible AI Usage

ChatGPT was used as a development and learning assistant.

AI-generated code and documentation suggestions were integrated into the project and reviewed through manual testing.

The AI assistance included substantial code generation, debugging, and documentation drafting.

This report identifies the major areas where AI contributed to the development process.

The accompanying evidence must contain the complete, unedited AI conversations and required intermediate artifacts.

## 9. AI Usage Log

The following log summarizes AI assistance during Assignment 3.

| Date | AI Tool | Purpose | Files Affected | Human Review and Modifications |
|---|---|---|---|---|
| November 20, 2026 | ChatGPT (OpenAI) | Plan Assignment 3 and identify advanced features | Project planning | Selected GitHub API integration, sorting, and improved validation |
| November 20, 2026 | ChatGPT (OpenAI) | Implement GitHub API integration | index.html, js/script.js | Added the code and verified that repositories appeared |
| November 20, 2026 | ChatGPT (OpenAI) | Implement alphabetical project sorting | index.html, js/script.js | Tested the sorting dropdown and investigated incorrect ordering |
| November 20, 2026 | ChatGPT (OpenAI) | Debug project filtering and HTML structure | index.html, css/styles.css, js/script.js | Inspected project containers and tested filtering behavior |
| November 20, 2026 | ChatGPT (OpenAI) | Rewrite and correct the three main website files | index.html, css/styles.css, js/script.js | Replaced the files in VS Code and tested the website |
| November 20, 2026 | ChatGPT (OpenAI) | Update README and technical documentation | README.md, docs/technical-documentation.md | Copied the updated documentation into the project |
| November 20, 2026 | ChatGPT (OpenAI) | Prepare Assignment 3 AI usage report | docs/ai-usage-report.md | Review the report and attach the required AI evidence before submission |

The entries above summarize the known development activities. They do not replace the complete conversation evidence required by the assignment.

## 10. AI Evidence

The AI evidence submission should include:

- Complete, unedited ChatGPT conversations used for Assignment 3
- AI-generated code and intermediate artifacts, where required
- Evidence of debugging and code revisions
- The final AI usage report
- Any additional materials specified by the assignment instructions

The evidence should be organized and included in the required submission format.

## 11. AI Usage Declaration

I acknowledge that ChatGPT was used extensively during the development of Assignment 3, including code generation, debugging, explanations, and documentation drafting.

I understand that all AI assistance must be disclosed accurately and supported by the evidence required by the instructor.

Before submission, I will verify that the evidence is complete and unedited and that I can explain the submitted code.

**Name:** Sara Almugbel  
**Student ID:** 202347670  
**Date:** November 20, 2026  
**Signature:** [Sign after verifying the declaration and evidence]
