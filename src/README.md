# Mergington High School Activities

A comprehensive web application for managing extracurricular activities at Mergington High School. Students can browse, search, and filter activities while teachers can manage registrations through an authenticated interface.

## Features

### For Students
- **Browse Activities**: View all 12+ extracurricular activities with detailed information
- **Advanced Search & Filtering**:
  - Search activities by name
  - Filter by category (Sports, Arts, Academic, Community, Technology)
  - Filter by day of the week (Monday through Sunday)
  - Filter by time (Before School, After School, Weekend)
- **Activity Details**: View schedules, descriptions, participant counts, and capacity limits
- **Registration**: Sign up for activities (requires teacher approval)

### For Teachers & Administrators
- **Secure Authentication**: Teacher login system with role-based access
- **Student Management**: 
  - Register students for activities
  - Remove students from activities
  - View participant lists and capacity

### Activity Categories
- **Sports**: Soccer Team, Basketball Team, Morning Fitness
- **Arts**: Art Club, Drama Club
- **Academic**: Math Club, Programming Class, Science Olympiad, Debate Team
- **Technology**: Weekend Robotics Workshop
- **Community**: Chess Club, Sunday Chess Tournament

## Technology Stack

- **Backend**: FastAPI (Python web framework)
- **Database**: MongoDB with Argon2 password hashing
- **Frontend**: Static HTML, CSS, JavaScript
- **Server**: Uvicorn ASGI server

## Quick Start

### Prerequisites
- Python 3.7+
- MongoDB
- pip (Python package manager)

### Installation
1. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Ensure MongoDB is running on `mongodb://localhost:27017/`

3. Run the application:
   ```bash
   uvicorn app:app --host 0.0.0.0 --port 8000 --reload
   ```

4. Access the application:
   - **Website**: http://localhost:8000
   - **API Documentation**: http://localhost:8000/docs

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/activities` | Get all activities with optional filtering by day/time |
| GET | `/activities/days` | Get list of all days that have activities |
| POST | `/activities/{name}/signup` | Register student for activity (teacher auth required) |
| POST | `/activities/{name}/unregister` | Remove student from activity (teacher auth required) |
| POST | `/auth/login` | Teacher authentication |
| GET | `/auth/check-session` | Validate login session |

### Teacher Login Credentials
- **Ms. Rodriguez** (mrodriguez / art123)
- **Mr. Chen** (mchen / chess456)  
- **Principal Martinez** (principal / admin789)

## Development Guide

For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).
