# Airbnb Clone Project

## Project Overview
The goal of this project is to create an Airbnb clone that allows users to manage property listings, make bookings, and leave reviews. The project will involve building a backend API with features such as user management, property management, a booking system, and payment integration.

## Team Roles

### Backend Developer
- **Responsibilities**: Responsible for implementing API endpoints, database schemas, and business logic. 

### Database Administrator
- **Responsibilities**: Manages database design, indexing, and optimizations.

### Devops Engineer 
- **Responsibilities**: Handles deployment, monitoring, and scaling of the backend services.

### QA Engineer
- **Responsibilities**: Ensures the backend functionalities are thoroughly tested and meet quality standards.

## Technology Stack

- **Django**: A high-level Python web framework used for building the RESTful API.
- **Django REST Framework**: Provides tools for creating and managing RESTful APIs.
- **PostgreSQL**: A powerful relational database used for data storage.
- **GraphQL**: Allows for flexible and efficient querying of data.
- **Celery**: For handling asynchronous tasks such as sending notifications or processing payments.
- **Redis**: Used for caching and session management.
- **Docker**: Containerization tool for consistent development and deployment environments.
- **CI/CD Pipelines**: Automated pipelines for testing and deploying code changes.

## Database Design

### Key Entities and Relationships

1. **Users**
   - Fields: `id`, `email`, `password`, `first_name`, `last_name`
   - A user can create multiple properties, make bookings, and leave reviews.

2. **Properties**
   - Fields: `id`, `owner_id (foreign key to Users)`, `price`, `location`, `description`
   - A property belongs to a user (the owner), and multiple bookings can be made for a property.

3. **Bookings**
   - Fields: `id`, `user_id (foreign key to Users)`, `property_id (foreign key to Properties)`, `booking_date`
   - A booking belongs to a user and a property.

4. **Reviews**
   - Fields: `id`, `user_id (foreign key to Users)`, `property_id (foreign key to Properties)`, `review_text`, `rating`
   - A review is made by a user for a specific property.

5. **Payments**
   - Fields: `id`, `user_id (foreign key to Users)`, `amount`, `payment_date`
   - A payment is made by a user for a booking.

## Feature Breakdown

- **User Management**
  - Allows users to sign up, log in, and manage their profiles.

- **Property Management**
  - Lets property owners list and manage their properties, including setting the price, location, and availability.

- **Booking System**
  - Users can book properties, view availability, and manage their bookings.

- **Review System**
  - Users can leave reviews and ratings for properties they have stayed at.

- **Payment Integration**
  - Users can make payments for bookings securely using a payment gateway.

## API Security

- **Authentication**: Ensures that users are verified through login credentials, such as email and password, before accessing protected resources.

- **Authorization**: Determines what data and actions a user is allowed to access. For example, only the owner of a property can modify its details.

- **Rate Limiting**: Prevents abuse by limiting the number of API requests a user can make in a given time period.

API security is essential to protect sensitive user data, secure financial transactions, and prevent unauthorized access to resources.
