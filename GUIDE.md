# Guide for React, Tailwind & Session Handling (Task 3)

This guide is meant to help you understand how to build your stock guessing game using **React**, **TypeScript**, **Tailwind CSS**, and **localStorage** for session handling. It does **not** contain code or solutions — use it to learn and apply the concepts yourself.

## 1. Project Structure & Folder Setup

Create your Vite project like you did for task 2. Key difference being you choose `React` over `Vanilla`.
In your Vite + React + TS project, your structure inside `src/` might look like this:
-   `App.tsx`: Main routing and layout
-   `components/`: For reusable UI components (e.g. InputBox, Game, LeaderboardList)
-   `pages/`: For your different screens like NameEntry, GamePage, Leaderboard
-   `utils/`: For helper functions like `fetchStockPrice()`, `validateGuess()`
This helps in maintaining modular and readable code.

## 2. React Basics

Understand key React concepts:

-   **Functional Components**: All components in this task should be functional.
    
-   **Hooks**: Use `useState` for storing data (name, guess, score, etc.) and `useEffect` for fetching stock price or checking localStorage.
    

Example concepts:

-   `useState<string>('')` (note that \<string\> here is optional and is inferred.)
    
-   `useEffect(() => { ... }, [])`
    

## 3. Tailwind CSS

You’ll use Tailwind for styling:

-   Use utility classes like `text-center`, `bg-blue-500`, `rounded`, etc.
    
-   Use responsive utilities like `md:p-8` for styling across screen sizes.
    
-   Use conditional classes (e.g. `className={isCorrect ? 'text-green-500' : 'text-red-500'}`)
    

Check the [Tailwind Docs](https://tailwindcss.com/docs) for more examples.

## 4. Routing (React Router)

To create a `/leaderboard` route, you'll need React Router:

-   Install it via `npm install react-router`
    
-   Use `<BrowserRouter>`, `<Routes>`, and `<Route>` to define page navigation
    
-   Example pages: `/` for name input/game, `/leaderboard` for leaderboard
    

Use `useNavigate()` for programmatic redirects (e.g., after name is entered).

## 5. State Management

React state will store:

-   `name`: Set after input, prevents game access before entering it
    
-   `guess`: Updated as user types
    
-   `price`: Fetched from API
    
-   `score`: Updated on correct guesses and stored in localStorage
    

Use `useState` for each of these and lift state where needed.

## 6. Session Handling via LocalStorage

Use `localStorage` to store scores:

-   On every correct guess, check if the name already exists in `localStorage`
    
-   If yes, increment score; if not, initialize to 1
    
-   Use `JSON.parse(localStorage.getItem(name))` to read and `localStorage.setItem(name, value)` to save
    

Avoid complex nesting — store scores as `{ [name: string]: number }`

Tip: Always `JSON.stringify()` when saving objects.

## 7. Fetching Stock Price

You’ll use `fetch()` or `axios` to call the API:

-   Use `async/await` inside `useEffect`
    
-   API: [https://finova-mancomm.vercel.app/api/stock](https://finova-mancomm.vercel.app/api/stock)
    
-   Store price in state on successful fetch
    
-   Re-fetch price after each guess to keep the game fresh
    

## 8. Input Validation

Before accepting a guess:

-   Ensure it’s a number (`!isNaN(Number(value))`)
    
-   Check if it’s ≥ 0 and ≤ 1000
    
-   Limit to 2 decimal places: use regex or `value.includes('.') && value.split('.')[1].length <= 2`
    

Use a validation helper in `utils/`.

## 9. Gameplay Logic

The guess is correct if:  
**price - 1 ≤ guess ≤ price + 1**

If guess is correct:
-   Increment score
-   Update localStorage
-   Show a success message
   
If incorrect, allow retry and show feedback.

## 10. Building the Leaderboard

In the `/leaderboard` page:
-   Loop through `localStorage` entries using `Object.entries()`
-   Sort by score (descending)
-   Map each name-score pair into a styled list using Tailwind

Use `Array.sort((a, b) => b[1] - a[1])` to sort by score.

## 11. Modals & UX Enhancements (Bonus)

Instead of using `alert()`:
-   Create a custom modal using Tailwind (e.g., absolute div with overlay and centered text)
-   Use `useState` to toggle modal visibility
-   Style with `bg-opacity-50`, `backdrop-blur`, `rounded-lg`, etc.
Add `transition`, `animate-fade-in`, or `scale` classes for a polished experience.

## 12. Clean Code Practices

-   Split logic into functions (e.g., `handleGuess`, `handleNameSubmit`)
-   Use clear naming (`userName`, `stockPrice`, `score`)
-   Keep one responsibility per component.   
-   Comment complex logic blocks  
-   Keep UI and logic separate when possible
    
## 13. Debugging and Development Tips

-   Use `console.log()` generously when testing logic
-   Use browser devtools to inspect localStorage, console, and network requests
-   Test all edge cases: empty guess, non-number input, decimal precision, etc.
    
## Summary

To succeed in this task, you need to:
-   Use React functional components and hooks effectively
-   Fetch and validate data
-   Use Tailwind for layout and styling
-   Store user data and scores using localStorage
-   Build a leaderboard with routing
-   Keep code modular and clean

Remember, the goal is **learning**. Focus on building one feature at a time. Don't hesitate to ask for help when you're stuck.

Good luck, and have fun!

**Pranav**  
_Fullstack Development Head_
