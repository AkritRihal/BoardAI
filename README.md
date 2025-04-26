# BoardAI

BoardAI is a full-stack application designed to analyze and solve mathematical problems from images using AI. It consists of a backend API server built with FastAPI and a frontend web application built with React, Vite, and Mantine UI.

---

## Project Overview

- **Backend:** A FastAPI server that exposes an endpoint to process images containing mathematical expressions, equations, or graphical math problems. It uses Google Generative AI to analyze and solve these problems.
- **Frontend:** A React-based web application that provides a user interface to upload images and interact with the backend API.

---

## Backend

### Overview

The backend is implemented using FastAPI and exposes a `/calculate` endpoint that accepts images encoded in base64 format. It processes the images using a Google Generative AI model to solve mathematical problems or interpret graphical math content.

### Key Components

- `main.py`: FastAPI app setup with CORS middleware and route registration.
- `constants.py`: Configuration constants including server URL, port, environment, and API keys.
- `apps/calculator/route.py`: Defines the API route for image processing.
- `apps/calculator/utils.py`: Contains the logic to interact with Google Generative AI for analyzing images.

### Environment Variables

- `GEMINI_API_KEY`: API key for Google Generative AI, loaded from environment variables.

### Running the Backend

1. Install dependencies (preferably in a virtual environment):

   ```bash
   pip install -r BoardAI-be/requirements.txt
   ```

2. Set environment variables, especially `GEMINI_API_KEY`.

3. Run the backend server:

   ```bash
   uvicorn BoardAI-be.main:app --host localhost --port 8900 --reload
   ```

---

## Frontend

### Overview

The frontend is a React application built with Vite. It uses Mantine UI for styling and React Router for navigation. The app allows users to upload images and view the results returned by the backend.

### Key Components

- `src/App.tsx`: Main app component setting up routing and UI provider.
- `src/screens/home/index.tsx`: Home screen component (entry point for the UI).
- `package.json`: Contains frontend dependencies and scripts.

### Running the Frontend

1. Navigate to the frontend directory:

   ```bash
   cd BoardAI-fe
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the development server:

   ```bash
   npm run dev
   ```

4. Open the app in your browser at the URL provided by Vite (usually `http://localhost:5173`).

---

## API Endpoint

- `POST /calculate`: Accepts an image with mathematical content encoded in base64 and a dictionary of variables. Returns the solved expressions or interpreted results.

---

## Additional Notes

- The backend server runs on `localhost:8900` by default.
- The frontend communicates with the backend API to process images.
- Ensure the `GEMINI_API_KEY` is set correctly for the backend to function.
- The frontend uses TailwindCSS and Mantine UI for styling.

---

## License

This project is licensed under the terms of the MIT License.
