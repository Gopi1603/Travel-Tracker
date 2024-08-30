# 🌍 Travel Tracker

Travel Tracker is a simple web application built with Node.js, Express, and PostgreSQL that allows users to track the countries they have visited.✈️

## Features

- 📋 View a list of countries that you have visited.
- ➕ Add new countries to your visited list.
- 🔢 Automatically updates the total number of countries visited.
- 🖥️ User-friendly interface with EJS templating.

## Technologies Used

- 🟢 Node.js
- 🚂 Express
- 🗄️ PostgreSQL
- 🧩 EJS
- 🛠️ Body-parser
- 🎨 CSS

## Prerequisites

Before you begin, ensure you have the following installed on your local machine:

- [Node.js](https://nodejs.org/) 🌐
- [PostgreSQL](https://www.postgresql.org/) 📊

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/travel-tracker.git
cd travel-tracker
```
### 2. Install Dependencies
```bash
npm install
```
### 3. Set Up the Database

Start PostgreSQL and create a database named world.
Run the following SQL commands to create the required tables:
```bash
CREATE TABLE countries (
    country_code VARCHAR(3) PRIMARY KEY,
    country_name VARCHAR(255) NOT NULL
);

CREATE TABLE visited_countries (
    id SERIAL PRIMARY KEY,
    country_code VARCHAR(3) REFERENCES countries(country_code)
);
```
Populate the countries table using the countries.csv file

```bash
\copy countries(country_code, country_name) FROM 'countries.csv' DELIMITER ',' CSV HEADER;
```

### 4. Configure the Database Connection
Update the database connection in index.js with your PostgreSQL credentials:
```bash
const db = new pg.Client({
  user: "your_username",
  host: "localhost",
  database: "world",
  password: "your_password",
  port: 5432,
});
```
### 5. Run the Application
```bash
node index.js
```
Visit http://localhost:3000 in your browser to view the application

## Contact Me

If you would like to get in touch, feel free to [visit my portfolio](https://mgopiportfolios.netlify.app/).

---

<sub><sup>✨ Crafted with ❤️ by [Gopi](https://github.com/Gopi1603) ✨</sup></sub>
