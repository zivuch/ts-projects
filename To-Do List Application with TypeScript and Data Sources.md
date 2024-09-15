### To-Do List Application with TypeScript and Data Sources

**What You Will Learn:**

- **TypeScript Basics**: Understanding TypeScript classes, interfaces, and type annotations.
- **Data Management**: Handling data with TypeScript classes and storing data in localStorage.
- **DOM Manipulation**: Creating and updating DOM elements dynamically based on application state.
- **Event Handling**: Setting up and managing events for user interactions.
- **Project Structure**: Organizing a TypeScript project with a clear modular structure using Vite.

**Time Needed:** 90 minutes

**Description:**
In this exercise, you'll build a simple to-do list application using **JavaScript with TypeScript**. This project will involve creating a few TypeScript classes and organizing them into a modular structure using **Vite** as your development tool.

#### **Project Overview**:

You'll work with four key files:

- `ListItem.ts`: Manages individual to-do items.
- `FullList.ts`: Handles the complete list of to-do items and operations on it.
- `ListTemplate.ts`: Manages rendering the list in the DOM.
- `main.ts`: Bootstraps the application and connects all components.

---

### 1. **Setting Up the Project with Vite**

1. **Install Vite**:
   If you haven’t already, install Vite and set up a new project. Run the following commands in your terminal:

   ```bash
   npm create vite@latest
   ```

   - Choose a project name when prompted.
   - Select **vanilla-ts** (Vanilla TypeScript) for the TypeScript template.

2. **Navigate to Your Project**:
   Move into the project directory and install dependencies:

   ```bash
   cd your-project-name
   npm install
   ```

3. **Install UUID Library**:
   You’ll use the `uuid` library to generate unique IDs for the to-do items:

   ```bash
   npm install uuid
   ```

4. **Folder Structure**:
   Inside the `src/` folder, create two folders: `model` and `templates`. These will contain your TypeScript files:
   ```
   - src/
      - model/
         - ListItem.ts
         - FullList.ts
      - templates/
         - ListTemplate.ts
      - main.ts
   ```

---

### 2. **Creating the Model Files**

#### 2.1. **Creating `ListItem.ts`**

- In the `src/model/` folder, create a `ListItem.ts` file.
- This file will define a class that represents each individual item in the to-do list. Each to-do item will have three properties:
  - **id**: A unique identifier for the item.
  - **item**: The text or description of the to-do item.
  - **checked**: A boolean value that indicates whether the item has been completed or not.
- You'll need to:
  - Create a TypeScript interface to represent the item structure.
  - Implement a class that manages the item properties with getter and setter methods.

#### 2.2. **Creating `FullList.ts`**

- In the `src/model/` folder, create a `FullList.ts` file.
- This file will define a class that manages the full list of to-do items. The class should:
  - Maintain an array of items.
  - Implement methods to:
    - Load the list from `localStorage`.
    - Save the list to `localStorage`.
    - Add and remove items from the list.
    - Clear the entire list.
- Use the `ListItem` class from the `ListItem.ts` file to represent each item.

---

### 3. **Creating the Template File**

#### 3.1. **Creating `ListTemplate.ts`**

- In the `src/templates/` folder, create a `ListTemplate.ts` file.
- This file will define a class responsible for rendering the list of to-do items in the DOM. You'll:

  - Reference the HTML `<ul>` element where the list will be displayed.
  - Create methods to:
    - Render the list of to-do items dynamically, creating new `<li>` elements for each item.
    - Handle interactions like checking off items and removing them from the list.

  Each list item should have:

  - A checkbox to mark the item as completed.
  - A label to display the item text.
  - A delete button to remove the item.

---

### 4. **Creating the Main Application File**

#### 4.1. **Creating `main.ts`**

- In the `src/` folder, create a `main.ts` file.
- This file will:
  - Initialize the to-do list application when the page loads.
  - Use the `FullList` and `ListTemplate` classes to manage the list and render it in the DOM.
  - Set up event listeners for:
    - Submitting the form to add new to-do items.
    - A button to clear all items from the list.

---

### 5. **Setting Up the HTML File**

1. **Create the HTML Structure**:
   Ensure your HTML file has the following elements to interact with:

   - An input form where users can add new to-do items.
   - A `<ul>` element to display the list items.
   - A button to clear all items from the list.

   Here's a basic example of what the HTML might look like:

   ```html
   <form id="itemEntryForm">
     <input type="text" id="newItem" placeholder="Enter new item..." />
     <button type="submit">Add Item</button>
   </form>

   <ul id="listItems"></ul>

   <button id="clearItemsButton">Clear All</button>
   ```

---

### 6. **Running the Project**

1. **Start the Vite Development Server**:
   Once everything is set up, start the Vite development server:

   ```bash
   npm run dev
   ```

   Vite will provide a URL (typically `http://localhost:3000/`) where you can view the running application.

2. **Testing the Application**:
   - Test adding items to the list by typing text into the input field and clicking "Add Item."
   - Check items off by clicking the checkbox next to each one.
   - Remove items by clicking the delete button (`X`) next to them.
   - Clear the entire list by clicking the "Clear All" button.

---

### 7. **Optional Enhancements**

1. **Styling**:
   Add some basic CSS to improve the look and feel of the application.

---
