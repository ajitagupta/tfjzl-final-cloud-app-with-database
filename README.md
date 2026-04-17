# Online Course Application

A Django-based web application for managing online courses with user authentication, course enrollment, and an interactive exam/assessment system. Users can register, enroll in courses, take exams, and view their results with detailed feedback.

## Features

- **User Authentication**: Register, login, and logout functionality
- **Course Management**: Browse and enroll in available courses
- **Lesson Content**: View course lessons with detailed content
- **Exam System**: Take course exams with multiple-choice questions
- **Results & Feedback**: View exam scores with correct/incorrect answer breakdown
- **Responsive Design**: Bootstrap-based UI for desktop and mobile

## Tech Stack

- **Backend**: Python, Django
- **Frontend**: HTML, CSS, JavaScript, Bootstrap
- **Database**: SQLite3 (default), PostgreSQL, or MySQL
- **Deployment**: IBM Cloud Foundry (default), or any cloud platform

## Project Structure

```
tfjzl-final-cloud-app-with-database/
├── myproject/
│   ├── settings.py          # Django project settings
│   ├── urls.py               # URL routing
│   └── wsgi.py               # WSGI configuration
├── onlinecourse/
│   ├── models.py             # Database models (Course, Lesson, Question, Choice, etc.)
│   ├── views.py              # View logic for all pages
│   ├── urls.py               # App-specific URL routing
│   ├── admin.py              # Admin panel configuration
│   └── templates/            # HTML templates
├── static/                   # Static files (CSS, JS, images)
├── manage.py                 # Django management script
├── requirements.txt          # Python dependencies
├── Procfile                  # Deployment configuration
├── manifest.yml              # IBM Cloud Foundry manifest
├── runtime.txt               # Python runtime version
└── README.md
```

## Data Model

The application uses the following entity relationships:

![ER Diagram](https://github.com/ibm-developer-skills-network/final-cloud-app-with-database/raw/master/static/media/course_images/onlinecourse_app_er.png)

| Entity | Description |
|--------|-------------|
| Course | Online course with name, description, and image |
| Lesson | Individual lessons belonging to a course |
| Instructor | Course instructors with user association |
| Learner | Students enrolled in courses |
| Question | Exam questions linked to a course |
| Choice | Answer choices for each question (with correct flag) |
| Submission | Student exam submissions tracking selected choices |

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ajitagupta/tfjzl-final-cloud-app-with-database.git
   cd tfjzl-final-cloud-app-with-database
   ```

2. **Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run database migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **Create a superuser** (for admin access)
   ```bash
   python manage.py createsuperuser
   ```

6. **Run the development server**
   ```bash
   python manage.py runserver
   ```

The application will be available at `http://localhost:8000`.

## Usage

### For Students
1. Register a new account or login
2. Browse available courses on the home page
3. Enroll in a course
4. View course lessons and content
5. Take the course exam
6. View your results with detailed feedback

### For Administrators
1. Access the admin panel at `/admin`
2. Add/edit courses, lessons, and instructors
3. Create exam questions with multiple choices
4. Mark correct answers for each question
5. View student enrollments and submissions

## Deployment

### IBM Cloud Foundry (Default)
```bash
ibmcloud cf push
```

### Alternative Platforms
The app can be deployed to Heroku, Render, or any platform supporting Django:
- Ensure `Procfile` contains: `web: gunicorn myproject.wsgi`
- Set environment variables for production (SECRET_KEY, DEBUG, DATABASE_URL)
- Configure static file serving with WhiteNoise

## Course Context

This project was developed as the final project for the **IBM Full Stack Software Developer Professional Certificate** on Coursera, specifically for the course on Django Application Development with SQL and Databases.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Author

**Ajita Gupta**  
- GitHub: [@ajitagupta](https://github.com/ajitagupta)
- Website: [ajitagupta.com](https://ajitagupta.com)

## Acknowledgments

- IBM Developer Skills Network for the course template and guidance
- Django Software Foundation for the web framework
