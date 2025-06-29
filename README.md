JavaFX Licence Management System

A JavaFX-based desktop application with a built-in socket server to handle software activation requests. Admins can manage users, view licences, and monitor logs—all from a user-friendly UI.

Tech Stack

- JavaFX (GUI)
- Java Sockets (Server-Client Communication)
- MySQL (Database)
- JDBC (Connectivity)

Features

- Start/Stop server from the Admin UI
- Auto-generate licence files on valid activation
- Prevent same system from registering under multiple users
- Search and revoke licences
- Logs and request monitoring in UI

Database Setup

Run the following SQL in MySQL:

CREATE DATABASE licence_system;

USE licence_system;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100) UNIQUE NOT NULL
);

CREATE TABLE licence_details (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100),
    mac TEXT,
    cpu TEXT,
    os TEXT,
    `key` TEXT,
    valid_until DATE,
    FOREIGN KEY (username) REFERENCES users(username)
);

