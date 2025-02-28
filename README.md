# google_sheets_clone

# Google Sheets Clone

This project is a web-based spreadsheet application designed to mimic the user interface and core functionalities of Google Sheets. Developed as part of **Assignment 1**, it focuses on replicating key spreadsheet features such as mathematical functions, data quality tools, data entry with validation, and an intuitive UI with drag-and-drop and resizing capabilities.

## Objective

The goal is to create a functional spreadsheet application that closely resembles Google Sheets, providing users with a familiar interface and essential tools for data manipulation, formatting, and visualization.

## Features

### 1. Spreadsheet Interface
- UI Design: Mimics Google Sheets with a gradient toolbar, formula bar, and a grid layout styled with Bootstrap and custom CSS.
- Drag Functionality: Supports dragging cell content or formulas to other cells, adjusting references dynamically (e.g., `A1` to `B2`).
- Cell Dependencies: Automatically updates cells with formulas (e.g., `=SUM(A1:A3)`) when referenced values change.
- Formatting: Includes bold, italic, font size, and color options via toolbar buttons.
- Row/Column Management: Allows adding/removing rows and columns, with column resizing via draggable resizers.

### 2. Mathematical Functions
- `SUM`: Calculates the sum of a range (e.g., `=SUM(A1:A3)`).
- `AVERAGE`: Computes the average of a range.
- `MAX`: Finds the maximum value in a range.
- `MIN`: Finds the minimum value in a range.
- `COUNT`: Counts numeric values in a range.

### 3. Data Quality Functions
- `TRIM`: Removes leading/trailing whitespace from all cells with a single button click.
- `UPPER`: Converts all non-formula cell content to uppercase.
- `LOWER`: Converts all non-formula cell content to lowercase.
- `REMOVE_DUPLICATES`: Deletes duplicate rows based on all cell values.
- `FIND_AND_REPLACE`: Replaces specified text across all non-formula cells.

### 4. Data Entry and Validation
- Supports input of numbers, text, and dates.
- Validates input: Non-formula cells turn red (`invalid` class) if they contain non-numeric/date values, ensuring data integrity.

### 5. Testing
- Users can input data or formulas and see real-time updates in dependent cells.
- Results are displayed directly in the grid or via the formula bar.

### Bonus Features
- Save/Load: Stores spreadsheet data (values and styles) in `localStorage` for persistence across sessions.
- Data Visualization: Generates a bar chart for a selected column using Chart.js.
- Sorting/Filtering: Sorts a column (numeric or text) and filters rows by value.
- Dynamic Formula Adjustment: Adjusts cell references when dragging formulas (relative referencing).

## Tech Stack

- Frontend: 
  - HTML: Structures the spreadsheet grid and toolbar.
  - CSS*: Custom styling with Bootstrap 5.3 for layout and responsiveness, plus a gradient-themed design.
  - JavaScript: Core logic for interactivity, formula evaluation, and event handling.
- Libraries: 
  - Bootstrap 5.3: Provides responsive design and button styling.
  - jQuery 3.6: Simplifies DOM manipulation (though minimally used).
  - Chart.js 4.4.1: Renders bar charts for data visualization.
- Storage: `localStorage` for saving/loading spreadsheet state.
- Version Control: Git with GitHub for repository management.

### Why This Stack?
- Bootstrap: Speeds up UI development with pre-built components and ensures mobile responsiveness.
- Vanilla JS: Chosen over frameworks like React for simplicity and direct DOM control, aligning with a lightweight, standalone app.
- Chart.js: Lightweight and easy to integrate for basic charting needs.
- localStorage: Simple solution for persistence without requiring a backend.

## Data Structures

- Map (`dependencies`): 
  - Stores cell formulas (e.g., `A1: "=SUM(B1:B3)"`) to track dependencies and enable real-time updates.
  - Chosen for O(1) key-value access and easy iteration.
- DOM as Data Store: 
  - Cell values and styles are stored directly in `<input>` elements within the table, leveraging the DOM as a live data structure.
  - Simplifies rendering and immediate UI updates.
- Array: 
  - Used temporarily for operations like sorting, filtering, and chart data extraction (e.g., collecting values from a column).
  - Efficient for linear data processing.

### Why These Structures?
- Map: Ideal for tracking formula dependencies with fast lookups and updates, avoiding complex graph implementations for this scale.
- DOM: Reduces memory overhead by using the UI as the primary data source, suitable for a client-side app.
- Array: Versatile for one-off computations and Chart.js integration.

## Installation and Setup

1. Clone the Repository:
   ```bash
   git clone https://github.com/GollaVamshi/google_sheets_clone
   cd google_sheets_clone

