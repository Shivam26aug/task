# W3 villa assignment task manager web app

This repository contains two services:

1. *UI*: A Vite-based React frontend.
2. *Backend*: A Node.js server using Express and Prisma.

## Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v16+ recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [Docker](https://www.docker.com/) (if you want to run the database locally)

## Environment Variables

### Backend

Create a .env file in the backend directory with the following variables:

env
DATABASE_URL=postgresql://<username>:<password>@localhost:5432/<database>
JWT_SECRET=<your_jwt_secret>
PORT=4000


### UI

Create a .env file in the ui directory with the following variables:

env
VITE_API_URL=http://localhost:4000


## Installation

### Clone the Repository

bash
git clone <repo_url>
cd <repo_directory>


### Backend Setup

1. Navigate to the backend directory:
   bash
   cd backend
   

2. Install dependencies:
   bash
   npm install
   # or
   yarn install
   

3. Start the database (if using Docker):
   bash
   docker run --name postgres-db -e POSTGRES_USER=<username> -e POSTGRES_PASSWORD=<password> -e POSTGRES_DB=<database> -p 5432:5432 -d postgres
   

4. Run Prisma migrations:
   bash
   npx prisma migrate dev
   

5. Start the backend server:
   bash
   npm run dev
   # or
   yarn dev
   

### UI Setup

1. Navigate to the ui directory:
   bash
   cd ../ui
   

2. Install dependencies:
   bash
   npm install
   # or
   yarn install
   

3. Start the UI development server:
   bash
   npm run dev
   # or
   yarn dev
   

The UI should now be running on [http://localhost:5173](http://localhost:5173).

## Running Both Services

1. Open two terminal windows or tabs.
2. Start the backend in one terminal:
   bash
   cd backend
   npm run dev
   
3. Start the UI in the other terminal:
   bash
   cd ui
   npm run dev
   

Both services should now be running locally:
- Backend: [http://localhost:4000](http://localhost:4000)
- UI: [http://localhost:5173](http://localhost:5173)

## Notes

- Make sure the VITE_API_URL in the UI .env file matches the backend URL.
- Use npm run build in both directories to prepare the services for production.
