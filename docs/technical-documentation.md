
# Technical Documentation – Assignment 3

**Student:** Sara Almugbel  
**Student ID:** 202347670  
**Course Project:** Advanced Interactive Personal Portfolio

## 1. Project Overview

Assignment 3 extends my personal portfolio website from Assignments 1 and 2 by introducing advanced JavaScript functionality, external API integration, improved form validation, and project sorting.

The website includes four main sections:

- About Me
- Project Ideas
- GitHub Projects
- Contact

The application uses HTML, CSS, and vanilla JavaScript without requiring a frontend framework or backend server.

## 2. Technologies Used

### HTML5

Provides the website structure, including navigation, semantic sections, project cards, filter buttons, sorting controls, and the contact form.

### CSS3

Controls the appearance, layout, responsive design, hover effects, and dark/light themes.

CSS Grid and Flexbox are used to organize the interface.

### JavaScript (ES6+)

Handles DOM manipulation, event listeners, project filtering, sorting, theme switching, form validation, and API requests.

### Fetch API

Allows JavaScript to request external data asynchronously.

### GitHub REST API

Provides public repository information, including repository names, descriptions, and links.

### localStorage

Stores the visitor's selected theme in the browser so the preference can be restored after refreshing.

## 3. Application Architecture

The application consists of three main files:

- `index.html` – Defines the website structure.
- `css/styles.css` – Defines the visual appearance and responsive layouts.
- `js/script.js` – Implements interactive functionality.

The JavaScript file is organized into clearly labeled feature sections.

The script is loaded using the `defer` attribute, allowing the HTML to be parsed before the JavaScript executes.

This ensures that the required DOM elements are available when the event listeners are registered.

## 4. Interactive Features

### 4.1 Dark and Light Mode

The theme button allows users to switch between dark and light appearances.

JavaScript uses:

`document.body.classList.toggle("dark")`

CSS variables define the colors used by each theme.

The selected preference is saved using:

`localStorage.setItem("portfolio-theme", selectedTheme)`

When the page loads, JavaScript retrieves the saved preference using `localStorage.getItem()`.

If browser storage is unavailable, the theme button can still change the appearance for the current session.

The button also updates its `aria-pressed` attribute to reflect its state.

### 4.2 Dynamic Project Filtering

The Projects section includes three filter buttons:

- All
- Productivity
- Campus

Each project card contains a `data-category` attribute.

For example:

```html
<article class="project-card" data-category="campus">
```

JavaScript reads the selected filter using `dataset.filter`.

The selected category is stored in the `selectedCategory` variable.

Each card is compared with the selected category.

Nonmatching cards are hidden using:

`card.hidden = !matches;`

The CSS rule `.project-card[hidden]` ensures hidden cards are not displayed.

A status message indicates how many projects are visible.

### 4.3 Project Sorting

Assignment 3 introduces a sorting dropdown with three options:

- Default Order
- Name (A–Z)
- Name (Z–A)

JavaScript stores the original project cards in an array:

```javascript
const originalProjects = [...projectCards];
```

When the user changes the sorting option, JavaScript creates a copy of the original array.

For alphabetical sorting, the program uses the `sort()` method and `localeCompare()` to compare project names.

For example:

```javascript
sortedProjects.sort((a, b) => {
  const nameA = a.querySelector("h3").textContent.trim();
  const nameB = b.querySelector("h3").textContent.trim();

  return nameA.localeCompare(nameB);
});
```

The sorted cards are then rearranged inside the project container using `appendChild()`.

The original DOM elements are reused rather than recreated.

### 4.4 Combining Filtering and Sorting

Filtering and sorting are managed by a shared function:

`updateProjects()`

This function performs the following operations:

1. Reads the selected sorting option.
2. Creates a copy of the original project array.
3. Sorts the copied array when required.
4. Rearranges the project cards in the DOM.
5. Applies the selected category filter.
6. Updates the number of visible projects.

Both filter buttons and the sorting dropdown call the same function.

This design ensures that filtering and sorting work together without conflicting.

### 4.5 Advanced Contact Form Validation

The contact form contains three fields:

- Name
- Email
- Message

JavaScript listens for the form's `submit` event.

`event.preventDefault()` prevents the browser from submitting the form and refreshing the page.

The validation rules are:

1. All fields must contain nonempty values.
2. The name must contain at least 2 characters.
3. The email must match a basic email-format pattern.
4. The message must contain at least 10 characters.
5. Field values must not exceed the specified maximum lengths.

The email validation uses the regular expression:

```javascript
const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
```

The `showFormMessage()` function displays error or success messages.

If the input is valid, the form displays a confirmation message and resets the fields.

The form is a client-side demonstration and does not transmit messages to a server.

## 5. External API Integration

### 5.1 API Selection

The GitHub REST API was selected because it provides publicly accessible information about software repositories.

It allows the portfolio to display current repository information without manually updating HTML cards.

### 5.2 API Endpoint

The application sends a GET request to:

