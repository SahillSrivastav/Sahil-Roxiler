# Sahil Srivastava - Roxiler

## Project Overview
This project is a MERN stack application designed for managing and visualizing product transaction data. It fetches data from a third-party API and provides functionalities to view transactions, statistics, and visual charts. The frontend offers filtering, search, and pagination features for ease of data exploration.

---

## Tech Stack
- **Backend**: Node.js, Express, MongoDB
- **Frontend**: React.js, Chart.js (or a charting library of choice)

---

## Table of Contents
1. [Setup Instructions](#setup-instructions)
2. [Database Initialization](#database-initialization)
3. [API Documentation](#api-documentation)
4. [Frontend Functionality](#frontend-functionality)
5. [Usage](#usage)

---

## Setup Instructions

### Backend Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>

2. Install Backend Dependencies:
cd backend
npm install

3. Environment Configuration: Create a .env file in the backend folder:
PORT=<your-server-port>
DATABASE_URL=<your-mongodb-connection-string>

4. Run Backend:
npm start

Frontend Setup
1. Navigate to Frontend Folder:
   cd frontend
2. Install Dependencies:
   npm install
3. Run Frontend:
   npm start

Database Initialization
Seed the Database
1. API Data Source:
   URL: https://s3.amazonaws.com/roxiler.com/product_transaction.json
   Request Method: GET
   Response Format: JSON
   
2. Endpoint:
   Route: GET /api/init
   Description: Fetches data from the third-party API to seed the database with initial transaction data.

API Documentation
1. List Transactions
 Route: GET /api/transactions
 Description: Returns a list of transactions with pagination and search capabilities.
Parameters:
month (required): Month (e.g., "January" to "December") to filter transactions by dateOfSale.
page (optional, default=1): Page number for pagination.
per_page (optional, default=10): Number of transactions per page.
search (optional): Search text to filter by title, description, or price.
2. Get Statistics
 Route: GET /api/statistics
 Description: Provides statistics for the selected month.
Parameters:
month (required): Month to filter transactions.
Response:
total_sales: Total sale amount.
total_sold: Total number of sold items.
total_unsold: Total number of unsold items.
3. Get Bar Chart Data
Route: GET /api/bar-chart
 Description: Returns data for a bar chart showing the number of items in various price ranges for the selected month.
Parameters:
month (required): Month to filter transactions.
Price Ranges:
0-100, 101-200, ..., 901+
4. Get Pie Chart Data
 Route: GET /api/pie-chart
 Description: Provides data for a pie chart showing unique product categories and item counts per category for the selected month.
Parameters:
month (required): Month to filter transactions.
5. Combined Data API
 Route: GET /api/combined
 Description: Combines responses from the statistics, bar-chart, and pie-chart endpoints into a single JSON response.

Usage
After setting up both backend and frontend, open the frontend in your browser. Select a month to view the transaction table, statistics, and charts. Use search and pagination to explore data further.

License
This project is licensed under the MIT License.
This `README.md` provides a comprehensive overview of your coding challenge project, including setup instructions, API documentation, and frontend features.
