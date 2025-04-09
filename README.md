# 📚 Assignment: Build an Online Bookstore (Laravel API + React Frontend)

## 🎯 Objective
Build a fullstack online bookstore application.  
- **Backend:** Laravel API (Laravel + Sanctum)  
- **Frontend:** React.js (fetch data from Laravel API)
- **Create** repo on your github.com and within repo add backend and frontend folders
- **Commit and push** when you finish working on checklist
---

## ✍️ Requirements

### Backend - Laravel API

1. **Authentication**
   - Laravel Sanctum for API token-based authentication.
   - Register, Login, Logout endpoints.

2. **Book Management**
   - Admin-only CRUD operations (Create, Read, Update, Delete).
   - Publicly list and search books.

3. **Order System**
   - Users can:
     - Add books to cart.
     - Place orders.
     - View and cancel their orders.

4. **API Endpoints (Examples)**

| Method | Endpoint                | Description                |
|--------|-------------------------|----------------------------|
| POST   | /api/register           | Register new user          |
| POST   | /api/login              | User login                 |
| POST   | /api/logout             | User logout                |
| GET    | /api/books              | List all books             |
| GET    | /api/books/{id}         | View book details          |
| POST   | /api/books              | Add book (Admin only)      |
| PUT    | /api/books/{id}         | Update book (Admin only)   |
| DELETE | /api/books/{id}         | Delete book (Admin only)   |
| POST   | /api/cart               | Add book to cart           |
| GET    | /api/cart               | View cart                  |
| POST   | /api/orders             | Place an order             |
| GET    | /api/orders             | View user orders           |

### Frontend - React

1. **Pages**
   - Homepage: List all books.
   - Book details page.
   - Register & Login pages.
   - Cart page.
   - Orders page.
   - Admin dashboard: Add / edit / delete books.

2. **Features**
   - User login & protected routes.
   - Book browsing & search.
   - Add to cart, view cart.
   - Place order.
   - View order history.

3. **Bonus (Optional)**
   - Pagination for book listings.
   - Toast notifications.
   - Responsive design (mobile-friendly).

---

## 🛠️ Tech Stack

### Backend
- Laravel 10+
- Laravel Sanctum
- MySQL

### Frontend
- React.js (Vite or Create React App)
- Axios (for API calls)
- React Router
- Tailwind CSS (optional but recommended)

---

## 🚀 Starter Pack

### Backend Setup (Laravel)

```bash
composer create-project laravel/laravel bookstore-api
cd bookstore-api
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\\Sanctum\\SanctumServiceProvider"
php artisan migrate
php artisan make:model Book -m
php artisan make:model Order -m
php artisan make:model OrderItem -m
php artisan make:controller API/BookController --api
php artisan make:controller API/AuthController
php artisan make:controller API/OrderController
php artisan make:controller API/CartController
```

> Don’t forget to add Sanctum middleware and seed your database!

### Frontend Setup (React)

```bash
# Using Vite
npm create vite@latest bookstore-frontend --template react
cd bookstore-frontend
npm install
npm install axios react-router-dom
npm run dev
```

### Folder Structure Suggestion

```
/src
  /components
    - BookList.jsx
    - BookDetail.jsx
    - Cart.jsx
    - OrderList.jsx
    - AdminDashboard.jsx
  /pages
    - Home.jsx
    - Login.jsx
    - Register.jsx
    - CartPage.jsx
    - OrdersPage.jsx
  /services
    - api.js (Axios config)
    - auth.js (Auth helper functions)
  App.jsx
  main.jsx
```

### Sample Axios API Config

```javascript
import axios from 'axios';

const api = axios.create({
  baseURL: 'http://localhost:8000/api',
  withCredentials: true,
});

export default api;
```

### Sample Login Request

```javascript
import api from './api';

export const login = async (email, password) => {
  const response = await api.post('/login', { email, password });
  return response.data;
};
```

---

## ✅ Evaluation Checklist

| Feature                         | Points |
|---------------------------------|---------|
| Laravel API with Sanctum         | ✅      |
| React frontend setup             | ✅      |
| Auth system (register/login)     | ✅✅     |
| Book CRUD (admin)                | ✅✅     |
| Book listing & search            | ✅      |
| Add to cart / Place order        | ✅✅     |
| View order history               | ✅      |
| Responsive & clean UI            | ⭐️     |
| API integration (Axios)          | ✅      |
| Bonus: Pagination, Toast, etc.   | ⭐️     |



---

## 📦 Delivery Instructions

- ✅ Push **both** Laravel API and React code to GitHub.
- ✅ Submit API collection or documentation (Postman or Swagger).
- ✅ Include README in both repos:
  - Project description
  - Setup & installation steps
  - Migration and seeding commands
  - How to run frontend & backend
  - API usage

---

### 🚀 Good Luck, and happy coding!

If you get stuck, post in the class discussion or ask for help!


