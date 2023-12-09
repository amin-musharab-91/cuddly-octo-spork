### Task Manager App

## This project is made using React, Express, NodeJs, Mongoose, and Docker.

- Frontend uses React, Tailwind Css
- Backend is made using MondoDB, Express and Mongoose
- Nginx is used to orchestrate backend with frontend using the /api route inside the same container

In order to run the project simple run the following command:

`docker-compose up --build`

This will run the application inside the docker container after pulling the config image and installing all the dependencies.

## How to Run Locally

Follow these instructions to run the application locally:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/task-management-app.git
   ```

Create Enviroment Variables

- cd backend
- create a .env file from .env.sample

- cd frontend
- create a .env file from .env.sample

Run following command
To run with Docker

```
docker-compose up --build
```

Tu Run without Docker, Open a new terminal and change your directory to backend and run `npm run dev`

```
cd task-management-app/backend
npm install
npm run dev
```

Open a new terminal and change your directory to frontend and run `npm start`

```
cd task-management-app/frontend
npm install
npm start
```

## Bonus Features

1. **Efficient Priority Handling:**
   - Implemented a solution for efficient handling of priority changes.
   - When the priority of a task is changed, the system doesn't impact other tasks in a massive way (e.g., updating 100 million records).
   - Leveraged priority columns for effective fetching of results without extensive updates.

### Implementation Overview

1. **Database Design:**

   - ODatabase schema incorporates a dedicated column for task priority.

2. **Update Priority Endpoint:**

   - I have implemented a specialized API endpoint (`PUT /api/tasks/:taskId/priority`) for updating the priority of a specific task.

3. **Fetching Priority Ranges:**

   - The application intelligently fetches tasks based on priority, utilizing the dedicated priority column efficiently.

4. **Consideration for Large Datasets:**
   - To address potential performance issues with large datasets, I have implemented pagination or limited the number of records returned in a single query.
