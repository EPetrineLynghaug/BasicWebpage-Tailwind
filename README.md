# Lecture notes, Tailwind CSS Setup and Overview

Tailwind CSS has rapidly become the preferred alternative to frameworks like Bootstrap due to its utility-first approach, focusing on styling individual elements rather than pre-built components. This guide provides an introduction to Tailwind, explains why and how we use it, and includes a setup tutorial.

## What is Tailwind CSS?
<details>
  <summary><strong>Click to read more</strong></summary>

Tailwind CSS is a utility-first CSS framework that allows you to apply styling directly to elements with predefined classes. This approach means more code initially but greater flexibility overall. Unlike traditional frameworks, Tailwind doesn’t impose design constraints, allowing you to customize and theme your application easily. It supports responsive design, includes dark mode out of the box, and can be purged for unused CSS classes to keep files small.
</details>

### Why Use Tailwind?
<details>
  <summary><strong>Click to read more</strong></summary>

- **Utility Classes**: Tailwind’s class-based system lets you style elements directly in HTML, removing the need for extensive custom CSS.
- **Color Shades**: Classes often come with color variants, e.g., `bg-blue-500`, where higher numbers represent darker shades, simplifying consistent design.
- **Responsive Design**: Built-in support for responsive layouts with breakpoints like `sm:`, `md:`, `lg:`, and `xl:`.
- **Customization**: Easily override default themes and extend functionality without needing SASS.
- **Unused CSS Purging**: Reduces file size by purging unused CSS, leaving only what's needed for your project.

[Explore the Tailwind UI Documentation](https://tailwindcss.com/docs/background-color) for a detailed guide on specific utilities.
</details>

## Tailwind vs. Bootstrap
<details>
  <summary><strong>Click to read more</strong></summary>

### Tailwind:
- **Approach**: Utility-first, highly customizable, provides maximum design flexibility.
- **File Size**: Small when purged of unused classes.
- **Learning Curve**: Requires familiarity with utility classes but speeds up development once learned.
  
### Bootstrap:
- **Approach**: Component-based with a predefined design system.
- **File Size**: Larger by default but can be cherry-picked.
- **Learning Curve**: Easier to start with, but less flexible for custom designs.
</details>

## Setting Up Tailwind CSS
<details>
  <summary><strong>Click to read more</strong></summary>

1. **Initialize Project**:
```bash
npm init -y
npm install tailwindcss
npx tailwindcss init -p
```

2. **Configure tailwind.config.js**:   
```js
module.exports = {
content: ["./src/**/*.{html,js}"],
theme: {
extend: {},
},
plugins: [],
}
```
3.	**Add CSS Imports**:
In src/styles/styles.css, add the following lines:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

4. **Add Build Scripts**:
In package.json, configure the build scripts:
```json 
"scripts": {
  "build:css": "npx tailwindcss -i ./src/styles/styles.css -o ./dist/output.css",
  "watch:css": "npx tailwindcss -i ./src/styles/styles.css -o ./dist/output.css --watch"
}
```

5.	**Run Build Command**:
```bash  
npm run build:css
npm run watch:css
```

6. **Set Up HTML Template**:
```HTML
 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Tailwind Project</title>
  <link rel="stylesheet" href="./dist/output.css">
</head>
<body class="font-sans antialiased">
  <!-- Your content goes here -->
</body>
</html>
```
</details>

### Practical Tailwind Example
<details>
  <summary><strong>Click to read more</strong></summary>

**Navigation Bar**
```HTML
<header class="bg-gray-800 text-white py-4">
  <div class="container mx-auto flex justify-between items-center">
    <h1 class="text-xl font-semibold">Site Logo</h1>
    <nav>
      <ul class="flex space-x-4">
        <li class="hover:text-gray-400">Home</li>
        <li class="hover:text-gray-400">About</li>
        <li class="hover:text-gray-400">Contact</li>
      </ul>
    </nav>
  </div>
</header>
```

**Hero Section**
```HTML
<section class="bg-cover bg-center h-64 text-center flex items-center justify-center" style="background-image: url('/path/to/image.jpg');">
  <h2 class="text-4xl font-semibold text-white opacity-50">Welcome to Our Site</h2>
</section>
```

**Responsive Product Cards**
```HTML
<section class="py-10 bg-gray-100">
  <div class="container mx-auto grid grid-cols-1 md:grid-cols-3 gap-6">
    <!-- Repeat this card for multiple items -->
    <div class="bg-white p-4 rounded-lg shadow-lg">Product Card</div>
  </div>
</section>
```
</details>

### Summary
<details>
  <summary><strong>Click to read more</strong></summary>

Tailwind CSS allows for rapid prototyping and scales well for larger projects by offering customizable utility classes for a streamlined and responsive design. Perfect for projects where you need flexibility, rapid prototyping, and efficient styling without extensive custom CSS files.
</details>


# Install dependencies
```bash
npm install -D tailwindcss postcss autoprefixer
```
# Initialize Tailwind config
```bash
npx tailwindcss init -p
```
# Start CSS build process
```bash
npm run build:css
```
# Watch CSS for changes
```bash
npm run watch:css
```