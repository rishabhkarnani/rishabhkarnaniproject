# Cloud-based Travel Itinerary Planner

## Section 1: Project Description

### 1.1 Project Name

**Cloud-based Travel Itinerary Planner**

### 1.2 Description

The Cloud-based Travel Itinerary Planner is a powerful tool designed for travelers to help organize, manage, and keep track of their vacations and trips. The app centralizes important travel data like flight information, accommodation, activities, and documents. It allows users to plan day-by-day itineraries, store and access travel documents, and receive reminders about upcoming travel events. The platform is fully cloud-based, ensuring users can access their travel details from any device.

### 1.3 Revision History

| Date       | Comment                                   | Author      |
|------------|-------------------------------------------|-------------|
| 2025-03-26 | Initial version of the README file        | Rishabh Karnani |

---

## Section 2: Overview

### 2.1 Purpose

The purpose of this project is to create a cloud-based system where travelers can store all their trip details in one place. The platform enables seamless management of itineraries, bookings, documents, and reminders, ultimately making travel planning a stress-free experience.

### 2.2 Scope

- **User Authentication**: Secure login to ensure personalized travel data is kept private.
- **Trip Management**: Users can create, edit, and delete trips, and manage day-by-day travel itineraries.
- **Document Storage**: Support for uploading and managing important travel documents (passport, tickets, etc.).
- **Cloud Storage**: All trip data and documents are stored securely on the cloud, ensuring access from any device.
- **Reminders & Notifications**: Automated notifications for upcoming flights, hotel check-ins, and activity bookings.

### 2.3 Requirements

#### 2.3.1 Functional Requirements
- Users must be able to register and log in securely.
- Users must be able to create and manage multiple trips with detailed itineraries.
- The system must allow document uploads (e.g., PDFs, images) for tickets, passports, and other travel-related papers.
- The system should provide notifications about upcoming trips, bookings, and reminders.

#### 2.3.2 Non-Functional Requirements
- The application must be scalable and able to handle up to 1000 concurrent users.
- It should have a minimum 99.9% uptime to ensure availability.

#### 2.3.3 Technical Requirements
- **Backend**: Node.js (Express.js) / Python (Flask)
- **Frontend**: React.js / HTML, CSS
- **Cloud Storage**: Firebase Storage / AWS S3
- **Database**: Firebase Firestore / AWS DynamoDB
- **Third-Party Integrations**: Google Maps API (for displaying locations of destinations)

#### 2.3.4 Security Requirements
- Multi-factor authentication for logging in.
- Encryption of sensitive data both in transit and at rest.

---

## Section 3: System Architecture

### 3.1 Overview

The system architecture is designed to be modular and scalable. It consists of three main components:

1. **Frontend (Client-side)**:
   - Built using React.js, this component handles all user interactions, including login, trip creation, and document management.
2. **Backend (Server-side)**:
   - Built using Node.js (Express.js) or Python (Flask), the backend handles user requests, processes data, and communicates with the database and cloud storage.
3. **Cloud Storage**:
   - Firebase Storage or AWS S3 is used to store documents and other user data securely.

### 3.2 Architectural Diagrams

#### System Architecture

```plaintext
+------------------+     +-----------------+     +-------------------+
|   Frontend       | <-- |  Backend (API)  | <-- | Cloud Storage     |
|   (React.js)     |     |  (Node.js/Flask)|     | (Firebase/AWS S3) |
+------------------+     +-----------------+     +-------------------+
       |                        |
       |                     Database
       |                     (Firestore/DynamoDB)
       v
+--------------------+
| User Authentication|
|   (OAuth2 / JWT)   |
+--------------------+
```

## Section 4: Data Dictionary

| Table            | Field           | Type        | Description                          |
|------------------|-----------------|-------------|--------------------------------------|
| `users`          | `user_id`       | INTEGER     | Unique identifier for each user     |
|                  | `username`      | VARCHAR(50) | User's login name                   |
|                  | `password`      | VARCHAR(255)| Encrypted user password             |
| `itineraries`    | `itinerary_id`  | INTEGER     | Unique identifier for each itinerary|
|                  | `user_id`       | INTEGER     | Foreign key linking to `users` table|
|                  | `trip_details`  | JSON        | Detailed trip information           |
| `documents`      | `document_id`   | INTEGER     | Unique identifier for each document |
|                  | `user_id`       | INTEGER     | Foreign key linking to `users` table|
|                  | `file_url`      | VARCHAR(255)| URL for stored file in cloud        |

## Section 5: Data Design

### 5.1 Persistent Data

Entities:
- **User**
  - **Attributes**: `user_id` (PK), `username`, `password`, `email`
  - **Relationships**: One-to-many relationship with itineraries.

- **Itinerary**
  - **Attributes**: `itinerary_id` (PK), `user_id` (FK), `trip_details` (JSON)
  - **Relationships**: One-to-many relationship with documents.

- **Document**
  - **Attributes**: `document_id` (PK), `user_id` (FK), `file_url`
  - **Relationships**: Each document is associated with one user.

## Section 6: User Interface Design

### 6.1 User Interface Design Overview

The interface is designed to be user-friendly and responsive. It includes:
- **Login Screen**: For secure access to the user’s personal information.
- **Dashboard**: A control center where users can manage multiple trips.
- **Itinerary Page**: Detailed breakdown of each trip, including day-wise travel plans and document uploads.
- **Reminders Section**: Displays upcoming events such as flights, check-ins, and bookings.

### 6.2 User Interface Navigation Flow

1. **Login Screen** → 2. **Dashboard** → 3. **Itinerary Page** → 4. **Reminders Section**

## Section 7: Testing

### 7.1 Test Plan

- **Objective**: Ensure that all features, such as user authentication, trip management, and document uploads, work as expected.

- **Test Cases**:
  - **Test case for login functionality**: Ensure valid credentials allow access and invalid credentials result in an error.
  - **Test case for document upload**: Ensure that only supported file types (PDF, JPG, PNG) are uploaded.
  - **Test case for trip creation**: Ensure users can create and edit their itineraries successfully.

## Section 8: Monitoring

### 8.1 Key Metrics

- **Performance**: Track API response time and system latency.
- **Error Rate**: Monitor failed requests to identify bugs or issues.
- **Availability**: Uptime monitoring to ensure the system is accessible.

## Section 9: Other Interfaces

- **Google Maps API**: For location-based features like map integration and displaying places from the itinerary.

## Section 10: Extra Design Features / Outstanding Issues

- **Future Enhancements**: 
  - AI-powered trip suggestions.
  - Integration with third-party booking systems for real-time flight and hotel bookings.

## Section 11: References

- [Firebase Documentation](https://firebase.google.com/docs)
- [AWS S3 Documentation](https://aws.amazon.com/s3/)

## Section 12: Glossary

- **API**: Application Programming Interface
- **PK**: Primary Key
- **FK**: Foreign Key





