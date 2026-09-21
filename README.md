TaskFlow — Student Project Manager

TaskFlow is a responsive frontend web application for organizing university assignments, project deadlines, work, and personal tasks. It was developed as a Full Stack Development internship project using only HTML5, CSS3, and vanilla JavaScript.

Features

Add tasks with a title, category, priority, and deadline

Mark tasks as completed or pending

Delete tasks with confirmation

Filter tasks by all, pending, or completed status

View live totals and completion progress

Save tasks automatically with browser Local Storage

Switch between light and dark themes

Responsive mobile navigation

Accessible semantic HTML structure

Responsive layouts using CSS Grid, Flexbox, and media queries

Technologies Used

HTML5 — Semantic page structure

CSS3 — Styling, responsive layouts, animations, and themes

JavaScript — Task management and interface interactions

Local Storage — Saves tasks and theme preferences in the browser

Google Fonts — DM Sans and Manrope typography

No JavaScript framework, CSS framework, database, or backend is required.

Project Structure

taskflow/
├── index.html
├── style.css
├── script.js
└── README.md

File Responsibilities

File

Purpose

index.html

Contains the semantic structure, dashboard, task form, navigation, and page content.

style.css

Controls the visual design, layout, themes, responsive breakpoints, and animations.

script.js

Handles task creation, deletion, filtering, completion, statistics, themes, and Local Storage.

README.md

Explains the project, its code structure, and how to run it.

How to Run the Project

Option 1: Open Directly

Download or clone the repository.

Make sure all three project files are in the same folder.

Double-click index.html.

The website will open in your default browser.

Option 2: Use Visual Studio Code Live Server

Open the project folder in Visual Studio Code.

Install the Live Server extension by Ritwick Dey.

Right-click index.html.

Select Open with Live Server.

The project should open at an address similar to:

http://127.0.0.1:5500/index.html

How the Application Works

1. Initial Tasks

script.js includes a defaultTasks array containing sample tasks. These tasks are shown only when the application has no previously saved task data.

const defaultTasks = [
  {
    id: 1,
    title: "Complete responsive frontend assignment",
    category: "University",
    priority: "high",
    date: getFutureDate(2),
    completed: false
  }
];

2. Loading and Saving Tasks

The application stores tasks in the browser using Local Storage.

function saveTasks() {
  localStorage.setItem("taskflow-tasks", JSON.stringify(tasks));
}

When the page opens, loadTasks() reads the saved JSON data and converts it back into a JavaScript array.

3. Rendering Tasks

The renderTasks() function:

Clears the current task list.

Applies the selected filter.

Creates an HTML element for each task.

Adds checkbox and delete-button events.

Updates the dashboard statistics.

4. Adding a Task

When the task form is submitted, addTask() creates an object containing:

A unique ID

Task title

Category

Priority

Deadline

Completion status

The task is inserted into the array, saved in Local Storage, and displayed immediately.

5. Completing and Deleting Tasks

toggleTask() changes a task's completed value between true and false. deleteTask() removes a selected task after asking the user for confirmation.

6. Task Filtering

The filter buttons update currentFilter with one of these values:

all
pending
completed

The task list is then re-rendered to show only matching tasks.

7. Progress Calculation

The completion percentage is calculated with:

const progress =
  total === 0 ? 0 : Math.round((completed / total) * 100);

This percentage updates the progress bar, circular progress indicator, statistics, and progress message.

8. Theme Switching

The theme button adds or removes the dark-theme class from the page. The selected theme is stored in Local Storage and restored when the page is opened again.

Responsive Design

The website uses a mobile-first-friendly responsive structure:

Large screens show multi-column dashboard layouts.

Tablet screens reduce the number of columns.

Mobile screens use single-column layouts.

Navigation changes into a menu button on smaller screens.

Buttons and form controls remain touch-friendly.

The main responsive breakpoints are:

@media (max-width: 900px) { }
@media (max-width: 768px) { }
@media (max-width: 520px) { }

Local Storage Keys

Key

Stored Data

taskflow-tasks

The complete tasks array

taskflow-theme

The selected light or dark theme

To reset the application, open the browser developer tools, go to Application → Local Storage, and delete these keys. You can also clear the website's browser data.

Testing Checklist

Add a new task

Complete and uncomplete a task

Delete a task

Test all task filters

Refresh and verify that tasks remain saved

Switch between light and dark themes

Test the navigation links

Test the website on desktop and mobile screen sizes

Confirm that no horizontal scrolling appears

Possible Future Improvements

Task editing

Search functionality

User accounts

Backend API integration

Database storage

Drag-and-drop task ordering

Email deadline reminders

Multiple task boards

Author

Muhammad Ashir

GitHub: M-Ashir

LinkedIn: Muhammad Ashir

License

This project is available for educational and portfolio use.
