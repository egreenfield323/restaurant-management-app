# 🍽️ Restaurant Management App

A Vue.js-based restaurant management application that uses a mock REST API via JSON Server.

## 🛠️ Tech Stack

- [Vue 3](https://vuejs.org/)
- [JSON Server](https://github.com/typicode/json-server)

---

## 🚀 Getting Started

Follow the steps below to run both the frontend Vue project and the JSON backend server locally.

### 1. Clone the Repository

```bash
git clone https://github.com/egreenfield323/restaurant-management-app.git
cd Project/restaurant-management-app
```

---

## ⚙️ JSON Server Setup

The app uses [JSON Server](https://github.com/typicode/json-server) to mock a backend API.

### 🔧 Install JSON Server

If you don’t already have it installed globally:

```bash
npm install -g json-server
```

### ▶️ Run JSON Server

From the project root directory:

```bash
json-server --watch db.json --port 3000
```

- The data lives in `db.json`.
- The server will run at: [http://localhost:3000](http://localhost:3000)

---

## 💻 Running the Vue App

### 📦 Install Dependencies

```bash
npm install
```

### 🏃 Start the Development Server

```bash
npm run serve
```

- The Vue app will typically be available at: [http://localhost:8080](http://localhost:8080)
- Make sure JSON Server is running on port 3000 for API calls to succeed.