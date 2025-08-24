## Team Roles

In our project, each team member has specific roles and responsibilities to ensure smooth collaboration and successful delivery. Below are the defined roles (based on the project overview and insights from the ITRexGroup blog):

### 1. Backend Developer
- Responsible for building and maintaining the server-side logic of the application.  
- Implements APIs, manages data processing, and ensures integration between the frontend and backend systems.  
- Focuses on performance, scalability, and security of the backend services.  

### 2. Frontend Developer
- Works on the user interface and client-side logic of the application.  
- Ensures that the application is responsive, visually appealing, and provides a seamless user experience.  
- Collaborates closely with the backend developer to integrate APIs and data.  

### 3. Database Administrator (DBA)
- Manages the project’s databases, ensuring data integrity, availability, and security.  
- Responsible for database design, optimization, and performance tuning.  
- Sets up backup and recovery plans to prevent data loss.  

### 4. Project Manager
- Oversees the project timeline, deliverables, and communication within the team.  
- Coordinates between stakeholders and developers to ensure project goals are met.  
- Tracks progress, manages risks, and ensures that the team adheres to deadlines.  

### 5. Quality Assurance (QA) Engineer
- Tests the application to identify and fix bugs before release.  
- Ensures that the product meets the required quality standards.  
- Creates and executes test cases (manual and automated) to validate functionality and performance.  

### 6. UI/UX Designer
- Designs the layout, visuals, and overall user experience of the application.  
- Creates wireframes, prototypes, and design assets to guide frontend implementation.  
- Ensures the product is intuitive and user-friendly.  

### 7. DevOps Engineer
- Sets up and manages deployment pipelines, CI/CD processes, and cloud infrastructure.  
- Monitors system performance, reliability, and uptime.  
- Automates repetitive tasks to streamline development and deployment.

  ## Technology Stack

This project uses a modern technology stack that supports scalability, performance, and maintainability. Below are the core technologies and their purposes in the project:

### 1. Django
- A high-level Python web framework used for building robust and secure server-side applications.  
- Provides built-in features for authentication, ORM (Object-Relational Mapping), and RESTful API development.  

### 2. PostgreSQL
- A powerful open-source relational database system.  
- Stores and manages structured data for the project while ensuring data consistency, integrity, and reliability.  

### 3. GraphQL
- A query language for APIs that allows clients to request only the data they need.  
- Provides flexibility and efficiency in data fetching compared to traditional REST APIs.  

### 4. Docker
- A containerization platform used to package the application and its dependencies.  
- Ensures consistent environments across development, testing, and production.  

### 5. Git & GitHub
- Git is a version control system for tracking code changes.  
- GitHub hosts the project repository, enabling team collaboration, code reviews, and issue tracking.  

### 6. HTML, CSS, and JavaScript
- Core frontend technologies for structuring, styling, and adding interactivity to the web application.  
- Ensure a responsive and user-friendly interface.  

### 7. REST/GraphQL APIs
- Provide communication between the frontend and backend.  
- Ensure seamless data exchange with security and performance in mind.

## Database Design

The project database is designed to support core functionality such as user management, property listings, bookings, payments, and reviews. Below are the key entities, their important fields, and their relationships.

### 1. Users
- **Fields:**  
  - `user_id` (Primary Key)  
  - `name`  
  - `email` (unique)  
  - `password_hash`  
  - `role` (e.g., admin, host, customer)  
- **Notes:** Users can act as customers (booking properties) or hosts (listing properties).

### 2. Properties
- **Fields:**  
  - `property_id` (Primary Key)  
  - `user_id` (Foreign Key → Users)  
  - `title`  
  - `description`  
  - `location`  
- **Notes:** A property is created by a user (host). One user can have many properties.

### 3. Bookings
- **Fields:**  
  - `booking_id` (Primary Key)  
  - `user_id` (Foreign Key → Users)  
  - `property_id` (Foreign Key → Properties)  
  - `check_in_date`  
  - `check_out_date`  
- **Notes:** A booking links a user (customer) to a property. One property can have multiple bookings.

### 4. Payments
- **Fields:**  
  - `payment_id` (Primary Key)  
  - `booking_id` (Foreign Key → Bookings)  
  - `amount`  
  - `payment_date`  
  - `status` (e.g., pending, completed, failed)  
- **Notes:** Each booking has one corresponding payment record.

### 5. Reviews
- **Fields:**  
  - `review_id` (Primary Key)  
  - `user_id` (Foreign Key → Users)  
  - `property_id` (Foreign Key → Properties)  
  - `rating` (1–5)  
  - `comment`  
- **Notes:** A user can leave multiple reviews, but only one per property per booking. Properties can have many reviews.

---

### Entity Relationships
- A **User** can list many **Properties**.  
- A **User** can make many **Bookings**.  
- A **Booking** is linked to one **Property** and one **User**.  
- A **Booking** has one **Payment**.  
- A **Property** can have many **Reviews**, each written by a **User**.  


