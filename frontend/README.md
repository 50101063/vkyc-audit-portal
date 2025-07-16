# V-KYC Recording Retrieval Frontend Application

This folder contains the frontend code for the V-KYC Recording Retrieval Portal. The application is built using HTML, CSS, and JavaScript, designed to integrate seamlessly with the backend API to provide search, filtering, and download functionalities for V-KYC recordings.

## Setup and Execution Instructions

This is a static web application that can be run directly in a web browser.

### Prerequisites

*   A modern web browser (e.g., Chrome, Firefox, Edge, Safari).
*   A running backend API service (as specified in the Solution Architect's design) to fetch data and recordings. Ensure the backend is accessible from where you are serving this frontend.

### Project Structure

```
frontend/
├── index.html       # The main HTML file for the application.
├── style.css        # Contains all the CSS for styling the application.
├── script.js        # Contains the core JavaScript logic, including API calls and UI manipulation.
└── README.md        # This file.
```

### Running the Application

Since this is a static HTML/CSS/JS application, you can run it in a few simple ways:

#### Option 1: Open Directly in Browser (Simplest)

1.  Navigate to the `frontend/` directory on your local machine.
2.  Double-click `index.html`.
    *   **Note**: For security reasons, browsers might restrict certain functionalities (like making API calls to a different domain or local file system access) when opening `index.html` directly using the `file://` protocol. If you encounter CORS issues, use Option 2 or 3.

#### Option 2: Using a Simple Local Web Server (Recommended for Development)

This is the most reliable way to run the application locally and avoid CORS issues.

1.  **Install Python (if not already installed)**: Python comes with a built-in simple HTTP server.
    *   Download from [python.org](https://www.python.org/downloads/).
2.  **Navigate to the `frontend/` directory** in your terminal or command prompt.
    ```bash
    cd frontend/
    ```
3.  **Start the server**:
    *   For Python 3.x:
        ```bash
        python -m http.server 8000
        ```
    *   For Python 2.x:
        ```bash
        python -m SimpleHTTPServer 8000
        ```
4.  Open your web browser and go to `http://localhost:8000`.

#### Option 3: Using Node.js `serve` package

If you have Node.js installed, you can use the `serve` package.

1.  **Install `serve` globally**:
    ```bash
    npm install -g serve
    ```
2.  **Navigate to the `frontend/` directory**:
    ```bash
    cd frontend/
    ```
3.  **Start the server**:
    ```bash
    serve .
    ```
4.  Open your web browser and go to the address provided by `serve` (usually `http://localhost:3000`).

### Integration with Backend API

The `script.js` file will contain JavaScript code responsible for making API calls to the backend service.

**Important**: You will need to configure the backend API endpoint in `script.js` (or through an environment variable if using a build tool, but for this simple setup, direct modification is expected).

Example of a placeholder API endpoint in `script.js`:
```javascript
const API_BASE_URL = 'http://localhost:8080/api/v1'; // **UPDATE THIS TO YOUR ACTUAL BACKEND URL**
```
Ensure this `API_BASE_URL` matches the deployed backend service URL.

### Features

*   **Dashboard View**: Displays a table of V-KYC records.
*   **Search by LAN**: Input field to search for specific LAN IDs.
*   **Filter/Sort by Date, Month, Year**: Functionality to filter and sort records.
*   **Bulk Upload**: Option to upload CSV/TXT files containing up to 50 LAN IDs for bulk search.
*   **Paginated Results**: Displays 10 records per page.
*   **Download Individual Recording**: Click on a LAN ID in the table to download the corresponding video.
*   **Download All (Bulk)**: Button to download all results from a bulk search (up to 50 records) as a ZIP file.

### Development Notes

*   **HTML Structure**: `index.html` provides the basic layout and elements for the UI.
*   **CSS Styling**: `style.css` provides responsive and clean styling for the portal.
*   **JavaScript Logic**: `script.js` handles all dynamic interactions, data fetching, and UI updates. It will include functions for:
    *   Handling form submissions (search, file upload).
    *   Fetching data from the backend.
    *   Rendering table rows and pagination.
    *   Handling download requests.
    *   Client-side validation for file uploads.

---
