## README: Running the Full-Stack Employee Management Application

This project is a **full-stack Employee Management System** built with **Spring Boot (backend) and React (frontend)**. It allows users to **view, add, and delete employees** from a database.

---

## 🛠 Prerequisites  
Before running the application, make sure you have:

- **Java 17+** (Check with `java -version`)
- **Node.js & npm** (Check with `node -v` and `npm -v`)
- **MySQL Database** (Ensure it's running)
- **Gradle** (Check with `gradle -v`)

---

## 🚀 Running the Backend (Spring Boot)  
### 1️⃣ Clone the repository (if not already done)
```bash
git clone <repo-url>
cd backend
```

### 2️⃣ Configure MySQL database  
- Open `src/main/resources/application.properties` and ensure your database settings are correct:
  ```properties
  spring.datasource.url=jdbc:mysql://localhost:3306/swe
  spring.datasource.username=root
  spring.datasource.password=yourpassword
  spring.jpa.hibernate.ddl-auto=update
  ```

### 3️⃣ Start MySQL (if not already running)  
```bash
mysql -u root -p
SHOW DATABASES;  # Ensure `swe` database exists
```
If missing, create it:
```sql
CREATE DATABASE swe;
```

### 4️⃣ Run the Spring Boot application  
```bash
./gradlew bootRun
```
- The backend will start on **`http://localhost:8081`**

---

## 🖥️ Running the Frontend (React)
### 1️⃣ Navigate to the frontend directory  
```bash
cd frontend
```

### 2️⃣ Install dependencies  
```bash
npm install
```

### 3️⃣ Start the frontend application  
```bash
npm start
```
- The React app will launch on **`http://localhost:3000`**

---

## 🔗 Testing the Application
1. Open **`http://localhost:3000`** in your browser.
2. Click **"Add Employee"** to create a new entry.
3. Click **"Delete"** to remove an employee.
4. Verify employees in MySQL:
   ```sql
   SELECT * FROM employees;
   ```

---

## ⚠️ Common Issues & Fixes
### ❌ Backend not starting?
- Ensure MySQL is running and the database `swe` exists.
- Check if **port 8081** is available, or change it in `application.properties`.

### ❌ Frontend Axios "Network Error"?
- Ensure the backend is running (`http://localhost:8081/api/employees` should return data).
- Check CORS settings in `WebConfig.java`.
- Verify `frontend/src/services/api.js` is pointing to the correct backend port.

---

## ✅ Summary
- **Backend (Spring Boot):** `./gradlew bootRun` (Runs on `http://localhost:8081`)
- **Frontend (React):** `npm start` (Runs on `http://localhost:3000`)
- **Database (MySQL):** Ensure `swe` exists and is configured properly.

🎉 **You’re ready to run the full-stack application!** 🚀
