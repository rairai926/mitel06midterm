
# EL106 Authentication API (Django + DRF)

**Author:** John Ryan Mag-usara  
**Contact:** magusara.johnryan@gmail.com  

A Django REST Framework-based RESTful API and graphical user interface designed for the MIT EL106 course.

---

## **Key Features**

- User Registration with Email Verification  
- JWT-based Login and Logout  
- Secured User Profile (JWT Authentication)  
- Password Reset via Email Link  
- Auto-generated Swagger API Documentation  
- Minimalist HTML + CSS Interface (Light Theme)

---

## **Installation Guide**

1. **Clone the repository and navigate to the project directory:**
   ```bash
   git clone <repo-url>
   cd el106_auth_api
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install required packages:**
   ```bash
   pip install django djangorestframework djangorestframework-simplejwt drf-yasg django-cors-headers
   ```

4. **Apply migrations and run the development server:**
   ```bash
   python manage.py migrate
   python manage.py runserver
   ```

5. **Access the app through your browser:**
   - GUI Home: [http://localhost:8000/](http://localhost:8000/)
   - Register: [http://localhost:8000/register/](http://localhost:8000/register/)
   - Login: [http://localhost:8000/login/](http://localhost:8000/login/)
   - Profile: [http://localhost:8000/profile/](http://localhost:8000/profile/)
   - Swagger Docs: [http://localhost:8000/swagger/](http://localhost:8000/swagger/)

---

## **Additional Notes**

- During development, all verification and password reset emails are displayed in the console.  
- Default database: SQLite (for faster setup).  
- To enable real email delivery, update your SMTP configuration in `el106_auth_api/settings.py`.

---

## **Typical User Flows**

### **Registration and Email Verification**
1. Register through `/register/`.  
2. Check your console for a verification link like:  
   ```
   http://localhost:8000/verify-email/?uid=1&token=<token>
   ```
3. Visit the link to activate your account.

### **JWT Authentication and Profile Access (API)**
1. Request a token:  
   ```
   POST /api/token/ 
   { "username": "youruser", "password": "..." }
   ```
2. Use the token for authenticated requests:  
   ```
   GET /api/profile/
   Authorization: Bearer <access_token>
   ```

---

