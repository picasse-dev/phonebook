# Phonebook

A full-stack Phonebook application built with React, Vite, Node.js, and Express. The application allows users to manage their contacts through a dynamic interface connected to a REST API.

This project was developed as part of my learning journey through the [Full Stack Open](https://fullstackopen.com/en/) course, covering fundamental concepts of modern web development, RESTful services, frontend-backend communication, and application deployment.

## Features

### Contact Management
- **Create contacts:** Add new contacts with a name and phone number.
- **Display contacts:** Retrieve and display all saved contacts.
- **Update contacts:** Modify existing contact information.
- **Delete contacts:** Remove contacts with a confirmation dialog.
- **Search contacts:** Filter contacts dynamically by name.

### Data Validation
- Prevent duplicate contact names (case-insensitive).
- Prevent assigning the same phone number to different contacts.
- Validate required fields before submitting data.
- Normalize phone numbers when comparing them, ignoring spaces and hyphens.
- Handle invalid requests and missing resources through appropriate HTTP status codes.

### User Feedback
- Success notifications for completed operations.
- Error notifications when server operations fail.
- Automatic removal of outdated contacts when a requested operation returns a 404 response.

## Technologies

### Frontend
- **React** – Component-based UI development.
- **Vite** – Development server and build tool.
- **Axios** – HTTP client for communicating with the REST API.
- **JavaScript (ES6+)** – Application logic and state management.

### Backend
- **Node.js** – JavaScript runtime environment.
- **Express** – REST API development and HTTP request handling.
- **Morgan** – HTTP request logging, including custom logging of request bodies.
- **CORS** – Cross-origin resource sharing configuration.

### Development Tools
- **JSON Server** – Mock REST API for development and experimentation.
- **REST Client** – Testing HTTP endpoints directly from VS Code.
- **Git & GitHub** – Version control and project management.

## Project Architecture

The application follows a client-server architecture:

```text
Frontend (React + Vite)
        |
        | Axios / HTTP Requests
        |
        v
Backend (Node.js + Express)
        |
        v
REST API (/api/persons)
        |
        v
In-memory data storage
```

The frontend is responsible for rendering the interface, managing application state, and interacting with the API.

The backend handles HTTP requests, validates incoming data, performs CRUD operations, and returns appropriate responses.

## REST API

The backend exposes the following endpoints:

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/persons` | Retrieve all contacts |
| GET | `/api/persons/info` | Retrieve phonebook information |
| GET | `/api/persons/:id` | Retrieve a specific contact |
| POST | `/api/persons` | Create a new contact |
| PUT | `/api/persons/:id` | Replace a contact's information |
| PATCH | `/api/persons/:id` | Partially update a contact |
| DELETE | `/api/persons/:id` | Delete a contact |

### HTTP Status Codes

The API uses HTTP status codes to communicate operation results:

- `200 OK` – Successful retrieval or update.
- `201 Created` – Contact successfully created.
- `204 No Content` – Contact successfully deleted.
- `400 Bad Request` – Invalid or missing input data.
- `404 Not Found` – Requested contact does not exist.
- `409 Conflict` – Contact name already exists.

## Installation and Local Development

### Prerequisites

- Node.js
- npm
- Git

### 1. Clone the repository

```bash
git clone YOUR_REPOSITORY_URL
cd YOUR_PROJECT_DIRECTORY
```

### 2. Install dependencies

Install the dependencies in both the frontend and backend directories:

```bash
npm install
```

### 3. Start the backend

From the backend directory:

```bash
npm install
npm start
```

The backend runs on port `3001` by default.

### 4. Start the frontend

From the frontend directory, open another terminal:

```bash
npm install
npm run dev
```

Vite starts the development server and provides a local URL in the terminal.

The frontend uses Vite's proxy configuration to forward `/api` requests to the local Express backend.

## Testing the API

The project includes REST Client request examples for testing the API directly from Visual Studio Code.

The `new_note.rest` file contains examples of:

- Retrieving all contacts.
- Retrieving individual contacts.
- Creating contacts.
- Updating contacts using PUT.
- Partially updating contacts using PATCH.
- Deleting contacts.

## Deployment

The application has been deployed using **Render**.

The production configuration includes:

- Dynamic port configuration through `process.env.PORT`.
- Serving the compiled React application using Express static middleware.
- Relative API URLs to support production deployment.
- Vite proxy configuration for local development.

## Current Status

<badge>Deployed</badge> <badge>Functional</badge>

The application is fully functional with its current in-memory data storage implementation.

A persistent database has not been integrated yet. Contact information is currently stored in a JavaScript array on the backend, meaning data is reset when the server restarts.

## Future Improvements

- [ ] Integrate a persistent database (MongoDB).
- [ ] Implement database-based CRUD operations.
- [ ] Improve backend error handling and validation.
- [ ] Add automated tests for API endpoints.
- [ ] Improve UI/UX and accessibility.
- [ ] Implement more robust phone number validation.

## Learning Objectives

Through this project, I practiced and consolidated concepts such as:

- React Hooks (`useState`, `useEffect`).
- Component composition and props.
- Controlled forms and event handling.
- Array methods (`map`, `filter`, `find`, `concat`).
- Asynchronous JavaScript and Promises.
- Axios and HTTP communication.
- REST API design and CRUD operations.
- Express middleware.
- Request validation and error handling.
- HTTP status codes.
- Frontend-backend integration.
- Production builds and deployment.

---

**Author:** [picasse-dev](https://github.com/picasse-dev)
