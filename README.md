# Responsive Portfolio Website – SASS (SCSS)

## Project Description
This project is a responsive portfolio website built using HTML and SASS (SCSS).  
It was developed to demonstrate a clear understanding of SASS fundamentals, modular styling, and responsive web design principles.

The website consists of four pages:
- Home
- About
- Projects
- Contact

All pages share a common layout and are styled using a single compiled CSS file generated from structured SCSS partials.

---

## Design Overview
The design follows a clean and minimal layout suitable for a personal portfolio.  
A consistent color scheme and typography are applied across all pages to ensure visual coherence.

The layout includes:
- A reusable header with navigation links
- A hero section on the home page
- A responsive grid layout for projects
- A contact form with accessible inputs
- A shared footer across all pages

Responsive behavior is implemented to ensure usability on desktop, tablet, and mobile screen sizes.

---

## SASS (SCSS) Features Used
The project makes use of the following SASS features:

- **Variables**  
  Used to define colors, fonts, and spacing values for consistency and easy maintenance.

- **Nesting**  
  Applied to reflect the HTML structure and improve readability of styles.

- **Mixins**  
  Created for reusable patterns such as flexbox centering, buttons, and responsive media queries.

- **Functions**  
  Used to convert pixel values to `rem` units for scalable typography.

- **Partials and Imports**  
  Styles are organized into partial files based on purpose (abstracts, base, layout, pages) and imported into a single `main.scss` file.

- **Responsive Design**  
  Media queries are managed through SASS mixins to adapt layouts for smaller screen sizes.

---

## Project Structure
sass-portfolio_website/
├── index.html
├── about.html
├── projects.html
├── contact.html
│
├── styles/
│ ├── main.scss
│ ├── main.css
│ │
│ ├── abstracts/
│ ├── base/
│ ├── layout/
│ ├── pages/



## How to Compile and View the Project

### 1. Install SASS
Make sure Node.js is installed, then install SASS globally:

```bash
npm install -g sass
```
2. Compile SCSS to CSS

From the project root directory, run:

``` sass styles/main.scss styles/main.css ```


(Optional: to watch for changes)

``` sass styles/main.scss styles/main.css --watch ```

3. View the Project

Open index.html in a web browser.
Use the navigation menu to access the About, Projects, and Contact pages.
