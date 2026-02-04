[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/cwb16fkL)
[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=22484390)
# afd-2023M-week-4-SASS

### Guided Learning Activity: Mastering SASS (SCSS) for Styling Web Applications

This learning activity is designed to help you master the fundamentals of **SASS (SCSS)**, a powerful CSS preprocessor. By the end of this activity, you will have designed and styled a web application using SASS, applying advanced features like variables, nesting, mixins, and more. The activity includes a **challenge section** where you will build a responsive web application from scratch, applying all the SASS concepts you’ve learned.

---

## **Learning Objectives**
1. Understand the fundamentals of SASS (SCSS) and its advantages over plain CSS.
2. Learn and apply SASS features like variables, nesting, mixins, and functions.
3. Use SASS to create modular and maintainable styles for a web application.
4. Build a responsive web application using SASS.
5. Complete a challenge to reinforce your learning.

---

## **Activity Structure**
1. **Introduction to SASS (SCSS)**
2. **SASS Fundamentals and Best Practices**
3. **Setting Up SASS in a Project**
4. **Hands-On Implementation with SASS**
5. **Challenge Section: Build and Style a Responsive Web Application**

---

### **1. Introduction to SASS (SCSS)**
SASS (Syntactically Awesome Style Sheets) is a CSS preprocessor that extends CSS with features like variables, nesting, mixins, and functions. It makes writing CSS more efficient and maintainable.

#### Key Concepts:
- **Variables**: Store reusable values (e.g., colors, fonts).
- **Nesting**: Write nested CSS rules for better readability.
- **Mixins**: Reusable blocks of styles.
- **Functions**: Perform calculations and return values.
- **Partials and Imports**: Organize styles into multiple files.
- **Operators**: Perform math operations directly in styles.

#### Example:
```scss
// Variables
$primary-color: #3498db;
$font-stack: 'Helvetica', sans-serif;

// Nesting
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }
  li { display: inline-block; }
  a {
    color: $primary-color;
    text-decoration: none;
  }
}

// Mixin
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
  -moz-border-radius: $radius;
  border-radius: $radius;
}

.button {
  @include border-radius(5px);
}
```

---

### **2. SASS Fundamentals and Best Practices**
Follow these best practices to write clean and maintainable SASS code:

#### a. Use Variables for Reusable Values
- Store colors, fonts, and other reusable values in variables.
- Example:
  ```scss
  $primary-color: #3498db;
  $secondary-color: #2ecc71;
  ```

#### b. Use Nesting Wisely
- Nest selectors to reflect the HTML structure.
- Avoid over-nesting to prevent overly specific CSS.

#### c. Use Mixins for Reusable Styles
- Create mixins for styles that are reused across the project.
- Example:
  ```scss
  @mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  ```

#### d. Use Partials and Imports for Modularity
- Split styles into smaller files (partials) and import them into a main file.
- Example:
  ```scss
  // _variables.scss
  $primary-color: #3498db;

  // main.scss
  @import 'variables';
  ```

#### e. Use Functions for Calculations
- Use SASS functions for dynamic calculations.
- Example:
  ```scss
  @function calculate-rem($px) {
    @return $px / 16 * 1rem;
  }
  ```

---

### **3. Setting Up SASS in a Project**
#### Step 1: Install SASS
1. Install SASS globally using npm:
   ```bash
   npm install -g sass
   ```

2. Alternatively, use a build tool like Webpack or Parcel to compile SASS.

#### Step 2: Set Up Your Project
1. Create a project folder:
   ```bash
   mkdir sass-project
   cd sass-project
   ```

2. Create a `styles` folder and add a `main.scss` file:
   ```bash
   mkdir styles
   touch styles/main.scss
   ```

3. Compile SASS to CSS:
   ```bash
   sass styles/main.scss styles/main.css
   ```

4. Link the compiled CSS file in your HTML:
   ```html
   <link rel="stylesheet" href="styles/main.css">
   ```

---

### **4. Hands-On Implementation with SASS**
#### Step 1: Create a Basic Layout
- Create a simple HTML structure:
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SASS Project</title>
    <link rel="stylesheet" href="styles/main.css">
  </head>
  <body>
    <header>
      <h1>Welcome to My Web App</h1>
      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <section class="hero">
        <h2>Hero Section</h2>
        <p>This is a hero section.</p>
      </section>
    </main>
    <footer>
      <p>&copy; 2023 My Web App</p>
    </footer>
  </body>
  </html>
  ```

#### Step 2: Style the Layout with SASS
- Use SASS features to style the layout:
  ```scss
  // Variables
  $primary-color: #3498db;
  $secondary-color: #2ecc71;
  $font-stack: 'Helvetica', sans-serif;

  // Mixins
  @mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  // Global Styles
  body {
    font-family: $font-stack;
    margin: 0;
    padding: 0;
  }

  header {
    background-color: $primary-color;
    color: white;
    padding: 1rem;
    @include flex-center;

    h1 {
      margin: 0;
    }

    nav {
      ul {
        list-style: none;
        margin: 0;
        padding: 0;
        @include flex-center;

        li {
          margin: 0 1rem;

          a {
            color: white;
            text-decoration: none;

            &:hover {
              text-decoration: underline;
            }
          }
        }
      }
    }
  }

  .hero {
    background-color: $secondary-color;
    padding: 2rem;
    text-align: center;
  }

  footer {
    background-color: $primary-color;
    color: white;
    text-align: center;
    padding: 1rem;
  }
  ```

---

### **5. Challenge Section: Build and Style a Responsive Web Application**
Now that you’ve learned the basics, it’s time to test your skills! In this challenge, you will build and style a responsive web application using SASS.

#### Scenario: **Portfolio Website**
You are tasked with building a responsive portfolio website for a fictional designer. The website should include the following pages:
1. **Home**: A hero section with a welcome message and call-to-action button.
2. **About**: A section with a bio and skills.
3. **Projects**: A grid layout showcasing projects with images and descriptions.
4. **Contact**: A contact form and social media links.

#### Requirements:
1. **Design Phase**:
   - Plan the layout and structure of the website.
   - Define a color scheme and typography using SASS variables.
   - Create reusable mixins for common styles (e.g., buttons, grids).

2. **Implementation Phase**:
   - Use SASS to style the website.
   - Implement responsive design using media queries.
   - Use partials and imports to organize your SASS code.

3. **Testing Phase**:
   - Test the website on different screen sizes (desktop, tablet, mobile).
   - Ensure the styles are consistent and maintainable.

#### Deliverables:
1. Push your code to a GitHub repository.
2. Include a `README.md` file with:
   - Instructions on how to compile and view the project.
   - A brief description of the design and SASS features used.
3. Submit your repository link via GitHub Classroom.

---

### **Additional Resources**
- [SASS Documentation](https://sass-lang.com/documentation)
- [CSS-Tricks Guide to SASS](https://css-tricks.com/guides/sass/)
- [Responsive Web Design Basics](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)

---

By completing this activity, you will have a solid understanding of SASS and be able to use it to create modular, maintainable, and responsive styles for web applications. Good luck!
