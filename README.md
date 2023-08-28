# Deployment Steps for GitHub Pages with a React App

This guide provides a step-by-step walkthrough on deploying a React app to GitHub Pages.

## 1. Initialize Your React App

If you haven't set up your React app yet:

```bash
npx create-react-app ecommerce-app
cd ecommerce-app
```

## 2. Installation

Ensure the `gh-pages` package is installed:

```bash
npm install gh-pages --save-dev
```

## 3. Configuration

In your `package.json`:

- Add a `homepage` field:

```json
  "name": "ecommerce-app",
  "version": "0.1.0",
  "private": true,
  "homepage": "https://jisshub.github.io/ecommerce-app/",
```

- Modify scripts for deployment:

```json
"scripts": {
   "predeploy": "npm run build",
   "deploy": "gh-pages -d build",
   // ... other scripts ...
}
```

## 4. Deploy

Deploy your app using:

```bash
npm run deploy
```

This will utilize the `gh-pages` branch in your repository and push the `build` directory to it.

## 5. Accessing the App

Your app should now be live at:

```
https://jisshub.github.io/ecommerce-app/
```

Remember: for any future updates, make your modifications, commit the changes, and run `npm run deploy` again.

---

# Troubleshooting Deployment Issues on GitHub Pages

Encountering issues like a blank screen after deployment? Follow these steps:

## 1. Use HashRouter Over BrowserRouter

React Router's `BrowserRouter` might have compatibility issues with GitHub Pages. Use `HashRouter` which operates with URL hashes:

```javascript
import { HashRouter as Router, Route } from "react-router-dom";
```

## 2. Commit and Push Changes

After making changes, such as transitioning from `BrowserRouter` to `HashRouter`, commit and push:

```bash
git add .
git commit -m "Switched to HashRouter for GitHub Pages deployment"
git push
```

## 3. Re-build the Project

Build the project again:

```bash
npm run build
```

## 4. Re-deploy the App

Deploy the app:

```bash
npm run deploy
```

## 5. Verify GitHub Pages Settings

- Navigate to your repository on GitHub.
- Enter the 'Settings' tab.
- In 'GitHub Pages', confirm the source is the `gh-pages` branch.
- Observe the given URL: `https://github-username.github.io/repository-name/`

## 6. Re-access the App

Access the app once more:

```
https://jisshub.github.io/ecommerce-app/
```

By following these instructions, your app should be visible without issues.

## 7. References

[ChatGPT*](https://chat.openai.com/share/b04be2e4-55b5-4bed-825a-efd63598472a)
--- 

