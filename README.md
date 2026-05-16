README — Task 1 (Metro Ticket Booking System)
# Metro Ticket Booking System

A Spring Boot backend application for booking metro tickets between stations.
The application generates a unique ticket ID which acts as the metro ticket.

---

## Features

- Book metro tickets between any two stations
- Ticket ID generated using UUID
- Ticket expires after 18 hours
- Ticket can be used only twice
  - First for station entry
  - Second for station exit
- Exit is not allowed before entry
- JSON-based station pricing
- MySQL database integration
- REST API support
- Exception handling and validation

---

## Technologies Used

- Java 17
- Spring Boot
- Spring Data JPA
- MySQL
- Maven
- Lombok
- Postman

---

## Project Structure

src/main/java/com/bxp/metro_ticket_system
│
├── controller
├── service
├── repository
├── entity
├── dto
├── exception
└── config

---

## Database Configuration

Create database:

```sql

CREATE DATABASE metrodb;
Update application.properties:

spring.datasource.url=jdbc:mysql://localhost:3306/metrodb
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
________________________________________
API Endpoints
1. Book Ticket
POST:

/api/tickets/book
Request Body:

{
  "sourceStation": "B",
  "destinationStation": "F"
}
Sample Response:

{
  "ticketId": "uuid-generated-id",
  "sourceStation": "B",
  "destinationStation": "F",
  "price": 20,
  "message": "Ticket Booked Successfully"
}
________________________________________
2. Enter Station
POST:

/api/tickets/enter/{ticketId}
Sample Response:

Entry Successful
________________________________________
3. Exit Station
POST:

/api/tickets/exit/{ticketId}
Sample Response:

Exit Successful
________________________________________
Validation Rules
•	Ticket expires after 18 hours
•	Ticket usage limit is 2
•	Exit not allowed before entry
•	Duplicate entry not allowed
•	Duplicate exit not allowed
________________________________________
How To Run
1.	Clone repository
2.	Configure MySQL
3.	Run application
4.	Test APIs using Postman
________________________________________
Build JAR

./mvnw clean package
Generated JAR file will be inside:

target/
________________________________________
Author
POORNA CHANDRA GANESH M

---


