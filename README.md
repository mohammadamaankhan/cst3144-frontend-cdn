# After-School Lessons App - Frontend (Vue CDN)

This is the frontend application for my CST3144 Full Stack Development coursework, built with Vue 2 using CDN (no build tools required).

**Student**: Mohammad Amaan Khan (M00986493)  
**Email**: mk2310@live.mdx.ac.uk  
**Module**: CST3144 - Full Stack Development  
**Lecturer**: Dr. Chinnu Mary George  
**Academic Year**: 2025-26, Semester 1

## Technologies Used

- **Framework**: Vue 2 (via CDN)
- **Styling**: Tailwind CSS (via CDN)
- **Icons**: Font Awesome (via CDN)
- **HTTP Requests**: Fetch API
- **Deployment**: GitHub Pages

## Why Vue CDN?

As per course requirements, this implementation uses Vue 2 loaded directly via CDN script tag instead of Vue CLI or build tools. This approach:
- Aligns with course material
- Requires no build process
- Single HTML file with inline JavaScript
- Simple to understand and demonstrate

## Live Application

**Live App**: https://mohammadamaankhan.github.io/cst3144-frontend-cdn/

The frontend connects to my backend API hosted on Render.com: https://cst3144-backend-f7yf.onrender.com

**Note**: After first push, enable GitHub Pages in repo settings:
1. Go to Settings → Pages
2. Source: Deploy from branch
3. Branch: main → / (root)
4. Save

## Features

All features implemented in a single `index.html` file:

- ✅ Display lessons with subject, location, price, and availability
- ✅ Sort lessons by subject, location, price, or spaces (ascending/descending)
- ✅ Search lessons in real-time (search as you type with debouncing)
- ✅ Add lessons to shopping cart (reduces available spaces)
- ✅ Remove lessons from cart (restores spaces)
- ✅ Checkout with form validation (name: letters only, phone: numbers only)
- ✅ Submit orders to backend API
- ✅ All fetch API calls (GET, POST, PUT)

## Local Testing

Simply open `index.html` in your browser - no build step needed!

```bash
open index.html
```

Or use a local server:
```bash
python3 -m http.server 8000
# Visit http://localhost:8000
```

## Project Structure

```
frontend-cdn/
├── index.html    # Complete app in one file
└── README.md     # This file
```

Everything (HTML, CSS via Tailwind, JavaScript via Vue) is in one file for simplicity!

## CDN Links Used

- **Vue 2.7.16**: https://cdn.jsdelivr.net/npm/vue@2.7.16/dist/vue.js
- **Tailwind CSS**: https://cdn.tailwindcss.com
- **Font Awesome**: https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css

## Vue 2 Syntax Used

### Data Properties:
```javascript
data: function() {
  return {
    lessons: [],
    cart: [],
    // ...
  };
}
```

### Computed Properties:
```javascript
computed: {
  displayedLessons: function() {
    return this.lessons.sort(...);
  }
}
```

### Methods:
```javascript
methods: {
  fetchLessons: function() {
    fetch(this.apiBaseUrl + '/lessons')
      .then(...)
  }
}
```

### Lifecycle Hooks:
```javascript
mounted: function() {
  this.fetchLessons();
}
```

## Deployment

This single HTML file is deployed to GitHub Pages. No build process required - just commit and push!

## Source Code

**GitHub Repository**: [To be created]

## How It Works

1. Browser loads HTML file
2. Loads Vue 2 from CDN
3. Vue mounts to `<div id="app">`
4. Fetches lessons from backend on load
5. All interactions handled by Vue's reactivity system
6. User can browse, search, sort, and checkout
7. All data persists to MongoDB via backend API

Simple, clean, and fully functional!

