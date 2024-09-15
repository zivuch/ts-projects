### Building a To-Do List Application with React, TypeScript, and Redux Toolkit

**What You Will Learn:**

- **State Management**: Leveraging Redux Toolkit for efficient and scalable state handling.
- **Component Architecture**: Structuring React components for reusability and maintainability.
- **TypeScript Integration**: Enhancing code reliability and developer experience with static typing.
- **Custom Hooks**: Creating reusable hooks to interact with the Redux store seamlessly.

**Time Needed:** 60 minutes

**Description:**
In this exercise, you'll create a robust To-Do List application using **React**, **TypeScript**, and **Redux Toolkit**. The application will allow users to add, remove, check/uncheck, and filter tasks.
By following these instructions, you'll gain hands-on experience with state management, component architecture, and TypeScript integration in a React application.

---

## Table of Contents

1. [Project Setup](#project-setup)
2. [Project Structure](#project-structure)
3. [Creating the Model](#creating-the-model)
4. [Setting Up Redux Store](#setting-up-redux-store)
5. [Building the Task Features](#building-the-task-features)
6. [Creating the Main Application Components](#creating-the-main-application-components)
7. [Styling the Application](#styling-the-application)


## Project Setup

1. **Initialize a New React Project with TypeScript**

   Create React App or Vite with TypeScript support.

2. **Install Required Dependencies**

   You'll need to install **Redux Toolkit** and **React-Redux** for state management.

   ```bash
   npm install @reduxjs/toolkit react-redux
   ```

## Project Structure

Organize your project files to maintain clarity and scalability:

Suggested Structure:

```
- src/
   - app/
      - store.ts
   - features/
      - tasks/
       * componenets and redux files *
   - model/
     - ListItem.ts
   - main.tsx
   - App.tsx
```

---

## Creating the Model

1. **Define the Task Model (`ListItem.ts`)**

   In the `src/model/` directory, create a `ListItem.ts` file. This model represents the structure of a task in your to-do list.

   - **Purpose**: Encapsulate task properties and provide methods for serialization/deserialization if needed.

   - **Key Components**:
     - **Interface**: Defines the shape of a task object.
     - **Class**: Implements the interface and includes getter/setter methods.

   **Steps**:

   - Create `ListItem.ts` in `src/model/`.
   - Define an `Item` interface with `id`, `item`, and `checked` properties.
   - Implement a `ListItem` class that adheres to the `Item` interface.

---

## Setting Up Redux Store

1. **Configure the Redux Store (`store.ts`)**

   In the `src/app/` directory, create a `store.ts` file to set up your Redux store.

   - **Purpose**: Combine reducers and configure the store using Redux Toolkit's `configureStore`.

   - **Key Concepts**:
     - **Reducers**: Functions that specify how the application's state changes in response to actions.
     - **CombineReducers**: Utility to combine multiple reducers into a single reducing function.

   **Steps**:

   - Create `store.ts` in `src/app/`.
   - Import `configureStore` and `combineReducers` from Redux Toolkit.
   - Import the tasks reducer from the tasks feature.
   - Combine reducers if you plan to add more features in the future.
   - Configure and export the store.
   - Define and export TypeScript types for `RootState` and `AppDispatch` for use throughout the app.

---

## Building the Task Features

1. **State Management for Tasks **

   Inside `src/features/tasks/`, create a `slice` file to manage the tasks' state.

   - **Purpose**: Define the initial state, reducers, and actions for tasks using Redux Toolkit's `createSlice`.

   - **Key Concepts**:
     - **Slice**: A collection of Redux reducer logic and actions for a single feature.
     - **Reducers**: Handle state changes based on dispatched actions.

   **Steps**:

   - Define an enumeration for filter states (All, Active, Completed).
   - Define the initial state with an empty tasks array and a default filter.
   - Use `createSlice` to define reducers for adding, removing, checking, clearing tasks, and setting the filter.
   - Export actions and the reducer.

2. **Creating Selectors **

   Create `selectors` to define selectors for accessing specific parts of the state.

   - **Purpose**: Abstract the logic for retrieving and deriving data from the store.

   - **Key Concepts**:
     - **Selectors**: Functions that extract specific pieces of state.
     - **createSelector**: Reselect function to create memoized selectors.

   **Steps**:

   - Import `createSelector` from Redux Toolkit.
   - Define selectors for retrieving all tasks, tasks by ID, and the current filter.
   - Create a selector to filter tasks based on the active filter state.

3. **Creating Task Hooks**

   Create `hooks` to define hooks that dispatch actions and select state.

   - **Purpose**: Encapsulate logic for interacting with the Redux store, making it reusable across components.

   - **Key Concepts**:
     - **useCallback**: Optimize performance by memoizing functions.
     - **Custom Hooks**: Enhance code reusability and readability.

   **Steps**:

   - Import necessary hooks and actions.
   - Define hooks for adding, removing, checking, clearing tasks, and setting the filter.
   - Use `useCallback` to memoize these hooks.

4. **Creating Task Components**

   Create the following components:

   - **TaskItem**

     - **Purpose**: Render individual tasks with the ability to check/uncheck and remove them.
     - **Key Concepts**: Component props, event handling.

   - **TaskRemove**

     - **Purpose**: Render a remove button for a task.
     - **Key Concepts**: Event handling, component abstraction.

   - **Tasks**

     - **Purpose**: Serve as the main container for all task-related components.
     - **Key Concepts**: Component composition.

   - **TasksFilterButtons**

     - **Purpose**: Render buttons to filter tasks based on their completion status.
     - **Key Concepts**: Enumerations, event handling.

   - **TasksInput**

     - **Purpose**: Provide an input field and button to add new tasks.
     - **Key Concepts**: Controlled components, form handling.

   - **TasksList**

     - **Purpose**: Display a list of all tasks.
     - **Key Concepts**: Mapping over arrays to render lists.

   - **TasksTitle**
     - **Purpose**: Display the total number of tasks.
     - **Key Concepts**: Component props.

   **Steps for Each Component**:

   - Create the respective `.tsx` file in `src/features/tasks/`.
   - Import necessary dependencies and hooks.
   - Define the component structure and logic based on its purpose.
   - Export the component for use in other parts of the application.

---

## Creating the Main Application Components

1. **Main Application Component (`App.tsx`)**

   In `src/`, create `App.tsx` to serve as the root component of your application.

   - **Purpose**: Compose the main features of the app.

   - **Key Concepts**:
     - **Component Composition**: Building complex UIs from smaller components.

   **Steps**:

   - Import the `Tasks` component.
   - Render the `Tasks` component within the `App` component.

2. **Entry Point (`main.tsx`)**

   In `src/`, create or modify `main.tsx` to render the `App` component within the Redux `Provider`.

   - **Purpose**: Initialize the React application and integrate Redux for state management.

   - **Key Concepts**:
     - **ReactDOM**: Renders React components to the DOM.
     - **Provider**: Makes the Redux store available to the rest of the app.

---

## Styling the Application

1. **Create CSS Styles**

   Create a `css` file to style your components.

   - **Purpose**: Enhance the visual appearance of the application.

   - **Key Concepts**:
     - **CSS Classes**: Define styles for different states (e.g., completed tasks).
     - **Component-specific Styling**: Scoped styles for better maintainability.
