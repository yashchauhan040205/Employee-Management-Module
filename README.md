# Employee Management System

A full-stack MERN (MongoDB, Express.js, React, Node.js) application for managing employee information with user authentication and role-based access control.

## Features

- User Authentication (Login/Registration)
- Role-based access control (Admin/User)
- Employee Management:
  - Create, Read, Update, Delete (CRUD) operations
  - Profile picture upload
  - Employee type selection
  - Detailed employee information
- Search and Filter:
  - Search by name or email
  - Filter by department and employee type
- Responsive Material-UI design

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (v4 or higher)
- npm or yarn package manager

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd employee-management-system
```

2. Install backend dependencies:
```bash
cd backend
npm install
```

3. Create a `.env` file in the backend directory with the following content:
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/employee-management
JWT_SECRET=your-super-secret-jwt-key
NODE_ENV=development
```

4. Install frontend dependencies:
```bash
cd ../frontend
npm install
```

## Running the Application

1. Start the MongoDB server:
```bash
mongod
```

2. Start the backend server:
```bash
cd backend
npm run dev
```

3. Start the frontend development server:
```bash
cd frontend
npm start
```

The application will be available at `http://localhost:3000`

## API Endpoints

### Authentication
- POST `/api/auth/register` - Register a new user
- POST `/api/auth/login` - Login user

### Employees
- GET `/api/employees` - Get all employees (with search and filter)
- GET `/api/employees/:id` - Get single employee
- POST `/api/employees` - Create new employee
- PUT `/api/employees/:id` - Update employee
- DELETE `/api/employees/:id` - Delete employee (admin only)

## Default Admin Account

To create an admin account, register a new user and manually update the role to 'admin' in the MongoDB database:

```javascript
db.users.updateOne(
  { email: "admin@example.com" },
  { $set: { role: "admin" } }
)
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License. 