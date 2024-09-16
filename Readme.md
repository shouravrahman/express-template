# 🚀 Express.js TypeScript Authentication Template

A robust and scalable authentication template built with **Express.js**, **TypeScript**, **Prisma**, and **Passport.js**, this project is designed for rapid deployment of secure applications. It includes all the necessary functionality such as authentication, authorization, admin API, testing, caching, sanitization, validation, rate limiting, and comprehensive documentation.

## 🌟 Features

-   **JWT Authentication**: Secure token-based authentication using Passport.js.
-   **Role-based Authorization**: Easy to manage role-based access control (e.g., Admin, User).
-   **Prisma ORM**: Leverage the powerful Prisma ORM for interacting with databases.
-   **TypeScript**: Full TypeScript support for type safety and better development experience.
-   **Input Validation & Sanitization**: Built-in data validation with Zod and input sanitization.
-   **Rate Limiting**: Protect your API from abuse with flexible rate-limiting policies.
-   **Caching**: Boost performance with built-in caching using Redis or memory caching.
-   **Admin API**: Ready-to-use API for admin-level actions.
-   **Testing**: Comprehensive unit and integration tests using Jest and Supertest.
-   **API Documentation**: Auto-generated API documentation using Swagger.
-   **Security Best Practices**: Implementing key security features like helmet, CORS, and more.
-   **Dockerized Setup**: Ready for development and production environments using Docker.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/express-ts-prisma-auth-template.git

cd express-ts-prisma-auth-template `
```

### 2. Install dependencie

```
npm install
```

### 3. Set up environment variables

Create a `.env` file in the root directory:

```
DATABASE_URL="postgresql://user:password@localhost:5432/mydb"
JWT_SECRET="your-secret-key"
REDIS_URL="redis://localhost:6379"
RATE_LIMIT_MAX=100
```

### 4. Set up the database

Generate the Prisma client and migrate the database:

```
npx prisma migrate dev
```

### 5. Start the development server

```
npm run dev
```

The server will start at `http://localhost:3000`.

### 6. Run tests

To ensure everything is working as expected:

```
npm run test
```

## 📚 API Documentation

API documentation is automatically generated using **Swagger**. You can access the docs at:

```
http://localhost:3000/api/docs
```

## 🔑 Authentication and Authorization

The template provides a modular authentication system using Passport.js with **JWT** strategy.

-   **Login**: `/api/auth/login`
-   **Register**: `/api/auth/register`
-   **Protected Route**: Add the `authMiddleware` to protect your routes
-   **Admin Routes**: For admin-level actions, assign the appropriate roles and use the `adminMiddleware`.

## 🔧 Configuration

### Rate Limiting

The template includes rate limiting to prevent abuse. You can configure the max requests and window duration in the `.env` file:

```
RATE_LIMIT_MAX=100
RATE_LIMIT_WINDOW_MS=60000
```

### Caching

For caching, Redis is supported out of the box. You can switch to a memory store for development purposes.

### Validation & Sanitization

Input validation is done using **Zod**. Sanitization is applied to all user inputs to prevent XSS and SQL injections.

## 🛠️ Testing

Testing is powered by **Jest** and **Supertest** to ensure your application works as expected.

-   **Unit tests**: For individual function logic
-   **Integration tests**: To ensure the API endpoints are working correctly

To run tests:

```
npm run test
```

## 🚀 Production

For a production-ready setup, we have included a **Dockerfile** and **docker-compose.yml** for easy deployment. Build the production image and start the containers:

```
docker-compose up --build
```

## 📂 Folder Structure

```
├── src
│   ├── controllers  # API controllers
│   ├── middlewares  # Authentication, Error handling
│   ├── models       # Prisma ORM models
│   ├── routes       # API route definitions
│   ├── services     # Business logic and services
│   ├── tests        # Unit and integration tests
│   ├── utils        # Utility functions (validation, sanitization, etc.)
│   └── app.ts       # Main Express app entry
├── prisma           # Prisma database schema and migrations
├── docker-compose.yml  # Docker setup for dev/prod
├── Dockerfile       # Dockerfile for building the production image
└── README.md        # Project documentation`
```

## 📝 License

This project is licensed under the MIT License.

---

Feel free to contribute, report bugs, or request features! Happy coding! 💻
