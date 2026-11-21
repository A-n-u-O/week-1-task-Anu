# Week 1 Assessment — Task Tracker Exploration

**Program:** She Code Africa FutureHer AI — Software Engineering  
**Student:** Anuoluwapo Victor  
**Repository:** https://github.com/A-n-u-O/week-1-task-Anu

## 1. Application Overview

The starter application is a full-stack task tracker built with React, Express.js, and SQLite.

I created my own repository from the provided template and ran the application using GitHub Codespaces.

The frontend runs on port 5173, while the backend runs on port 4000.

The application allows users to create tasks, assign priorities and due dates, mark tasks as completed, filter tasks by status, edit task titles, and delete tasks.

## 2. Understanding the Application

### Frontend — React

The `client/src/App.tsx` file contains the task tracker interface.

It uses `useState` to manage tasks, form inputs, filters, and editing state.

It uses `useEffect` to retrieve existing tasks when the component first loads.

The frontend communicates with the backend using the Fetch API.

### Backend — Express.js

The `server/server.js` file provides four main API endpoints:

- GET `/api/tasks` — retrieves tasks.
- POST `/api/tasks` — creates a task.
- PUT `/api/tasks/:id` — updates a task.
- DELETE `/api/tasks/:id` — deletes a task.

### Database — SQLite

The `server/db.js` file manages database operations using `sql.js`.

Tasks are stored in a SQLite database. Changes are written to `server/data/tasks.db`, allowing the data to remain available after refreshing the application.

## 3. Functionality Testing

I tested the application and made the following observations:

- Creating and deleting tasks worked.
- Marking tasks as completed worked.
- Filtering tasks by status worked.
- Editing task titles worked.
- Tasks remained saved after refreshing the browser.
- The application allowed empty task titles.
- Due dates were optional and displayed as blank when not provided.
- The editing interface did not allow changes to task priorities or due dates.

## 4. Improvements I Would Make

### Improvement 1: Validate Task Titles

The application currently accepts tasks with empty titles.

I would add frontend and backend validation to prevent empty or whitespace-only task titles.

**Why:** This would improve data quality and prevent users from accidentally creating meaningless tasks.

### Improvement 2: Improve Task Editing

The current editing interface only allows task titles to be changed.

I would extend the edit form to support changing task priority and due date.

**Why:** Users should be able to update task details without deleting and recreating tasks.

### Improvement 3: Improve API Error Handling

The frontend does not explicitly handle failed API requests, and the backend lacks clear validation and error responses.

I would add appropriate error handling, HTTP status codes, and user-friendly feedback messages.

**Why:** This would make the application more reliable and help users understand when operations fail.

## 5. AI-Assisted Exploration

**AI tool:** ChatGPT

I used ChatGPT to support my exploration of the application by sharing the source code from `client/src/App.tsx` and `server/server.js`.

The code-sharing prompts were part of an ongoing conversation about understanding the starter application.

My exploration focused on:

- Understanding how React state works.
- Explaining the API requests.
- Understanding how the frontend communicates with the backend.
- Investigating the issues I discovered during testing.
- Identifying potential improvements.

I compared the explanations against the actual source code and application behaviour instead of relying only on AI-generated answers.

## 6. Something AI Missed

During the initial frontend explanation, AI described how the application fetched data from the backend but did not establish the exact database persistence mechanism.

I checked `server/db.js` to understand this further.

The file showed that the project uses `sql.js`, which operates with an in-memory SQLite database and saves changes to a database file.

This helped me understand why tasks remained available after refreshing the page.

**Lesson learned:** AI explanations can be helpful but incomplete. Checking the source code is necessary to understand the full implementation.

## 7. Reflection

This assessment helped me understand how the frontend, backend, and database work together in a full-stack application.

I also learned the importance of testing an application before reviewing its code.

By testing the task tracker myself, I was able to discover limitations and then investigate their causes in the source code.

My biggest takeaway is that AI should support my understanding and decision-making as a software engineer, not replace them.