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

# README — Task 2 (Gmail Email Reader)

```markdown
# Gmail Email Reader

A Spring Boot application that connects with Gmail using Gmail API and fetches the latest 200 emails.

The application displays:
- Sender Name
- Email Subject

---

## Features

- Gmail API integration
- OAuth 2 authentication
- Fetch latest 200 emails
- Display sender and subject
- Spring Boot backend implementation

---

## Technologies Used

- Java 17
- Spring Boot
- Gmail API
- OAuth 2.0
- Maven
- Lombok

---

## Project Structure

src/main/java/com/bxp/gmail_email_reader
│
├── gmail
│   ├── GmailService.java
│   └── GmailRunner.java

---

## Gmail API Setup

1. Create Google Cloud Project
2. Enable Gmail API
3. Configure OAuth Consent Screen
4. Create OAuth Client ID
5. Download credentials.json
6. Place credentials.json inside:

```text

src/main/resources/
________________________________________
Dependencies Used
•	google-api-client
•	google-oauth-client-jetty
•	google-api-services-gmail
________________________________________
Sample Output

FROM : Amazon
SUBJECT : Your Order Has Been Shipped

FROM : LinkedIn
SUBJECT : Java Developer Jobs Recommended For You
________________________________________
How To Run
1.	Configure Gmail API credentials
2.	Place credentials.json in resources folder
3.	Run application
4.	Login to Gmail when browser opens
5.	Allow permissions
6.	Console displays latest 200 emails
________________________________________
Build JAR

./mvnw clean package
Generated JAR file will be inside:

target/
________________________________________
Important Note
Do NOT upload:

credentials.json
tokens/
These contain sensitive OAuth credentials.
________________________________________
Author
POORNA CHANDRA GANESH M ```
