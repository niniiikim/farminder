# farminder
game-themed to-do list with React, TailwindCSS, Firebase

## 🌾 Interactive Stardew Valley Seasonal Guide

This application features a unique **dual-panel interface** designed to streamline gameplay planning.

### 🎮 Feature Overview
* **Seasonal Dashboard (Right Panel):** A dynamic guide that displays curated game data for each season (Spring, Summer, Fall, Winter).
* **One-Click Task Generation:** Users can click on any crop, event, or tip in the guide to instantly convert it into a task in their To-Do list.
    * *Example:* Clicking on "Blueberries" in the Summer tab automatically adds "Buy Blueberry Seeds" to the active task list.
* **Context-Aware Tips:** Displays building recommendations and main seasonal goals to keep the player on track.

### ⚙️ How It Works (Under the Hood)
The application utilizes a **Database-First architecture** to sync the UI components:

1.  **Data Source:** Seasonal data is pulled from a local structured object (`stardewData.js`) acting as an internal API.
2.  **Event Trigger:** When a user selects an item from the guide, the app triggers an asynchronous function `addQuickTodo()`.
3.  **Firebase Integration:** Instead of updating the local state directly, this function sends a `POST` request to the **Firestore Database**.
4.  **Real-Time Sync:** A Firebase `onSnapshot` listener detects the database change and automatically pushes the new task to the specific client (and any other connected devices) in real-time, ensuring the UI is always in sync with the backend.

## Preview
<img width="1920" height="943" alt="image" src="https://github.com/user-attachments/assets/d9de256b-3d3d-4d20-ab71-d30475cfd79c" />

