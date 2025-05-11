
# 🏫 school-manager-api

A Node.js and Express-based RESTful API to manage school data, including adding schools and retrieving a list of schools sorted by proximity to a user-specified location. Uses MySQL for data storage.

---

## 📦 Features

- Add new schools with name, address, and coordinates
- Retrieve and sort schools by distance from user location
- RESTful endpoints with input validation
- Compatible with deployment platforms like Render and Railway
- Basic HTML interface for form-based interaction

---

## 🚀 Live Deployment

🌐 **API URL**: [https://school-manager-api-production.up.railway.app]
   **API URL FOR LIST SCHOOL**:[https://school-manager-api-production.up.railway.app/listSchools?latitude=20&longitude=21]
   -> Latitute And Longitude values can be changed from the param.
---

## 🛠️ Technologies Used

- **Node.js**
- **Express.js**
- **MySQL**
- **dotenv**
- **body-parser**
- **HTML/CSS (for basic UI)**

---

## 🧩 Database Schema

```sql
CREATE TABLE schools (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255),
  address VARCHAR(255),
  latitude FLOAT,
  longitude FLOAT
);
```

---

## 📂 API Endpoints

### ➕ `POST /addSchool`

Adds a new school to the database.

**Request Body (JSON):**

```json
{
  "name": "Ryan International",
  "address": "Jaipur",
  "latitude": 26.9124,
  "longitude": 75.7873
}
```

**Response:**
```json
{
  "message": "School added successfully"
}
```

---

### 📍 `GET /listSchools`

Returns all schools sorted by proximity to the given location.

**Query Parameters:**

- `latitude` – user's latitude
- `longitude` – user's longitude

**Example:**

```
GET /listSchools?latitude=26.9&longitude=75.8
```

**Response:**
```json
[
  {
    "id": 1,
    "name": "Ryan International",
    "address": "Jaipur",
    "latitude": 26.9124,
    "longitude": 75.7873,
    "distance": 1.38
  }
]
```

---

## 🧪 Postman Collection

Use the link below to test all endpoints:

🔗 **[Postman Collection](https://drive.google.com/file/d/1uo0wqVSpjsP8PAEnMLd-vEIFWTKD7e8R/view?usp=sharing)**

---

## ⚙️ Running Locally

1. Clone this repo:
   ```bash
   git clone https://github.com/Raashika0201/school-manager-api.git
   cd school-management-api
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create `.env` file in root with your MySQL credentials:
   ```env
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=yourpassword
   DB_NAME=school_db
   ```

4. Start the server:
   ```bash
   node app.js
   ```

5. Visit: [http://localhost:3000]

---

## 🌐 Deploying on Railway

1. Push this repo to GitHub
2. Go to [Railway](https://railway.app)
3. Create a project → Deploy from GitHub
4. Add a **MySQL plugin** (Railway-hosted DB)
5. Set environment variables in your service
6. Railway gives you a public API URL to share!

---
## 🙋‍♂️ Author

**Your Name**  
GitHub: [@raashika0201](https://github.com/raashika0201)

