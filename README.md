# ExpressTeaAPI

## Overview
TeaTimeAPI is a simple RESTful API built with Node.js and Express. It allows users to manage a collection of teas by adding, updating, deleting, and retrieving tea data. This project also demonstrates structured logging using Morgan and Winston for better log management.

## Features
- **Add Tea**: Add a new tea with a name and price.
- **Retrieve Teas**: Get a list of all available teas.
- **Retrieve Tea by ID**: Get details of a specific tea using its unique ID.
- **Update Tea**: Update the details of an existing tea by its ID.
- **Delete Tea**: Remove a tea from the collection by its ID.
- **Structured Logging**: Logs requests in JSON format with essential details (method, endpoint, status, and response time).

## Technologies Used
- **Node.js**: JavaScript runtime environment.
- **Express**: Web framework for building APIs.
- **Morgan**: HTTP request logger middleware.
- **Winston**: Logger for structured log management.

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/TeaTimeAPI.git
   ```
2. Navigate to the project directory:
   ```bash
   cd TeaTimeAPI
   ```
3. Install the dependencies:
   ```bash
   npm install
   ```
4. Create a `.env` file for environment variables (if required).

## Usage
1. Start the server:
   ```bash
   npm start
   ```
2. The server will run on `http://localhost:8000`.

## Endpoints
### 1. Add a New Tea
**POST** `/teas`
- **Request Body**:
  ```json
  {
    "name": "Green Tea",
    "price": 5.99
  }
  ```
- **Response**:
  ```json
  {
    "id": 1,
    "name": "Green Tea",
    "price": 5.99
  }
  ```

### 2. Get All Teas
**GET** `/teas`
- **Response**:
  ```json
  [
    {
      "id": 1,
      "name": "Green Tea",
      "price": 5.99
    }
  ]
  ```

### 3. Get a Tea by ID
**GET** `/teas/:id`
- **Response (Success)**:
  ```json
  {
    "id": 1,
    "name": "Green Tea",
    "price": 5.99
  }
  ```
- **Response (Error)**:
  ```json
  "Chai nhi mili"
  ```

### 4. Update a Tea
**PUT** `/teas/:id`
- **Request Body**:
  ```json
  {
    "name": "Matcha",
    "price": 6.99
  }
  ```
- **Response**:
  ```json
  {
    "id": 1,
    "name": "Matcha",
    "price": 6.99
  }
  ```
- **Response (Error)**:
  ```json
  "chai nhi mili"
  ```

### 5. Delete a Tea
**DELETE** `/teas/:id`
- **Response (Success)**:
  ```json
  "deleted"
  ```
- **Response (Error)**:
  ```json
  "chai nhi mili"
  ```

## Logging
The API uses Morgan to log HTTP requests. Logs are formatted as JSON and include:
- Method (e.g., GET, POST)
- URL (e.g., /teas)
- Status Code (e.g., 200, 404)
- Response Time (e.g., 15ms)

Example log entry:
```json
{
  "method": "GET",
  "url": "/teas",
  "status": "200",
  "responseTime": "15ms"
}
```

## Notes
- **Backend Principles**:
  - If you aren’t measuring it, you can’t improve it.
  - If you aren’t testing it, you can’t trust it.
  - If you aren’t documenting it, you can’t maintain it.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

