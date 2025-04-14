# Student-Registration-and-Course-Management-System

 Project Title:
Student Registration and Course Management System

🔹 Objective:
To design and implement a relational database to manage student information, their course enrollments, and performance using SQL.

🔹 Database Tables Created:
Students – stores student details

Courses – stores course information

Enrollments – links students to the courses they enroll in

📁 SQL File Content (You can save this as student_management.sql)
sql
Copy
Edit
-- Create Students Table
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100),
    DateOfBirth DATE
);

-- Create Courses Table
CREATE TABLE Courses (
    CourseID INT PRIMARY KEY,
    CourseName VARCHAR(100),
    Credits INT
);

-- Create Enrollments Table
CREATE TABLE Enrollments (
    EnrollmentID INT PRIMARY KEY,
    StudentID INT,
    CourseID INT,
    EnrollmentDate DATE,
    Grade CHAR(2),
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);

-- Insert Sample Data
INSERT INTO Students VALUES (1, 'Alice', 'Brown', 'alice.brown@example.com', '2002-04-12');
INSERT INTO Courses VALUES (101, 'Database Systems', 4);
INSERT INTO Enrollments VALUES (1001, 1, 101, '2025-04-14', 'A');
🧠 What It Does:
Stores structured student and course data

Tracks which student is enrolled in which course

Maintains grade records for each enrollment

