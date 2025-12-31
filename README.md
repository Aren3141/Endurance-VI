# Endurance VI - Official Team Platform

![Status](https://img.shields.io/badge/Status-Completed-success) ![Stack](https://img.shields.io/badge/Tech-Tailwind_HTML_Firebase-red) ![Context](https://img.shields.io/badge/Context-A_Level_CS_Project-blue)

### Project Overview
This repository hosts the official website and internal admin portal for **Endurance VI**, a STEM Racing (previously known as F1 in Schools) team. 

Developed using **Agile methodology** between **September and November 2025**, the project delivers:
1.  **Public Interface:** A responsive landing page to showcase the team and attract sponsors.
2.  **Admin System:** A secure dashboard for team communication, file management, and handling any enquiries.

---

### The Tech Stack
* **Frontend:** HTML5, JavaScript (ES6 Modules), Tailwind CSS.
* **Backend:** Google Firebase.
    * **Auth:** Email/Password gating for the Admin Panel.
    * **Firestore:** NoSQL database for contact messages and real-time chat if we need.
    * **Storage:** Cloud bucket for team file sharing (CAD designs).

---

### Agile Development Cycle (Sept - Nov 2024)
Development was broken into two-week sprints to allow for iterative testing.

* **Sprint 1: The Foundation** Focus on "Mobile First" responsive design using Tailwind utility classes like `md:flex` and `hidden`. Solved CSS animation challenges for the hero section car.

* **Sprint 2: Backend Integration** Connected Firebase and established the `contactMessages` collection. Implemented `async/await` syntax with `try/catch` blocks to handle any errors or network requests.

* **Sprint 3: The Admin System** Built the secure `admin.html` interface. Implemented a navigation sort of "aid" using `onAuthStateChanged` to redirect unauthorized users.

* **Sprint 4: Real-time Features** Added a live team chat using Firestore's `onSnapshot` listener and a file I/O system for uploading/downloading resources via Firebase Storage.

---

### Key Features

#### Public Site (`index.html`)
* **Performance:** Uses custom `IntersectionObserver` logic for scroll animations (`section-reveal`) instead of heavy external libraries.
* **Dynamic DOM:** "Ethos" cards are injected dynamically via JavaScript.

#### Admin Panel (`admin.html`)
* **Security:** Route protection ensures `currentUser` is valid before rendering content.
* **CRUD Operations:** Full capability to **C**reate (uploads), **R**ead (inbox), **U**pdate (live chat), and **D**elete (messages/files).

---

### Usage & Installation

**Note:** This project uses ES6 Modules and requires a local server (due to CORS).

1.  **Clone the Repo:**
    `git clone https://github.com/yourusername/endurance-vi.git`

2.  **Configuration:**
    Create a `firebase-config.js` file in the root and export your specific `firebaseConfig` object (API keys).

3.  **Run Locally:**
    Use the **Live Server** extension in VS Code or run `python3 -m http.server`.

4.  **Admin Access:**
    Navigate to `/login.html` and use authorized team credentials.

---

### Reflections
This project was a practical application of **state management** (tracking user sessions) and **asynchronous programming**. The biggest challenge was managing the execution order of file fetches to ensure the UI didn't render empty lists before the database connection was established.

*Built by the Team Leader of Endurance VI.*
