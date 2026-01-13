# 🔗 URL Shortener

A clean and scalable URL shortener web application built with **FastAPI** and **SQLite**. This project demonstrates modern Python web development practices with a focus on clean architecture and separation of concerns.

## ✨ Features

- 🚀 **Shorten long URLs** with randomly generated short codes
- 🔄 **Redirect to original URLs** using short codes
- 📊 **Track click statistics** for each shortened URL
- 🗄️ **SQLite database** for persistent storage
- 🔌 **RESTful API** with comprehensive endpoints
- ✅ **Input validation** with Pydantic models
- 🧪 **Comprehensive test suite** with pytest
- 📝 **Auto-generated API documentation**

## 🏗️ Project Structure

```
.
├── main.py            # FastAPI app with routing
├── models.py          # Pydantic models for validation
├── database.py        # SQLite database setup and models
├── crud.py            # Database operations (Create, Read, Update, Delete)
├── utils.py           # Utility functions (URL code generator)
├── test_main.py       # Comprehensive test suite
├── requirements.txt   # Python dependencies
├── .gitignore        # Git ignore rules
└── README.md         # Project documentation
```

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- pip (Python package manager)


### Test Coverage

The test suite covers:
- ✅ URL shortening functionality
- ✅ URL redirection
- ✅ Statistics tracking
- ✅ Input validation
- ✅ Error handling
- ✅ Edge cases

## 🏛️ Architecture

### Clean Architecture Principles

1. **Separation of Concerns**
   - `main.py`: API routing and HTTP handling
   - `models.py`: Data validation and serialization
   - `database.py`: Database models and connection
   - `crud.py`: Database operations
   - `utils.py`: Business logic utilities

2. **Dependency Injection**
   - Database sessions injected via FastAPI's Depends
   - Easy to mock for testing

3. **Input Validation**
   - Pydantic models ensure data integrity
   - Automatic API documentation generation


### Development Commands

```bash
# Install in development mode
pip install -e .

# Run with auto-reload for development
uvicorn main:app --reload

# Format code
black .

# Type checking
mypy .

# Run linter
flake8 .
```

## 🚀 Deployment

### Local Deployment
```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

### Production Deployment (Render)

1. **Create a `Procfile`:**
   ```
   web: uvicorn main:app --host 0.0.0.0 --port $PORT
   ```

2. **Deploy to Render:**
   - Connect your GitHub repository
   - Set build command: `pip install -r requirements.txt`
   - Set start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`

### Docker Deployment
```dockerfile
FROM python:3.9-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .
EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

## 🔐 Security Considerations

- Input validation with Pydantic
- SQL injection prevention with SQLAlchemy ORM
- Rate limiting (can be added with slowapi)
- HTTPS in production (handled by deployment platform)

## 🛠️ Technology Stack

- **Backend:** FastAPI (Python)
- **Database:** SQLite with SQLAlchemy ORM
- **Validation:** Pydantic
- **Testing:** pytest
- **Documentation:** Auto-generated with FastAPI



