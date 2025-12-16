# Todo API Backend

A RESTful API backend for a Todo application built with Node.js, Express, and MongoDB. Features full CRUD operations with validation and comprehensive testing.

## 🚀 Quick Start

### Prerequisites

- Node.js (v16+)
- MongoDB
- npm

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd deployable-todo-node-main

# Install dependencies
npm install

# Start development server
npm start
```

The API will be available at `http://localhost:4000`

## 🛠️ Tech Stack

- **Runtime**: Node.js with ES6 modules
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Validation**: Express Validator
- **Testing**: Mocha + Chai + Chai-HTTP
- **Coverage**: c8
- **CORS**: Enabled for cross-origin requests

## 📚 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | Get all todos |
| `POST` | `/` | Create a new todo |
| `PUT` | `/:id` | Update an existing todo |

### Example Requests

#### Get All Todos

```bash
GET http://localhost:4000/
```

#### Create Todo

```bash
POST http://localhost:4000/
Content-Type: application/json

{
  "todoDescription": "Complete project documentation",
  "todoDateCreated": "2023-09-11T13:19:00.000Z",
  "todoCompleted": false
}
```

#### Update Todo

```bash
PUT http://localhost:4000/:id
Content-Type: application/json

{
  "todoDescription": "Updated task description",
  "todoCompleted": true
}
```

## 📊 Data Model

### Todo Schema

```javascript
{
  todoDescription: String (required),
  todoDateCreated: Date (default: Date.now, required),
  todoCompleted: Boolean (required)
}
```

## 🧪 Testing

```bash
# Run all tests
npm test

# Run tests with coverage
npm run coverage
```

Tests include:

- GET all todos validation
- POST todo creation with validation
- PUT todo updates with error handling
- Database integration testing

## 📁 Project Structure

```text
src/
├── controllers/     # Request handlers
├── db/             # Database configuration and connection
├── middlewares/    # Validation middleware
├── models/         # Mongoose schemas
├── routes/         # API route definitions
└── services/       # Business logic
test/
├── testData/       # Sample test data
├── requests.http   # HTTP request examples
└── todos.test.js   # Test suite
```

## 🔧 Scripts

- `npm start` - Start development server with nodemon
- `npm test` - Run test suite with 10s timeout
- `npm run coverage` - Run tests with HTML coverage report

## 🌐 Environment Variables

### Development (.env.development)

```env
PORT=4000
HOST=localhost
DBURI=mongodb://127.0.0.1:27017/todos
```

### Testing (.env.test)

```env
PORT=4000
HOST=localhost
DBURI=mongodb://127.0.0.1:27017/todos_test
```

## ✅ Validation Rules

- `todoDescription`: Required string
- `todoDateCreated`: Required valid date
- `todoCompleted`: Required boolean

## 🚀 Deployment Ready

The application is structured for easy deployment with:

- Environment-based configuration
- Proper error handling
- CORS enabled
- Comprehensive test coverage

## 📄 License

ISC License
