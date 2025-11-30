# ALX Travel App API

A Django REST Framework application for managing travel listings and bookings.

## Overview

This project implements a RESTful API for a travel booking platform similar to Airbnb or Booking.com. It provides CRUD (Create, Read, Update, Delete) endpoints for managing property listings and bookings, with Swagger documentation for easy API exploration and testing.

## Features

- **Listings Management**: Create, read, update, and delete property listings
- **Bookings Management**: Create, read, update, and delete bookings
- **Swagger Documentation**: Interactive API documentation at `/swagger/`
- **RESTful API Design**: Following REST best practices

## Tech Stack

- **Django** - High-level Python web framework
- **Django REST Framework (DRF)** - Toolkit for building Web APIs
- **drf-yasg** - Swagger/OpenAPI documentation generator
- **MySQL** - Database (configurable)
- **CORS Headers** - Cross-Origin Resource Sharing support

## Project Structure

```
alx_travel_app_0x01/
├── manage.py
├── alx_travel_app/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   ├── asgi.py
│   └── listings/
│       ├── __init__.py
│       ├── admin.py
│       ├── apps.py
│       ├── models.py
│       ├── serializers.py
│       ├── urls.py
│       ├── views.py
│       └── tests.py
├── listings/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── serializers.py
│   ├── urls.py
│   ├── views.py
│   └── tests.py
└── README.md
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/alx_travel_app_0x01.git
cd alx_travel_app_0x01
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install django djangorestframework drf-yasg django-cors-headers python-decouple mysqlclient
```

4. Create a `.env` file with your database credentials:
```
DB_NAME=your_database_name
DB_USER=your_database_user
DB_PASSWORD=your_database_password
```

5. Run migrations:
```bash
python manage.py makemigrations
python manage.py migrate
```

6. Start the development server:
```bash
python manage.py runserver
```

## API Endpoints

### Listings

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/listings/` | Retrieve all listings |
| POST | `/api/listings/` | Create a new listing |
| GET | `/api/listings/<id>/` | Retrieve a specific listing |
| PUT | `/api/listings/<id>/` | Update a specific listing |
| DELETE | `/api/listings/<id>/` | Delete a specific listing |

### Bookings

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/bookings/` | Retrieve all bookings |
| POST | `/api/bookings/` | Create a new booking |
| GET | `/api/bookings/<id>/` | Retrieve a specific booking |
| PUT | `/api/bookings/<id>/` | Update a specific booking |
| DELETE | `/api/bookings/<id>/` | Delete a specific booking |

## API Documentation

Access the Swagger documentation at: `http://localhost:8000/swagger/`

## Models

### Listing
- `title` - Property title
- `description` - Property description
- `location` - Property location
- `price_per_night` - Price per night
- `created_at` - Creation timestamp
- `updated_at` - Last update timestamp

### Booking
- `listing` - Foreign key to Listing
- `user_name` - Name of the user making the booking
- `user_email` - Email of the user
- `start_date` - Booking start date
- `end_date` - Booking end date
- `total_price` - Total booking price
- `status` - Booking status (pending, confirmed, canceled)
- `created_at` - Creation timestamp

## Testing with Postman

1. Import the API endpoints into Postman
2. Test each endpoint:
   - **GET** requests to retrieve data
   - **POST** requests to create new entries
   - **PUT** requests to update existing entries
   - **DELETE** requests to remove entries

## License

This project is part of the ALX Software Engineering program.
