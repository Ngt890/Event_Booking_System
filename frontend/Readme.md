# Eventat - Event Booking System Frontend

Welcome to **Eventat**! This is the frontend for an event booking system, built as a modern, responsive static web app. Users can browse events, register/login, and book events with a beautiful UI.

---

## 🚀 Features

- **Browse Events:** View a list of upcoming events with details and images.
- **User Authentication:** Register and log in securely (JWT-based).
- **Book Events:** Book your favorite events with a single click.
- **My Bookings:** View your bookings in a stylish dashboard.
- **Responsive Design:** Works great on desktop and mobile.
- **Modern UI:** Built with Poppins font, Font Awesome icons, and custom CSS.

---

## 📁 Project Structure

```
frontend/
│
├── index.html                # Main landing page
├── css/
│   └── styles.css            # Main stylesheet
├── js/
│   ├── auth.js               # Authentication logic
│   ├── events.js             # Event listing & booking logic
│   ├── mybookings.js         # My Bookings page logic
│   ├── main.js               # UI helpers, notifications, menu
│   └── config.js             # API base URL
├── pages/
│   ├── login.html            # Login page
│   ├── signup.html           # Registration page
│   └── mybookings.html       # User's bookings page
└── package.json              # For static server (optional)
```

---

## 🖥️ How to Run Locally

1. **Clone or Download** this repository.

2. **Navigate to the frontend directory:**
   ```bash
   cd path/to/EventBookingSystem/frontend
   ```

3. **Start a static server:**
   - With Node.js:
     ```bash
     npx serve .
     ```
   - With Python:
     ```bash
     python -m http.server 8080
     ```
   - Or use the VS Code **Live Server** extension (right-click `index.html` → "Open with Live Server").

4. **Open your browser and go to:**
   ```
   http://localhost:8080/
   ```
   - Main page: `/index.html`
   - Login: `/pages/login.html`
   - Signup: `/pages/signup.html`
   - My Bookings: `/pages/mybookings.html`

---

## 🔗 Backend API Integration

- The frontend expects the backend API to be running and accessible at the URL specified in [`js/config.js`](js/config.js).
- All API requests are made to endpoints like:
  - `/api/Accounts/login`
  - `/api/Accounts/Register`
  - `/api/Events`
  - `/api/Bookings/CreateBooking`
  - `/api/Bookings/GetBooking/{id}`
- JWT tokens are required for protected endpoints and are automatically attached by the frontend.

---

## 📝 Customization

- **API Base URL:**  
  Set your backend API URL in [`js/config.js`](js/config.js):
  ```js
  const API_BASE_URL = 'http://localhost:5264';
  ```

- **Styling:**  
  All styles are in [`css/styles.css`](css/styles.css).  
  You can easily adjust colors, fonts, and layout.

---

## 🛠️ Troubleshooting

- **404 errors for JS/CSS:**  
  Make sure you are running the server from the `frontend` directory and all files exist in their correct folders.

- **CORS issues:**  
  The backend must allow requests from the frontend's origin (handled by CORS policy in the backend).

- **Token/auth issues:**  
  Ensure the backend is running and the API base URL is correct in `config.js`.

---

## 📄 License

This project is for educational/demo purposes.  
Feel free to use and modify as needed.

---

## 🙏 Credits

- [Google Fonts - Poppins](https://fonts.google.com/specimen/Poppins)
- [Font Awesome](https://fontawesome.com/)
- All contributors and open-source libraries used.

---

Enjoy using **Eventat**!  
If you have any questions or suggestions, feel free to open an issue or contact the maintainer.