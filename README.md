# Flashcard Web App

A web application that allows users to create, manage, and study flashcards using the SM-2 algorithm, a spaced repetition system designed to help users optimize learning efficiency. The site includes user authentication, flashcard set management, and a study mode for reviewing flashcards based on the SM-2 algorithm.

## Features

### User Authentication

- Login Page: Users can log in to access their saved flashcards and study progress.
- Register Page: New users can create an account to access the full functionality of the app.

### Flashcard Management

- Sets Page: Users can create and view flashcard sets.
- Flashcards Page: Users can add, edit, and delete flashcards within each set.

### Study Mode

- Study Page: The study mode leverages the SM-2 algorithm to schedule flashcard reviews based on a spaced repetition technique, helping users remember information more effectively.

## Technologies Used

- **Frontend**: React, TypeScript, CSS
- **Backend**: Golang, PostgreSQL
- **User Authentication**: JWT-based authentication
- **Docker**: For containerized deployment

## Installation

1. **Clone the repository**  
   ```bash
   git clone --recurse-submodules git@github.com:NikenCarolina/flashcard-app.git
   cd flashcard-app
   ```

2. **Install frontend dependencies**  
   ```bash
   cd frontend
   npm install
   ```

3. **Set up the backend**  
   Ensure you have Go modules initialized in the `backend` folder and set up environment variables for PostgreSQL and JWT.
   ```bash
   cd backend
   go mod tidy
   ```

4. **Configure PostgreSQL Database**  
   Set up a PostgreSQL database and add your database credentials to the environment variables. 
   You can set up database tables by running **./backend/database/migration/000001_init_mg.up.sql**. 

   Or set up database tables with [migrate CLI](https://github.com/golang-migrate/migrate) (optional) 
   Run make migrateup to migrate with provided Makefile. 
   ```bash
   cd backend
   make migrateup 
   ```

5. **Run the application**  
   - **Frontend**  
     ```bash
     cd frontend
     npm run dev 
     ```
   - **Backend**  
     ```bash
     cd backend
     go run ./cmd/app/main.go
     ```

6. **Docker Setup (Optional)**  
   Use Docker Compose to start both services in containers.  
   ```bash
   docker compose up
   ```

## Usage

1. **Register** for a new account or **login** if you already have one.
2. Navigate to the **Sets Page** to create new flashcard sets.
3. Within a set, go to the **Flashcards Page** to add, edit, or delete flashcards.
4. Start a study session from the **Study Page**, where the SM-2 algorithm will determine the optimal intervals for reviewing each card based on your prior performance.

## Documentations



## Planned improvements and features:

- **404 Page**: Add a custom 404 error page for improved navigation and user experience.
- **Memorized Card Tabs**: Include a tab in the study section to track flashcards that have been memorized or mastered.
- **Testing**: Implement unit and integration tests for both frontend and backend, covering user authentication, flashcard CRUD operations, and the SM-2 scheduling logic.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

