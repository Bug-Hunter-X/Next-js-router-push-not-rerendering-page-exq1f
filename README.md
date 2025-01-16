# Next.js router.push Not Rerendering Page

This repository demonstrates a bug in Next.js where `router.push('/')` does not rerender the home page after navigating from the about page.  The issue seems to be related to how Next.js handles client-side navigation and rehydration.

## Steps to Reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm run dev` to start the development server.
4. Navigate to `/about`.
5. Click the button to navigate back to `/`.

You'll observe that the UI does not update to show the home page content.  The URL changes, but the content remains that of the `/about` page.

## Solution
The solution involves using `router.replace()` instead of `router.push()`. `router.replace()` does not add a new entry to the browser history which resolves the re-rendering issue.  See `bugSolution.js` for the corrected code.