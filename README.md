
# Task 3: React, Tailwind & Basic Session Handling

## **Objective**

The goal of this task is to enhance your stock guessing game by porting it to a React + TypeScript project using Vite, and to implement game logic, name input, local storage, and a leaderboard, all styled using Tailwind CSS.

---

## Prerequisites

Before beginning this task, ensure you have the following installed:

-   **Node.js** ([Download Page](https://nodejs.org/en))
-   **Vite (React + TypeScript)** ([Setup Guide](https://vite.dev/guide/))
-   **Git** ([Download Page](https://git-scm.com/downloads))

Also, we are building on the previous task. If you haven't completed that and you want to straight away jump into this task, take a look at the [previous task's solution](https://github.com/Finova-MIT/fullstack-task-2-template). 

---

## Git Workflow Reminder

🚨 **Using the Git CLI is mandatory. Avoid GUI clients and drag/drop uploads.**  
Refer to [Task 1 Git Basics](https://github.com/Finova-MIT/fullstack-task-1-template/blob/main/README.md#git-basics) to brush up on essential commands like `git init`, `git add`, `git commit`, `git push`, and `git log`.

---

## Learning Resources

Refer to the following resources to brush up on React and Tailwind:
[React and Tailwind Learning Resource](https://docs.google.com/document/d/1s-cJsmTYCFdqsBFWPlm-0MzFZ4T8PgTfiy6l6Wj7vF4/edit?usp=sharing)

---

## Task: Full Game Implementation + Leaderboard

### **Phase 1: Port to React + Tailwind**

-   Convert your previous vanilla JS stock guessing game to a **React + TypeScript** application.
-   Style your components using **Tailwind CSS**.
-   Use **functional components and hooks**.    

### **Phase 2: Ask Player Name on Load**

-   When a user loads or refreshes the app, display a screen asking for their **name**. 
-   Only allow them to access the game **after entering a name**. 
-   Save the name in a React state.

### **Phase 3: Gameplay Logic**

-   Use the same API to fetch the stock price:  
    **API:** [https://finova-mancomm.vercel.app/api/stock](https://finova-mancomm.vercel.app/api/stock)
    
-   Modify guess validation:
    -   Correct guess if **price - 1 ≤ guess ≤ price + 1** (easier). 
-   Validate:
    -   Input must be a **non-negative number**.
    -   Up to **2 decimal places**.
    -   Must be **≤ 1000**.
        

### **Phase 4: Store Score in LocalStorage**

-   On a correct guess:
-   Update a **score counter** (1 point per correct guess).   
-   Save the updated score in `localStorage` using the **player’s name** as the key.
        

### **Phase 5: Leaderboard Page**

-   Create a `/leaderboard` route/page.
-   Fetch all entries from `localStorage`.
-   Sort them by score (highest to lowest).
-   Display top players in a clean, styled list.

---

## Submission Guidelines

1.  Clone your **auto-generated repository**.
2.  Work within the project and commit changes often using the **Git CLI**.
3.  Include a `README.md` or `Submission.md` file with:
    -   **Screen recording or GIF** of the app in action.
    -   **Screenshots of Git commands** used (e.g. commits, branches).
    -   **Screenshot of file/project structure** (include all directories under src/).
        
---

## **Evaluation Criteria**

Your submission will be evaluated on:

-   Use of **React + TypeScript** and **Tailwind CSS**.
-   Proper **state management and effect usage**.
-   LocalStorage integration and logic separation.
-   Clear, modular, and maintainable code.
-   Proper **Git CLI usage**.
    
### **Bonus Points:**

-   Smooth UX using **custom modals/popups** instead of browser `alert`.
-   Animations or transitions using Tailwind’s utility classes.
- Good component structure.
 
---

## Deadline

🕒 **20th July 2025, 11:59 PM**

Reach out in DMs or the group if you’re stuck or need clarification.  
Good luck and happy coding!

**Pranav**  
_Fullstack Development Head_
