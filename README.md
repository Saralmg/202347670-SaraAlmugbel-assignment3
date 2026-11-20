
# Personal Portfolio Website – Assignment 3

**Student:** Sara Almugbel  
**Student ID:** 202347670  
**University:** King Fahd University of Petroleum & Minerals (KFUPM)

## Project Description

This project is an enhanced version of my personal portfolio website developed for Assignments 1 and 2.

The purpose of Assignment 3 is to extend the website with advanced JavaScript functionality, external API integration, improved form validation, project sorting, and state persistence.

The website introduces me as a Software Engineering student, displays my project ideas, retrieves public GitHub repositories, and includes an interactive contact form.

## Technologies Used

- HTML5 – Website structure and semantic elements
- CSS3 – Styling, responsive layouts, and animations
- JavaScript (ES6+) – Interactive functionality and DOM manipulation
- Fetch API – Retrieving external data asynchronously
- GitHub REST API – Displaying public repositories
- localStorage – Saving the selected theme
- Git and GitHub – Version control and repository hosting
- ChatGPT – AI-assisted development, explanations, and debugging

## Interactive Features

### 1. Dark and Light Mode

Users can switch between dark and light themes.

The selected theme is saved using localStorage, allowing the website to remember the user's preference after refreshing the page.

### 2. Dynamic Project Filtering

The Projects section contains three filter buttons:

- All
- Productivity
- Campus

JavaScript displays project cards based on the selected category.

A status message informs users how many projects are currently displayed.

### 3. Project Sorting

Users can sort project ideas using a dropdown menu.

Available options:

- Default Order
- Name (A–Z)
- Name (Z–A)

JavaScript uses the `sort()` method and `localeCompare()` to arrange projects alphabetically.

Filtering and sorting work together, allowing users to sort projects while a category filter is active.

### 4. GitHub API Integration

The website connects to the GitHub REST API to retrieve public repositories from my GitHub account.

API endpoint:

https://api.github.com/users/Saralmg/repos?sort=updated&per_page=6

JavaScript uses `async/await` and `fetch()` to request repository information.

Each repository card displays:

- Repository name
- Repository description, if available
- A link to view the repository on GitHub

The website also handles API errors and displays a message if repositories cannot be loaded.

### 5. Advanced Contact Form Validation

The contact form accepts a name, email address, and message.

JavaScript validates the following conditions:

- All fields must be completed.
- The name must contain at least 2 characters.
- The email must follow a valid basic email format.
- The message must contain at least 10 characters.
- Input values must not exceed the maximum allowed lengths.

The website displays clear error messages when validation fails and a confirmation message when validation succeeds.

The form is a demonstration and does not send real emails.

### 6. Animations and Transitions

The website includes:

- Smooth scrolling between sections
- Hover effects on project cards
- Button hover animations
- Smooth transitions between light and dark themes

The CSS also respects reduced-motion accessibility preferences.

### 7. Responsive Design

CSS media queries and flexible layouts allow the website to adapt to different screen sizes.

On smaller screens, the project grid changes from two columns to one column.

Navigation and sorting controls also adjust to fit smaller displays.

## Project Structure

```text
202347670-SaraAlmugbel-assignment3/
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
├── assets/
│   └── images/
├── docs/
│   ├── ai-usage-report.md
│   └── technical-documentation.md
├── README.md
└── .gitignore
```

## How to Run the Website Locally

1. Download or clone this repository.
2. Open the project folder in Visual Studio Code.
3. Locate the `index.html` file.
4. Open `index.html` in Safari, Chrome, or another modern web browser.
5. Test the project filters, sorting dropdown, theme button, GitHub projects, and contact form.

No additional packages or installations are required.

An internet connection is required to load repositories from the GitHub API.

## Testing

The following features were manually tested:

- Dark/light theme switching
- Theme persistence after refreshing
- Project filtering by category
- Alphabetical sorting
- Filtering and sorting together
- Contact form validation with valid input
- GitHub API repository display

Additional edge cases and browser compatibility should be verified before final submission.

## Performance and Code Quality

The project uses plain JavaScript without requiring additional frontend libraries.

Project cards are rearranged using existing DOM elements instead of being recreated whenever sorting changes.

The original project order is preserved in an array so that users can return to the default order.

GitHub repository cards are generated dynamically after the API response is received.

The code is divided into clearly labeled sections to improve readability and maintainability.

## AI Assistance

ChatGPT was used during development to assist with:

- Planning Assignment 3 features
- Implementing GitHub API integration
- Developing project sorting functionality
- Combining project filtering and sorting
- Improving contact form validation
- Debugging HTML, CSS, and JavaScript issues
- Explaining code and updating documentation

AI-generated suggestions were reviewed and manually tested.

For more information, see:

[AI Usage Report](docs/ai-usage-report.md)

## Technical Documentation

Detailed explanations of the website architecture, JavaScript functionality, API integration, and testing are available in:

[Technical Documentation](docs/technical-documentation.md)

## Future Improvements

Potential improvements include:

- Adding more completed software projects
- Connecting the contact form to a backend service
- Adding project search functionality
- Introducing additional sorting options
- Deploying the portfolio using GitHub Pages

## Author

Sara Almugbel  
Software Engineering Student – KFUPM
