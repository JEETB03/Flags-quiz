

# Flag Quiz Application

This is a simple Node.js web application that quizzes users on country flags. The application fetches flag data from a PostgreSQL database and presents random flags to the user, who must correctly identify the country.

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Database Setup](#database-setup)
- [Running the Application](#running-the-application)
- [Application Structure](#application-structure)
- [Usage](#usage)
- [Contributing](#contributing)


## Features

- Displays a random flag and prompts the user to name the country.
- Tracks the total number of correct answers.
- Provides immediate feedback on whether the user's answer was correct or incorrect.
- User can restart the quiz after an incorrect answer.

## Technologies Used

- **Node.js**: JavaScript runtime used for building the backend.
- **Express.js**: Web framework for Node.js.
- **PostgreSQL**: Relational database for storing flag data.
- **EJS**: Embedded JavaScript templating for rendering HTML views.
- **Body-parser**: Middleware to parse incoming request bodies.
- **CSS**: Used for basic styling of the web pages.

## Installation

Follow these steps to set up the application locally:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/flag-quiz.git
   cd flag-quiz
   ```

2. **Install Node.js and npm:**
   - Make sure Node.js and npm are installed on your machine.
   - You can download Node.js from [here](https://nodejs.org/).

3. **Install dependencies:**
   ```bash
   npm install
   ```

4. **Create a `.env` file:**
   - In the root of your project directory, create a `.env` file to store your database credentials securely.
   ```bash
   touch .env
   ```
   - Add the following environment variables to the `.env` file:
   ```bash
   DATABASE_USER=your_postgres_user
   DATABASE_HOST=localhost
   DATABASE_NAME=World
   DATABASE_PASSWORD=your_postgres_password
   DATABASE_PORT=5432
   ```

## Database Setup

1. **Install PostgreSQL:**
   - Make sure PostgreSQL is installed on your machine.
   - You can download it from [here](https://www.postgresql.org/download/).

2. **Create the Database:**
   - Create a database named `World` and a table `flags`:
   ```sql
   CREATE DATABASE World;

   \c World

   CREATE TABLE flags (
     id SERIAL PRIMARY KEY,
     country VARCHAR(100) NOT NULL,
     flag VARCHAR(100) NOT NULL
   );

   INSERT INTO flags (country, flag) VALUES ('France', '🇫🇷'), ('United Kingdom', '🇬🇧'), ('United States', '🇺🇸');
   ```

3. **Configure Database Connection:**
   - The database connection is configured in your application using the `.env` file. Make sure the values match your local PostgreSQL setup.

## Running the Application

1. **Start the server:**
   ```bash
   npm start
   ```
   - The application will be available at `http://localhost:3000`.

2. **Visit the homepage:**
   - Open your web browser and navigate to `http://localhost:3000` to start the quiz.

## Application Structure

- **app.js**: The main entry point of the application where the server is initialized and routes are defined.
- **views/**: Contains EJS templates for rendering HTML.
  - **index.ejs**: The main page where the quiz is presented.
- **public/**: Contains static files like CSS, images, etc.
  - **styles/main.css**: The CSS file used for styling the application.
- **routes/**: Contains route handlers (if you later modularize your routes).

## Usage

- **Homepage**: The quiz starts immediately with a random flag.
- **Answer Submission**: Enter the country name and submit the answer.
- **Feedback**: The app provides immediate feedback on whether the answer was correct.
- **Restart**: If the answer is incorrect, you can restart the quiz.



## Contributing

If you'd like to contribute, please fork the repository and use a feature branch. Pull requests are warmly welcome.

1. **Fork the repository**.
2. **Create a new branch**: `git checkout -b feature-branch-name`.
3. **Commit your changes**: `git commit -m 'Add some feature'`.
4. **Push to the branch**: `git push origin feature-branch-name`.
5. **Create a pull request**.

