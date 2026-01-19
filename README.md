# Sky Web App - Team Health Check Platform

A Django-based internal health check platform designed for Sky employees to assess team wellbeing through periodic voting sessions. Features role-based access control, trend visualization, and secure authentication.

**Academic Project** - Developed for the 5COSC021W Software Development module at the University of Westminster.

## 📹 Demo Video
[Watch the full demonstration](https://universityofwestminster-my.sharepoint.com/:v:/g/personal/psarroa_westminster_ac_uk/EUgI8GFmuvRHinCGMNclvR0BkgnD4WpWi4XNxohedFzAWA?e=yKeMDm&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)

---

## 🎯 Key Features

### 🔐 Authentication & Security
- Secure user registration and login with email validation
- Password strength validation (uppercase, lowercase, numbers, special characters)
- Password reset functionality via email
- Role-based access control (RBAC) for different user types

### 👥 Role-Based Access
- **Engineers & Team Leaders** → Access to voting interface
- **Department Leaders & Senior Managers** → Access to trends and analytics
- **Admins** → Full Django admin panel access

### 📊 Voting System
- Vote on 11 pre-defined "Health Cards" covering team aspects:
  - Delivering Value
  - Easy to Release
  - Fun
  - Health of Codebase
  - Learning
  - Mission
  - Pawns or Players
  - Speed
  - Suitable Process
  - Support
  - Teamwork

### 📈 Trends Dashboard
- Visual representation of voting results with color-coded bar charts
- Track sentiment (Green/Yellow/Red) across health cards
- Monitor progress states (Improving/Stable/Declining)
- View aggregated comments from team members

### 🎨 User Interface
- Clean, responsive design following Sky brand guidelines
- Color-coded voting interface for intuitive feedback
- Progress tracking during voting sessions
- Centralized navigation bar across all pages

---

## 🛠️ Technologies Used

- **Backend**: Django 4.2.20 (Python 3)
- **Frontend**: HTML5, CSS3, JavaScript
- **Database**: SQLite (development) / PostgreSQL-ready
- **Authentication**: Django's built-in authentication system
- **Email**: SMTP (Gmail) for password reset
- **Additional Libraries**: django-widget-tweaks

---

## 📦 Installation & Setup

### Prerequisites
- Python 3.8+
- pip (Python package manager)
- Virtual environment (recommended)

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR-USERNAME/Sky-Web-App.git
cd Sky-Web-App
```

### 2. Create Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run Migrations
```bash
python3 manage.py makemigrations
python3 manage.py migrate
```

### 5. Load Sample Data (Optional but Recommended)
Load the fixture data in the following order:
```bash
python3 manage.py loaddata fixtures/departments.json
python3 manage.py loaddata fixtures/teams.json
python3 manage.py loaddata fixtures/healthcards.json
python3 manage.py loaddata fixtures/users.json
python3 manage.py loaddata fixtures/votes_sessions.json
```

### 6. Create Superuser (if not using fixtures)
```bash
python3 manage.py createsuperuser
```

### 7. Run Development Server
```bash
python3 manage.py runserver
```

Access the application at: `http://127.0.0.1:8000/`

---

## 👤 Default Admin Credentials (from fixtures)

- **Username**: `admin`
- **Email**: `admin1@gmail.com`
- **Password**: `admin`
- **Admin Panel**: http://127.0.0.1:8000/admin

---

## 📁 Project Structure

```
Sky-Web-App/
├── accounts/              # User authentication & profiles
│   ├── models.py         # Profile model with roles
│   ├── views.py          # Login, register, password reset
│   ├── decorators.py     # Role-based access decorators
│   └── templates/        # Auth templates
├── voting/               # Voting system
│   ├── models.py         # Department, Team, HealthCard, Vote, Session
│   ├── views.py          # Voting workflow logic
│   ├── forms.py          # VoteForm, StartVotingForm
│   └── templates/        # Voting interface templates
├── trends/               # Analytics & trends
│   ├── views.py          # Trend calculation and display
│   └── templates/        # Trend visualization templates
├── healthcheck/          # Main project settings
│   ├── settings.py       # Django configuration
│   └── urls.py           # URL routing
├── static/               # CSS, images, JavaScript
├── fixtures/             # Sample data
└── requirements.txt      # Python dependencies
```

---

## 🎓 My Contributions

As part of the development team, I contributed to:

### Backend Development
- **Role-Based Access Control**: Implemented `restrict_to_roles` decorator for securing views
- **Context Processor**: Created `user_role` context processor for dynamic navigation
- **Voting Logic**: Developed multi-step voting workflow with session management
- **Data Models**: Designed Profile, Vote, and Session models with proper relationships

### Frontend Development
- **Responsive Navigation**: Built centralized navbar with role-based link visibility
- **Form Styling**: Created custom form fields with Sky brand styling
- **Progress Tracking**: Implemented visual progress bar for voting sessions
- **State Management**: Developed radio button groups with custom styling

### Key Files Authored/Co-Authored
- `accounts/context_processors.py` - User role context for templates
- `accounts/decorators.py` - Role-based access decorators
- `voting/views.py` - Complete voting workflow
- `voting/models.py` - Database schema design
- `voting/forms.py` - Custom form implementations

---

## 🔒 Security & Compliance

### GDPR Compliance
- No identifiable vote data is stored
- User data can be deleted upon request
- Secure password hashing with Django's built-in system
- Email-based password recovery

### Security Features
- CSRF protection on all forms
- SQL injection protection via Django ORM
- XSS prevention through template escaping
- Role-based access control

---

## 🚀 Future Enhancements

Potential improvements for production deployment:

- [ ] PostgreSQL database integration
- [ ] Real-time trend updates with WebSockets
- [ ] Export trends to PDF/Excel
- [ ] Multi-language support
- [ ] Mobile-responsive optimizations
- [ ] OAuth integration (Google, Microsoft)
- [ ] Automated voting reminders via email
- [ ] Historical trend comparison across sessions

---

## 👥 Team - 5SC14_15_H

- **Parham Golmohammadi** - Backend & Frontend Development
- **Dawud Hussain** - Authentication System & Database Design
- **Aleena Haroon** - Tutorial System & UI Components
- **A-nuur Hasan** - Testing & Documentation
- **Hasan Jaafar** - Frontend Styling & UX

---

## 📄 License

This project is for **academic purposes only** and is not intended for commercial deployment.

---

## 🙏 Acknowledgments

- University of Westminster - 5COSC021W Software Development Module
- Sky UK - For project inspiration and brand guidelines
- Django Community - For excellent documentation and support
