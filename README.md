# MatchCareer - Skills and Job Role Mapping System with personalized Dashboard

A Flask-based web application that helps users discover job opportunities based on their skills and track their career progress through an interactive dashboard.

## Features

- **Skill-to-Job Matching**: Enter your skills and find relevant job opportunities
- **Job-to-Skill Analysis**: Enter a job title and see required skills
- **Personal Dashboard**: Track your skill development progress
- **User Authentication**: Secure login and registration system
- **Database Storage**: SQLite by default for local and Render deployment, with optional `DATABASE_URL` override.

## Prerequisites

- Python 3.8+
- pip (Python package manager)

## Installation

1. **Clone the repository** (if applicable) or navigate to the project directory

2. **Database Setup**:
   - No local database server is required. The app uses SQLite by default and stores data in `matchcareer.db`.

3. **Install Python Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables**:
   Create a `.env` file with:
   ```env
   SECRET_KEY=your_secure_secret_key_here
   FLASK_ENV=development
   ```

   Optionally, you can set `DATABASE_URL` if you want to use a different SQLAlchemy-compatible database backend.
   ```env
   DATABASE_URL=sqlite:///matchcareer.db
   ```

## Running the Application

1. **Start the Flask application**:
   ```bash
   python app.py
   ```

2. **Access the application**:
   - Open your browser and go to `http://127.0.0.1:5000`
   - Register a new account or login
   - Start exploring job opportunities and tracking your progress!

## Usage

1. **Register/Login**: Create an account to access personalized features
2. **Find Skills**: Enter a job title to see required skills
3. **Find Jobs**: Enter your skills to discover matching job opportunities
4. **Dashboard**: Track your progress, mark skills as completed, and monitor your career goals

## Database Schema

The application uses the following main table:

- **User**: Stores user account information and progress data
  - id (Primary Key)
  - username (Unique)
  - email (Unique)
  - password_hash
  - created_at
  - todo_skills (JSON)
  - completed_skills (JSON)
  - target_jobs (JSON)

## Technologies Used

- **Backend**: Flask, SQLAlchemy, Flask-Login
- **Database**: MySQL (primary) or SQLite (automatic fallback)
- **Frontend**: HTML, CSS, JavaScript
- **ML**: scikit-learn, pandas for job-skill matching
- **Visualization**: Plotly for dashboard charts

## Troubleshooting

### MySQL Connection Issues
- Ensure MySQL server is running
- Check database credentials in `.env` file
- The app automatically falls back to SQLite if MySQL is unavailable

### sklearn Version Warnings
- Warnings about "unpickling estimator" are normal after sklearn updates
- Models still function correctly despite version differences

### Special Characters in Passwords
- Passwords with special characters (@, #, etc.) are automatically URL-encoded
- No manual encoding required
