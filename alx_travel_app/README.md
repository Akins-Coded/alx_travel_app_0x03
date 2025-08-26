# ALX Travel App

ALX Travel App is a Django-based travel booking platform that allows users to browse listings (hotels, tours, rentals, activities), make bookings, and pay via the **Chapa** payment gateway. The system also supports **payment verification**, **email notifications**, and background task handling with **Celery**.

---

## **Features**

- **Listings**
  - Browse Hotels, Tours, Rentals, and Activities.
  - CRUD operations for listings (via API endpoints).

- **Bookings**
  - Book listings with check-in/check-out dates.
  - Track booking status: Pending, Confirmed, Cancelled, Completed.

- **Payments**
  - Initiate payments via Chapa API.
  - Verify payment status with Chapa.
  - Update payment status in database: Pending, Completed, Failed, Refunded.
  - Email confirmation sent asynchronously via Celery.

- **Reviews**
  - Rate listings from 1–5.
  - Each user can only review a listing once.

---

## **Tech Stack**

- Backend: **Django 5.x**, **Django REST Framework**
- Database: **MySQL**
- Task Queue: **Celery** with **RabbitMQ**
- Payment Gateway: **Chapa**
- Environment Management: **django-environ**
- API Documentation: **drf-yasg (Swagger)**

---



###  **API Endpoints**
Endpoint	Method	Description
/listings/	GET/POST	List or create listings
/listings/<id>/	GET/PUT/DELETE	Retrieve, update, delete listing
/bookings/	GET/POST	List or create bookings
/bookings/<id>/	GET/PUT/DELETE	Retrieve, update, delete booking
/payments/initiate/<booking_id>/	POST	Initiate Chapa payment for booking
/payments/verify/<transaction_id>/	