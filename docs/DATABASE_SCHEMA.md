# Database Schema Design

## 1. Finances
### Tables:
- **Transactions**  
  - `transaction_id`: INT, Primary Key  
  - `user_id`: INT, Foreign Key  
  - `amount`: DECIMAL  
  - `transaction_type`: ENUM('income', 'expense')  
  - `date`: DATETIME  

## 2. Fitness
### Tables:
- **Workout_Records**  
  - `record_id`: INT, Primary Key  
  - `user_id`: INT, Foreign Key  
  - `exercise`: VARCHAR  
  - `duration`: INT (minutes)  
  - `calories_burned`: INT  
  - `date`: DATETIME  

## 3. Mental Health
### Tables:
- **Mood_Tracking**  
  - `mood_id`: INT, Primary Key  
  - `user_id`: INT, Foreign Key  
  - `mood`: ENUM('happy', 'sad', 'anxious', etc.)  
  - `note`: TEXT  
  - `date`: DATETIME  

## 4. Sleep
### Tables:
- **Sleep_Records**  
  - `sleep_id`: INT, Primary Key  
  - `user_id`: INT, Foreign Key  
  - `sleep_start`: DATETIME  
  - `sleep_end`: DATETIME  
  - `quality`: ENUM('good', 'average', 'poor')  

## 5. Reading
### Tables:
- **Books**  
  - `book_id`: INT, Primary Key  
  - `user_id`: INT, Foreign Key  
  - `title`: VARCHAR  
  - `author`: VARCHAR  
  - `status`: ENUM('reading', 'completed', 'on hold')  
  - `date_added`: DATETIME  

## 6. Chatbot
### Tables:
- **Chatbot_Interactions**  
  - `interaction_id`: INT, Primary Key  
  - `user_id`: INT, Foreign Key  
  - `query`: TEXT  
  - `response`: TEXT  
  - `timestamp`: DATETIME  

## 7. User Management
### Tables:
- **Users**  
  - `user_id`: INT, Primary Key  
  - `username`: VARCHAR  
  - `email`: VARCHAR  
  - `password_hash`: VARCHAR  
  - `created_at`: DATETIME  

## Relationships:
- Each module has a `user_id` that links to the `Users` table, creating a one-to-many relationship between Users and each module's table.
