-- SQL Mini Project: Library Book Management System

CREATE DATABASE LibraryDB;
USE LibraryDB;

CREATE TABLE Books (
    book_id INT PRIMARY KEY,
    title VARCHAR(100),
    author VARCHAR(100),
    genre VARCHAR(50),
    available_copies INT
);

CREATE TABLE Members (
    member_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    join_date DATE
);

CREATE TABLE Loans (
    loan_id INT PRIMARY KEY,
    book_id INT,
    member_id INT,
    loan_date DATE,
    return_date DATE,
    FOREIGN KEY(book_id) REFERENCES Books(book_id),
    FOREIGN KEY(member_id) REFERENCES Members(member_id)
);

INSERT INTO Books VALUES
(1, 'The Hobbit', 'J.R.R. Tolkien', 'Fantasy', 5),
(2, '1984', 'George Orwell', 'Dystopian', 2),
(3, 'To Kill a Mockingbird', 'Harper Lee', 'Classic', 3);

INSERT INTO Members VALUES
(1, 'Alice Brown', 'alice@example.com', '2024-01-10'),
(2, 'John Smith', 'john@example.com', '2024-02-05');

INSERT INTO Loans VALUES
(1, 1, 1, '2024-03-01', NULL),
(2, 2, 2, '2024-03-05', '2024-03-12');
