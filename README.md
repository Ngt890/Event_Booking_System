# EventBookingSystem

A full-stack event booking system that allows users to browse, book, and manage event reservations. The solution includes a .NET backend, a modern static frontend, and unit/integration tests.

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Backend Setup](#backend-setup)
- [Frontend Setup](#frontend-setup)
- [Running Tests](#running-tests)
- [API Endpoints](#api-endpoints)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- User registration and authentication (JWT-based)
- Browse upcoming events
- Book and cancel event reservations
- View user-specific bookings
- Admin dashboard for event and booking management
- Responsive frontend UI

---

## Project Structure

```
EventBookingSystem/
│
├── AdminDashBoard/         # ASP.NET Core admin dashboard (UI & API)
├── Booking.Core/           # Core business models and interfaces
├── Booking.Repo/           # Data access layer (repositories, EF DbContext)
├── Bookings.Service/       # Business logic/services
├── DTOS/                   # Shared DTOs (Data Transfer Objects)
├── EventBookingSystem/     # Main ASP.NET Core Web API
├── frontend/               # Static frontend (HTML, CSS, JS)
├── unitTesting/            # xUnit test project
├── EventBookingSystem.sln  # Visual Studio solution file
└── README.md               # This file
```

---

## Backend Setup

1. **Requirements:**  
   - [.NET 8 SDK](https://dotnet.microsoft.com/download)
   - SQL Server (or update connection string for your DB)

2. **Restore & Build:**
   ```sh
   dotnet restore
   dotnet build
   ```

3. **Database Migration:**  
   Update your connection string in `appsettings.json` (in [AdminDashBoard/appsettings.json](AdminDashBoard/appsettings.json) or [EventBookingSystem/appsettings.json](EventBookingSystem/appsettings.json)), then run:
   ```sh
   dotnet ef database update --project EventBookingSystem/EventBookingSystem.csproj
   ```

4. **Run the API:**
   ```sh
   dotnet run --project EventBookingSystem/EventBookingSystem.csproj
   ```
   The API will be available at `https://localhost:5001` (or as configured).

---

## Frontend Setup

1. **Navigate to the frontend directory:**
   ```sh
   cd frontend
   ```

2. **Open `index.html` in your browser**  
   Or use the VS Code Live Server extension for local development.

3. **Configure API URL:**  
   Edit `frontend/js/config.js` to set the correct backend API base URL if needed.

---

## Running Tests

1. **Navigate to the test project:**
   ```sh
   cd unitTesting
   ```

2. **Run all tests:**
   ```sh
   dotnet test
   ```

---

## API Endpoints

> See Swagger UI at `/swagger` when running the backend for interactive API docs.

- `POST /api/auth/register` – Register a new user
- `POST /api/auth/login` – Authenticate and receive JWT
- `GET /api/events` – List all events
- `POST /api/bookings` – Book an event
- `GET /api/bookings/user/{userId}` – Get bookings for a user
- `DELETE /api/bookings/{bookingId}` – Cancel a booking

*(Endpoints may vary; see controllers in [AdminDashBoard/Controllers/](AdminDashBoard/Controllers/) and [EventBookingSystem/Controllers/](EventBookingSystem/Controllers/))*

---

## Technologies Used

- **Backend:** ASP.NET Core, Entity Framework Core, SQL Server
- **Frontend:** HTML, CSS, JavaScript
- **Testing:** xUnit, FluentAssertions, Moq, EFCore.InMemory
- **Other:** AutoMapper, JWT Authentication, Swagger

---

## Contributing

1. Fork the repo and create your branch (`git checkout -b feature/your-feature`)
2. Commit your changes (`git commit -am 'Add new feature'`)
3. Push to the branch (`git push origin feature/your-feature`)
4. Open a Pull Request

---

## License

This project is licensed under the MIT License.