```text
https://api.github.com/users/Saralmg/repos?sort=updated&per_page=6
```

The endpoint requests up to six public repositories, ordered by their latest updates.

### 5.3 Fetching Data

The application uses an asynchronous function named `loadGitHubProjects()`.

The function sends a request using `fetch()`:

```javascript
const response = await fetch(
  "https://api.github.com/users/Saralmg/repos?sort=updated&per_page=6"
);
```

The application checks `response.ok` before processing the response.

The response body is converted into JavaScript objects using:

`await response.json()`

### 5.4 Displaying Repository Information

For each repository, JavaScript dynamically creates:

- An article element for the repository card
- A heading containing the repository name
- A paragraph containing the repository description
- A link to the repository on GitHub

The application uses `textContent` to insert repository names and descriptions as plain text.

Repository links open in a new tab and use `rel="noopener noreferrer"`.

### 5.5 API Error Handling

The API request is placed inside a `try...catch` block.

If the request fails or GitHub returns an unsuccessful response, the application displays:

"Unable to load GitHub projects. Please try again later."

The error is also logged using `console.error()`.

If the API returns an empty repository list, the application displays a message indicating that no public repositories were found.

## 6. State Management and Persistence

The application manages two types of state.

### Persistent Theme State

The selected theme is stored in localStorage and restored when the page reloads.

### Temporary Project State

The selected project category is stored in the `selectedCategory` variable.

The sorting option is read from the dropdown element.

Filtering and sorting state are maintained while the page remains open, but are not saved across page reloads.

## 7. Performance and Code Quality

The application uses several techniques to maintain simple and efficient code.

### 7.1 Reusing DOM Elements

Sorting rearranges existing project cards instead of creating new cards every time.

This reduces unnecessary element creation.

### 7.2 Preserving Original Project Order

The original project array is stored once.

Sorting operates on a copy of this array, allowing the default order to be restored.

### 7.3 Asynchronous API Requests

The GitHub API is requested asynchronously using `async/await`.

This avoids blocking the page while waiting for the network response.

### 7.4 Limited API Results

The `per_page=6` query parameter limits the number of repositories requested.

This reduces the amount of repository data processed and displayed.

### 7.5 Shared Update Function

The `updateProjects()` function handles both filtering and sorting.

This reduces duplicated logic and makes the code easier to maintain.

### 7.6 Safe Text Rendering

GitHub repository names and descriptions are inserted using `textContent` rather than `innerHTML`.

This prevents repository text from being interpreted as HTML.

## 8. Animations and Transitions

CSS transitions improve the user experience.

Examples include:

- Button hover effects
- Project card hover effects
- Smooth theme color transitions
- Smooth navigation scrolling

The website respects reduced-motion preferences through the `prefers-reduced-motion` media query.

## 9. Error Handling and User Feedback

The application provides feedback through:

- Required-field validation messages
- Invalid email messages
- Minimum-length validation messages
- Maximum-length validation messages
- Successful form validation confirmation
- Project filtering status messages
- Empty project result messages
- GitHub API loading and error messages
- Console warnings if localStorage is unavailable

Status messages use `role="status"` and `aria-live="polite"` to support accessibility.

## 10. Responsive Design

The website uses CSS Grid and Flexbox.

Project cards are displayed in two columns on wider screens.

A media query at `max-width: 700px` changes the project grid to one column.

Navigation elements can wrap to fit smaller screens.

Sorting controls also adjust their layout on mobile devices.

## 11. Testing

The following functionality was manually verified during development:

| Test | Expected Result | Result |
|---|---|---|
| Dark mode | Switch to dark theme | Passed |
| Theme persistence | Retain dark mode after refresh | Passed |
| Productivity filter | Show Smart Study Planner only | Passed |
| Campus filter | Show Campus Connect only | Passed |
| All filter | Show both projects | Passed |
| A–Z sorting | Show Campus Connect first | Passed |
| Filtering and sorting | Both features work together | Passed |
| Valid contact form | Display confirmation | Passed |
| GitHub API | Display public repositories | Passed |

Additional validation edge cases, API failure scenarios, and mobile layouts should be tested before final submission.

## 12. Limitations

- The contact form does not send real emails.
- The portfolio currently contains two manually defined project ideas.
- The GitHub API requires an internet connection.
- GitHub API requests may be affected by rate limits or network failures.
- Project filtering and sorting preferences are not saved after refreshing.
- The application does not use a backend server.

## 13. Future Improvements

Possible improvements include:

- Adding more completed software projects
- Implementing project search functionality
- Connecting the contact form to a backend service
- Adding additional project categories
- Implementing more advanced sorting options
- Deploying the portfolio using GitHub Pages

## 14. Conclusion

Assignment 3 demonstrates the integration of HTML, CSS, JavaScript, and an external REST API to create a responsive and interactive personal portfolio.

The main technical concepts include DOM manipulation, event handling, asynchronous API requests, filtering and sorting algorithms, localStorage, input validation, error handling, and responsive design.
