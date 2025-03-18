# Hospital-Management-System
# Hospital Management System

A comprehensive web-based hospital management system built with Flask, featuring patient management, doctor profiles, appointment scheduling, and administrative controls.

## Features

- User authentication with role-based access control (Admin, Doctor, Staff)
- Patient records management
- Doctor profiles and availability tracking
- Appointment scheduling and management
- Admin dashboard with reports and user management
- Responsive design for all devices

## Prerequisites

- Python 3.8 or higher
- pip (Python package manager)
- Git (optional, for cloning the repository)

## Installation and Setup

Follow these steps to run the project on your local machine:

### 1. Clone or download the repository

```bash
git clone <repository-url>
# Or download and extract the ZIP file
cd hospital-management
```

### 2. Create and activate a virtual environment (recommended)

#### Windows
```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS/Linux
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Initialize the database

```bash
python -c "from app import db, create_app; db.create_all(app=create_app())"
```

### 5. Populate the database with sample data (optional)

```bash
python mock_data.py
python populate_appointments.py
```

### 6. Run the application

```bash
python run.py
```

The application will be accessible at `http://127.0.0.1:5000/` in your web browser.

## Default Login Credentials

### Admin
- Username: admin
- Password: admin1234

### Doctors
- Username: doctor1
- Password: doctor1

Additional doctor accounts follow the same pattern (doctor2/doctor2, doctor3/doctor3, etc.)

## Project Structure

```
hospital-management/
├── app/                    # Application package
│   ├── __init__.py         # App initialization
│   ├── models.py           # Database models
│   ├── routes/             # Route blueprints
│   ├── static/             # Static files (CSS, JS)
│   └── templates/          # HTML templates
├── config.py               # Configuration settings
├── mock_data.py            # Sample data generator
├── populate_appointments.py# Appointment data generator
├── requirements.txt        # Dependencies
└── run.py                  # Application entry point
```

## Development

To run the application in debug mode:

```bash
flask run --debug
```

## Troubleshooting

If you encounter any issues:

1. Ensure your virtual environment is activated
2. Verify all dependencies are installed correctly
3. Check that the database has been initialized properly
4. Make sure you're using the correct Python version

For database-related issues, you can reset the database:

```bash
# Remove the existing database
rm -f instance/hospital.db

# Recreate and populate the database
python -c "from app import db, create_app; db.create_all(app=create_app())"
python mock_data.py
python populate_appointments.py
```

## License

[MIT License](LICENSE)
