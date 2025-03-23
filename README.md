# Kontinentalist Tech Assessment – Task 1

This is a simple web application built as part of the Kontinentalist internship assessment. It displays a list of stories from a provided API, showing the title, hero image, and content snippet (if available), with the ability to load more stories.

## 🚀 Features

- Clean, responsive design
- Fetches stories from Kontinentalist's public API
- Displays story title, hero image, and snippet of story content
- "Load More" button loads the next page of stories
- Added enhancement where hero image links to the original story on the Kontinentalist website 


## 🛠 Tech Stack

- [Vue 3](https://vuejs.org/)
- [Vite](https://vitejs.dev/) 
- [Bootstrap 5](https://getbootstrap.com/) 

## 📦 Setup Instructions

🛠️ You can run these commands using Bash, your VSCode terminal, or any terminal that supports Node.js (e.g., Git Bash, macOS Terminal, Windows Terminal, etc.)

### 1. Clone the repository

```bash
git clone https://github.com/Dexter-Wong/stories-app.git
cd stories-app
```

### 2. Install Dependencies  

Make sure you have Node.js installed
- Run `npm install`

### 3. Run the development server

- Run `npm run dev`

This will start the app at http://localhost:5173 

## Notes
- Stories without a dek field will only show their title and image.

- The snippet (dek) is in HTML format and rendered safely using v-html.

- The hero image links to the full story on https://kontinentalist.com/stories/{slug}