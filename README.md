# OneClinic.vet

## Table of Contents

1. [📌 Overview](#-overview)
2. [🧰 Tech Stack](#-tech-stack)
3. [📁 Folder Structure](#-folder-structure)
4. [## Key Features](#key-features)
5. [## Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Environment Setup](#environment-setup)
   - [Installation](#installation)
   - [Development](#development)
   - [Production Build](#production-build)
6. [## Environment Variables](#environment-variables)
7. [## API Endpoints](#api-endpoints)
   - [Authentication & Session Management](#authentication--session-management)
   - [User Registration & Account Management](#user-registration--account-management)
   - [Clinic & Pet Management](#clinic--pet-management)
   - [Notifications](#notifications)
   - [Other Endpoints](#other-endpoints)
8. [## Key Components and Pages](#key-components-and-pages)
   - [Main Pages](#main-pages)
   - [Important Components](#important-components)
9. [## Data Flow](#data-flow)
10. [## API Integration](#api-integration)
11. [📦 Key Dependencies](#-key-dependencies)
12. [🧠 State Management (Redux Toolkit)](#-state-management-redux-toolkit)
13. [👤 Maintainer](#-maintainer)

## 📌 Overview

**OneClinic.Vet** is a web-based platform designed to streamline the operations of veterinary clinics, helping clinic staff manage appointments, medical records, invoicing, and communication with pet owners in an efficient, digital environment. By automating administrative tasks, offering secure access to pet health records, and facilitating easy communication, the platform aims to improve clinic efficiency, reduce errors, and enhance the overall user experience for both clinic staff and pet owners. With features like multi-language support and responsive design, OneClinic.Vet is built to meet the needs of modern veterinary practices.

## 🧰 Tech Stack

- **Frontend Framework**: React (v18)
- **State Management**: Redux Toolkit
- **Styling**: TailwindCSS + SCSS
- **Routing**: React Router DOM
- **Form Handling**: React Hook Form
- **Analytics**:Google Analytics
- **Maps**: Google Maps API (`@react-google-maps/api`)
- **Auth & Data**: Firebase
- **Notifications**: React Toastify
- **Misc UI**: MUI (Material UI), Emotion, Framer Motion

---

## 📁 Folder Structure

<details>
<summary><strong>Click to expand</strong></summary>

src
│
├── App.js
├── App.scss
├── firebase.js
├── Fr.js
├── index.css
├── index.js
├── index.scss
├── logo.svg
├── structure.txt
│
├── app/
│ └── store.js
│
├── assets/
│ ├── Icons/
│ │ ├── Add-icon.png
│ │ ├── addIcon.svg
│ │ ├── AddRed.svg
│ │ └── ... (other icon files)
│ ├── Images/
│ │ ├── campany_banner.jpg
│ │ ├── customer_banner.jpg
│ │ ├── google.png
│ │ └── ... (other image files)
│ └── Logos/
│ ├── bottom.png
│ ├── logo-black.png
│ └── logo-white.png
│
├── components/
│ ├── admin/
│ │ └── Dashboard.js
│ ├── client/
│ │ ├── Home.js
│ │ ├── Insicription.js
│ │ ├── account/
│ │ │ ├── Change.js
│ │ │ ├── ClientPreInfo.js
│ │ │ ├── CompanyPreInfo.js
│ │ │ └── ... (other account files)
│ │ ├── clinic/
│ │ │ ├── Account.js
│ │ │ ├── AnimalDetail.js
│ │ │ ├── Animals.js
│ │ │ └── ... (other clinic files)
│ │ ├── common/
│ │ │ ├── AnimalAutoComplete.js
│ │ │ ├── Banner.js
│ │ │ ├── Footer.js
│ │ │ └── ... (other common components)
│ │ ├── customer/
│ │ │ ├── Account.js
│ │ │ ├── AddAnimal.js
│ │ │ └── ... (other customer files)
│ │ ├── search/
│ │ │ ├── General.js
│ │ │ ├── Confirm.js
│ │ │ └── ... (other search files)
│ │ └── ... (other client-related files)
│ └── ... (other components like admin, common, etc.)
│
├── config/
│ ├── axios.js
│ ├── Translate.js
│ └── variables.js
│
├── features/
│ ├── AnimalsListChange.js
│ ├── LanguageSlice.js
│ ├── SearchSlice.js
│ └── ... (other feature-related files)
│
├── helper/
│ ├── Auth/
│ │ ├── BookingRedirect.js
│ │ ├── ProtectedRoute.js
│ │ └── ... (other auth files)
│ ├── Dictionary/
│ │ ├── En.js
│ │ ├── Fr.js
│ │ └── ... (other dictionary files)
│ ├── Loader/
│ │ └── Loader.js
│ ├── Message/
│ │ ├── ErrorToast.js
│ │ ├── FormErrors.js
│ │ └── ... (other message files)
│ ├── Modal/
│ │ └── Modal.js
│ ├── Url.js
│ └── MobileRedirect.js
│
├── hooks/
│ ├── useScrollToTop.js
│ └── useUnsavedChange.js
│
├── pages/
│ ├── client/
│ │ ├── Home.js
│ │ ├── CustomerDashboard.js
│ │ ├── account/
│ │ │ ├── Change.js
│ │ │ └── ... (other account pages)
│ │ ├── clinic/
│ │ │ ├── ClinicDashboard.js
│ │ │ └── ... (other clinic pages)
│ │ ├── contact-us/
│ │ │ └── ContactUs.js
│ │ ├── customer/
│ │ │ ├── Board.js
│ │ │ └── ... (other customer pages)
│ │ ├── search/
│ │ │ ├── GeneralSearchCard.js
│ │ │ └── ... (other search pages)
│ │ └── ... (other client-related pages)
│ └── ... (other pages)
│
├── styles/
│ ├── client/
│ │ ├── account/
│ │ │ ├── Change.scss
│ │ │ └── ... (other account styles)
│ │ ├── clinic/
│ │ │ ├── GridTimetable.scss
│ │ │ └── ... (other clinic styles)
│ │ ├── common/
│ │ │ ├── Banner.scss
│ │ │ ├── Footer.scss
│ │ │ └── ... (other common styles)
│ │ ├── customer/
│ │ │ ├── Dashboard.scss
│ │ │ └── ... (other customer styles)
│ │ ├── home/
│ │ │ └── Home.scss
│ │ └── search/
│ │ └── General.scss
│ └── ... (other style directories)
│
└── ... (other files and directories)

</details>

---

## Key Features

- **General**:

  - Multi-language support (French at launch, with plans for more languages).
  - Responsive design optimized for desktops, tablets, and mobile devices.
  - Secure user authentication with encrypted data storage.
  - Automated system updates for future improvements.

- **Client Portal**:

  - Book, reschedule, or cancel appointments.
  - Access and manage pet health records (future feature).
  - Receive real-time updates and appointment reminders.
  - Secure communication with clinic staff.
  - View nearby clinics and search based on location.

- **Clinician Portal**:

  - Manage clinic hours, appointment scheduling, and availability.
  - Access and organize pet medical records (future feature).
  - Generate and send invoices to pet owners.
  - Manage patient histories and appointment details.
  - Send reminders and notifications to pet owners.

## Getting Started

### Prerequisites

To get started with the project, make sure you have the following installed:

- **Node.js** version 18 or higher.
- **PostgreSQL** for database management.
- **Firebase** for authentication and real-time updates.
- **Git** for version control.

### Environment Setup

Follow these steps to set up your environment:

1. Clone the repository using the following command:

   ```bash
   git clone <repository-url>
   ```

2. Copy the .env.example file to a new .env file:

```bash
cp .env.example .env
```

3. Update the .env file with your environment-specific variables (e.g., database credentials, Firebase configurations).

### Installation

Install the necessary dependencies by running:

```bash

npm install
```

If you face any issues during installation, try running the following command to force the installation:

```bash
npm install --force
```

### Development

To start the development environment, use the following command:

```bash

npm run start:test
```

This will run the application locally, and you can begin developing with live updates.

### Production Build

To prepare the project for production, build the optimized version of the app using:

```bash
npm run build
```

Once the build is complete, you can deploy it to your chosen environment.

## Environment Variables

The following environment variables need to be configured in the `.env.example` file:

- `REACT_APP_BASE_URL_PROD`: The production base URL for the application.
  - Example:
    ```bash
    REACT_APP_BASE_URL_PROD=https://oneclinic.shopveto.ch
    # or
    REACT_APP_BASE_URL_PROD=https://v1.oneclic.vet
    ```

Make sure to uncomment and update the correct URL for your production environment in the `.env` file.

## API Endpoints

The following API endpoints are used in the OneClinic.Vet application to handle various user interactions like authentication, session verification, and other functionalities.

### Authentication & Session Management

- **POST /verify-session**
  - **Description**: Verifies the current user session.
  - **Method**: `POST`
  - **Request Body**:
    ```json
    {
      "username": "ikramqazidev@oneclinic.vet",
      "password": "ThisIsAFakePassword"
    }
    ```
  - **Response**:
    - **200 OK**: Session is valid, returns user data.
    - **401 Unauthorized**: Invalid credentials.

### User Registration & Account Management

- **POST /register**

  - **Description**: Registers a new user (both client and clinic).
  - **Method**: `POST`
  - **Request Body**:
    ```json
    {
      "email": "ikramqazidev@oneclinic.vet",
      "password": "ThisIsAFakePassword",
      "role": "client" // or "clinic"
    }
    ```
  - **Response**:
    - **201 Created**: User registered successfully.
    - **400 Bad Request**: Invalid data or missing fields.

- **POST /login**
  - **Description**: Logs in an existing user.
  - **Method**: `POST`
  - **Request Body**:
    ```json
    {
      "email": "ikramqazidev@oneclinic.vet",
      "password": "ThisIsAFakePassword"
    }
    ```
  - **Response**:
    - **200 OK**: Returns authentication token (JWT).
    - **401 Unauthorized**: Invalid credentials.

### Clinic & Pet Management

- **GET /clinics/{clinicId}**

  - **Description**: Retrieves details of a specific clinic.
  - **Method**: `GET`
  - **Response**:
    - **200 OK**: Returns clinic details such as name, address, and services.
    - **404 Not Found**: Clinic not found.

- **POST /clinics/{clinicId}/appointments**
  - **Description**: Books a new appointment for a pet.
  - **Method**: `POST`
  - **Request Body**:
    ```json
    {
      "petId": "123",
      "appointmentDate": "2025-06-01T10:00:00",
      "service": "General Checkup"
    }
    ```
  - **Response**:
    - **201 Created**: Appointment successfully booked.
    - **400 Bad Request**: Invalid data or unavailable slot.

### Notifications

- **GET /notifications**
  - **Description**: Retrieves all notifications for the authenticated user.
  - **Method**: `GET`
  - **Response**:
    - **200 OK**: Returns a list of notifications (appointments, reminders, etc.).
    - **204 No Content**: No notifications available.

### Other Endpoints

- **POST /contact-us**
  - **Description**: Submits a contact form from the user.
  - **Method**: `POST`
  - **Request Body**:
    ```json
    {
      "name": "Ikram Qazi",
      "email": "ikramqazidev@oneclinic.vet",
      "message": "I have an inquiry about services."
    }
    ```
  - **Response**:
    - **200 OK**: Successfully submitted the contact request.
    - **400 Bad Request**: Invalid data.

## Key Components and Pages

### Main Pages

The following pages are essential for the application’s core functionality:

- **Home Page** (`Home.js`): The landing page for the app, displaying general information and navigation options.
- **Login Page** (`Login.js`): Allows users to log in to their account.
- **Register Page** (`Register.js`): Used for registering new users, including both clients and clinics.
- **Clinic Dashboard Page** (`ClinicDashboard.js`): The main page for clinics to manage their profile, services, and appointments.
- **Customer Dashboard Page** (`CustomerDashboard.js`): The main page for customers to manage their animals, appointments, and personal information.
- **Account Pages** (`Change.js`, `Forget.js`, `Reset.js`): Pages related to user account management (e.g., password reset, account modification).
- **Search Page** (`General.js`): Allows users to search for clinics and services based on various filters.
- **Appointment Pages** (`Rendezvous.js`, `Booking.js`, `Confirmed.js`): Manage appointment scheduling, confirmation, and status tracking.

These pages are primarily responsible for user interactions and presenting data in an organized and user-friendly manner.

### Important Components

The application relies on several reusable components for consistent UI and functionality:

- **Banner Component** (`Banner.js`): Displays a promotional or informational banner at the top of pages.
- **Footer Component** (`Footer.js`): The footer section with links, copyright information, etc.
- **Sidebar Component** (`Sidebar.js`): A navigation sidebar for clinics and customers to access different sections of the platform.
- **Animal List Component** (`Animals.js`): Allows customers to view and manage their pets' details.
- **Clinic Services Component** (`Services.js`): Displays and manages the available services in a clinic.
- **TimeTable Component** (`TimeTable.js`): Allows clinics to manage their available timeslots for appointments.
- **Modal Component** (`Modal.js`): Reusable modal component for displaying information or confirmation dialogs.

These components handle specific functionality and UI elements throughout the app.

---

## Data Flow

The flow of data between components and backend services is a crucial part of the application. Here’s an overview of how data moves through the app:

### User Authentication Flow:

1. **Login**: When a user enters their credentials on the Login Page, the data is sent via a POST request to the backend’s **authentication endpoint**.
2. **Session Verification**: After successful login, the backend returns a session token (JWT), which is stored in local storage or cookies. This token is sent with each subsequent request to authenticate the user.
3. **Protected Routes**: Certain pages like `CustomerDashboard` and `ClinicDashboard` are protected. These pages check for the session token before allowing access.

### Appointment Management Flow:

1. **Booking Appointment**: When a user books an appointment through the `Booking.js` page, the appointment data (e.g., pet ID, clinic ID, service) is sent to the backend via a POST request.
2. **Appointment Confirmation**: Once the appointment is confirmed, a notification is triggered for the user (via Firebase or similar service), and the appointment status is updated in the database.
3. **Status Updates**: The customer or clinic is notified about status changes (e.g., canceled or rescheduled appointments) through real-time updates via WebSockets or Firebase.

### Data Syncing:

1. **Real-Time Sync**: The app uses Firebase for real-time syncing of data such as appointment statuses, clinic schedules, and notifications.
2. **Persistent Storage**: User data (e.g., animals, appointments) is stored in the database (PostgreSQL), and the data is persisted even after the app reloads.

---

## API Integration

The application integrates with several APIs to interact with the backend services. Below are some of the key API endpoints and their purposes:

### Authentication APIs

- **POST /register**: Registers a new user or clinic.

  - Sends user data (name, email, password) to the backend to create an account.
  - **Response**: Returns a success message or validation error.

- **POST /login**: Authenticates a user or clinic.

  - Sends login credentials (email, password) to the backend to verify the user.
  - **Response**: Returns a JWT token for session management.

- **POST /verify-session**: Verifies the current session of a logged-in user.
  - **Response**: Returns user data if the session is valid, or an error if not.

### Appointment APIs

- **POST /appointments**: Books a new appointment.

  - Sends appointment data (pet ID, service, clinic ID, date/time) to the backend.
  - **Response**: Returns appointment details, including confirmation and status.

- **GET /appointments**: Retrieves all appointments for the authenticated user (customer or clinic).

  - **Response**: Returns a list of appointments with their details.

- **DELETE /appointments/{id}**: Cancels an existing appointment.
  - **Response**: Returns a success or error message.

### Clinic APIs

- **GET /clinics/{clinicId}**: Retrieves the details of a specific clinic.

  - **Response**: Returns clinic data such as name, services, and schedule.

- **POST /clinics/{clinicId}/services**: Adds a new service to the clinic.
  - **Response**: Returns the updated list of services.

### Notification APIs

- **POST /notifications**: Sends a new notification (e.g., appointment reminder).

  - **Response**: Returns the status of the notification.

- **GET /notifications**: Retrieves notifications for the authenticated user.
  - **Response**: Returns a list of notifications (e.g., upcoming appointments, clinic updates).

These endpoints ensure that users can interact with the platform, book appointments, manage clinic details, and receive real-time updates.

---

## 📦 Key Dependencies

| Library                           | Purpose            |
| --------------------------------- | ------------------ |
| `@mui/material`, `@emotion/react` | UI components      |
| `@reduxjs/toolkit`, `react-redux` | Global state       |
| `react-router-dom`                | Routing            |
| `react-hook-form`                 | Form handling      |
| `firebase`                        | Auth, storage      |
| `@react-google-maps/api`          | Maps               |
| `axios`                           | HTTP requests      |
| `redux-persist`                   | State persistence  |
| `framer-motion`                   | Animations         |
| `react-toastify`                  | Notifications      |
| `nprogress`                       | Loading indicators |

---

## 🧠 State Management (Redux Toolkit)

Redux is set up in `src/app/store.js`.

### 🔍 Important Slices

- `UserInfoSlice` – User authentication and profile
- `SearchSlice` – Search filters and results
- `StepsSlice` – Multi-step form state
- `LanguageSlice` – i18n language preference
- `counterSlice` – (Demo/test purpose)

## External Services

Our website uses some helpful external tools and services to work better:

### 1. Google Maps API

- **What it does:** Shows maps and helps find nearby vets.
- **How we use it:** We add maps and location features so you can see vets close to you.

### 2. Google Fonts

- **What it does:** Provides nice-looking text styles (fonts) for our website.
- **How we use it:** We use two fonts called Poppins and Open Sans to make the text easy to read and look good.

### 3. Font Awesome

- **What it does:** Gives us cool icons like little pictures for buttons and menus.
- **How we use it:** We include icons to make the website easier to use and look nicer.

### 4. Marker.io

- **What it does:** Helps us collect feedback and bug reports from users during testing.
- **How we use it:** When we're testing the site (not the live version), this tool helps catch problems faster.

### 5. Google Tag Manager

- **What it does:** Helps manage website tracking and analytics without changing the website code all the time.
- **How we use it:** We track visits and user actions to improve the website and services.

## 👤 Maintainer

**[Ikram Qazi]**
Junior Front-End Developer — OneClinic.Vet

## Important Functions and Pages

### Login / Register

**Login.jsx**  
Handles user login with email/password and Google OAuth. Manages form validation, submission, and redirects based on account type and verification status. Displays booking info if present.

**Register.jsx**  
Manages user registration with form validation and server submission. Shows success or error messages and redirects to verification page after successful registration.

**Verify.jsx (Client)**  
Verifies user account via 6-digit OTP input. Handles OTP submission, error handling, resend code, and redirects after successful verification.

**Forget.jsx**  
Provides password reset by email. Handles form submission and displays success or error notifications. Shows booking details if present.

**VetVerify.jsx**  
Similar to Verify.jsx but styled and configured for veterinarian account verification with OTP, including resend and submission handling.

**CompanyPreInfo.jsx**  
Manages clinic user info update with form inputs for contact and facility details. Fetches existing data, auto-updates geolocation via Google Maps API on address changes, and submits updates via API. Includes phone input with validation and displays success/error toasts.

**Change.jsx**  
Handles user password change with validation on current and new passwords. Submits changes to backend and shows success or error notifications. Redirects to home page on success.

**ClientPreInfo.jsx**  
Displays and updates client user profile info including personal and address details. Fetches initial data and allows form editing with validation. Submits updates to backend and navigates based on booking info. Uses toast notifications for feedback.

### Home

**Home.jsx**  
Renders the home page with two sections: one for pet owners to book appointments (navigates internally) and one for veterinarians to learn more (opens external link). Uses `useNavigate` for routing and `Fade` for image animations.

### Clinic Account and Management Components

**Account.jsx**  
Manages clinic user account updates including email and password changes. Supports different forms based on authentication type (normal or social login). Provides real-time validation with react-hook-form and feedback via toast notifications. Password visibility toggles included.

**AnimalDetail.jsx**  
Displays detailed pet information with editable forms for medical, lifestyle, and identification data. Calculates pet age from birthdate. Uses API calls to fetch and update pet data with loading states and error handling.

**Animals.jsx**  
Lists clinic animals with clickable cards for details and a button to add new animals. Simple UI with static images and navigation handlers.

**Board.jsx**  
Clinic dashboard showing veterinarians and today's appointments. Fetches providers and appointment data on load, formats and displays info with images and icons. Provides navigation to vet profiles and appointment details. Handles loading and empty states gracefully.

**ClinicActivePageContent.jsx**  
Shows active clinic details including timetable, veterinarians, services, contact info, and a map. Fetches data via parallel API calls, manages loading states. Formats phone numbers and URLs. Includes booking info dispatch to Redux and navigation to booking page.

**ClinicDashboard.jsx**  
Wrapper dashboard component with sidebar and navigation. Checks clinic info on mount, redirects if incomplete. Highlights active navigation item based on route.

**ClinicInactivePageContent.jsx**  
Displays inactive clinic info with working hours, contact details, and map. Shows messaging encouraging clinic owner to register on platform. Uses local clinic data and formats contact info. Includes detailed working hours with morning/afternoon sessions.

**MyclinicInfo.jsx**  
Manages clinic profile and contact person info with dual forms. Features address autocomplete with Google Maps geocoding, map display, photo upload, and social links. Uses react-hook-form for validation, blocks navigation on unsaved changes, and shows success/error toasts.

**Rendezvous.jsx**  
Displays clinic appointments with filtering by animal, vet, date, and client. Supports today’s and all appointments views. Allows deleting appointments with confirmation and toast feedback. Uses custom cards and icon-enhanced search inputs.

### Services Management Component

**Services.jsx**  
Manages clinic services with listing, adding, editing, duplicating, and deleting functionalities. Features multi-step form with service details, schedule, and assigned vets. Supports image uploads and real-time validation with toast notifications. Includes navigation blocking on unsaved changes, search filter for vets, and toggling views for better UX. Uses Axios for API calls and Material UI modal for confirmation dialogs.

**Service Add**  
Facilitates the creation of new services for clinics. Includes form fields for service name, description, duration, and images. Supports file uploads with image preview and multi-step service details. Allows for species and providers selection. Handles form validation and toggles visibility based on user input. Utilizes Axios for API interactions, including service creation and picture uploads. Implements a blocking mechanism to prevent unsaved changes from navigating away.

---

**Sidebar.jsx**  
A sidebar navigation component for the clinic dashboard. It manages different menu options and toggles submenus like account, clinic information, animals, and veterinary schedules. It dynamically updates the sidebar based on the selected language and active routes. Includes a logout function that clears local storage and navigates the user to the homepage. Uses React Router's `NavLink` for navigation and `useState` to track active states.

**TimeTable.jsx**  
Displays the clinic’s weekly schedule and special hours. The component includes a tabbed interface allowing users to toggle between the weekly calendar and special settings for scheduling. Uses `useState` to manage the active tab and conditionally renders either the `GridTimeTable` or `TimeTableSettings` component based on the tab selected.

**Veterinary**  
Manages veterinarian profiles, including viewing, editing, deleting, and assigning services to veterinarians, with features like photo uploads and timetable settings.

**Veterinary Add**  
Allows the addition of new veterinarians through a form with personal details, language preferences, services, and photo upload, while handling validation and form submission.

### Common Components

**AnimalAutocomplete**  
An input field that allows users to search and select animal types from a list. Provides real-time suggestions based on input and stores the selected value in local storage. Handles input change, suggestion selection, and blur events.

**PlaceAutocomplete**  
An autocomplete input for selecting a city or postal code. Fetches city and postal code suggestions via an API and filters the results based on user input. Supports city and postal code selection, updates related state, and stores the selected value.

**Banner**  
A banner component that displays a title and subtitle with animation effects. Uses `AnimatePresence` and `motion.div` from `framer-motion` for smooth transitions. The content is revealed with a fade effect.

**BannerHome**  
Displays a home page banner with search functionality for clinics, cities, and animal types. Utilizes multiple autocomplete components for searching and selecting clinics, addresses, and animal types. Handles form submission and interacts with an API to fetch clinic data, displaying search results based on user input.

**ClinicAutocomplete**  
A component for autocompleting clinic names. Fetches clinic data via an API and filters suggestions based on user input. Provides input change handling, selection of clinic names, and click-outside functionality to hide suggestions.

**ClinicBanner**  
A banner component used specifically for clinic pages. Utilizes animation from `framer-motion` and `react-reveal` to display a title and subtitle with fade effects.

**CustomerBanner**  
A banner component tailored for customer pages. Similar to `ClinicBanner`, it uses animations to display title and subtitle with fade-in effects.

**Footer**  
A footer component with links to various pages, social media icons, contact information, and email subscription options. Includes quick links to privacy policy, terms, and frequently asked questions (FAQ). It also contains a section for subscribing to the newsletter.

**GooglePlaceAutocomplete**  
Integrates Google Places API for location autocomplete. Retrieves and formats geolocation data, adjusting terms like "Switzerland" and "Geneva" to French equivalents. Updates the location, coordinates, and address based on user selection.

**Header**  
A header component featuring a logo, a menu button, and dynamic user data display. The menu is toggleable, and user roles determine the routing to specific dashboards upon login. It also includes scroll effect handling for sticky headers.

**ClinicMap**  
Displays a Google Map with a marker indicating a clinic's location. Geocodes the address to obtain latitude and longitude, updating the map center accordingly. It uses the Google Maps API for fetching geolocation data based on the address.

**Menu**  
A side navigation menu component that allows users to navigate between pages, including the option to logout. It shows additional menu items based on user login status and account type. Social media links are also integrated within the menu.

**MobileSearch**  
A mobile-friendly search form for clinics, locations, and animal types. Filters are applied dynamically, and the user can toggle between search categories like clinic name, location, and animal type. Includes reset and search button functionality, with support for loading states.

## Customer Segment

**Account**  
Displays the user's account information, including email and options to change their email and password. It shows different forms based on the authentication type and provides buttons to submit changes. It uses `Form1`, `Form2`, and `Form3` for handling changes.
Form1: Handles the email change for the user. The form requires the user to input a new email and confirm it. Utilizes `react-hook-form` for validation, Axios for PUT requests to update credentials, and displays loading or success/error messages based on the response.

Form2: Handles password change for the user. The form allows the user to input a new password and confirm it, with validation for required fields and a specific password pattern. Uses `react-hook-form` for form handling and Axios for updating the password via PUT requests.

Form3: A combination of email, password, and other personal information update form for users. It allows the user to update email, password, and other details like gender and birthdate. Handles data validation and submission with feedback messages using `react-hook-form` and Axios.

**AddAnimal**  
Form for adding a new animal to the user's profile. Includes photo upload, animal description (name, sex, species, breed, etc.), medical history, and lifestyle information. The form supports validation and submission through `react-hook-form` and Axios, with file uploads handled for animal pictures.

**AnimalDetail**  
Displays detailed information about a selected animal, including the ability to edit the animal's details such as name, sex, breed, and medical information. Provides functionality to update the animal’s picture and delete the animal’s profile.

**Animals**  
Lists all animals associated with the user. Provides the option to navigate to each animal's detail page or add a new animal to the profile. Displays a loader while fetching animal data and handles user navigation with `useNavigate`.

**Board**  
A dashboard for users to view their pets and upcoming appointments. It fetches pet data and appointment details via API calls, filters the appointments to show only pending ones, and displays them on the UI. A "take appointment" button is shown when no upcoming appointments are available.

**CustomerDashboard**  
Displays a sidebar navigation menu and main content area. The sidebar allows users to navigate between different sections of their dashboard, such as their profile, pets, and appointments. It also dynamically adjusts based on the active route.

**MyclinicInfo**  
Allows users to manage and update their clinic-related information, including personal details like name, address, and phone number. It uses form handling with validation to ensure that the user's input is correctly submitted. It also prevents navigation if there are unsaved changes.

**Rendezvous**  
Manages appointments by displaying upcoming appointments and allowing users to delete them. It fetches all appointments from the backend and filters them based on their status (e.g., "pending"). If no appointments are available, a "make an appointment" button is shown.

**Sidebar**  
A navigation menu displayed on the side of the dashboard. It allows users to quickly navigate between sections like their profile, pets, and appointments. The sidebar shows different submenus depending on the section the user is currently viewing and includes a logout button.

Sidebar (Responsive): The sidebar adapts to different screen sizes and allows users to toggle submenus, displaying sections like "MY ACCOUNT" or "MY PETS" based on the current route. It includes dynamic logic to highlight the active section and provides a logout option.

**Pets**  
Displays a list of pets associated with the user. It fetches pet data via an API call and renders it. Users can navigate to individual pet details by clicking on a pet's name.

**Pet Details**  
Shows detailed information about a selected pet, including its name, age, breed, and other details. Users can update their pet's information here.

### Inscription Component

**Description**  
The Inscription component provides two sections for user sign-up: one for individuals (clients) and one for veterinarians. The layout is split into two columns with images on each side and a call-to-action button for registration. It also includes background images and a fade-in effect for dynamic content presentation.

- **Two Sections**: One for clients to sign up for online veterinary appointments, and one for veterinarians to join the platform.
- **Responsive Design**: The component adapts to both mobile and desktop views.
- **Interactive Buttons**: Each section contains a button that navigates to either the client or veterinarian sign-up page.
- **Background & Animation**: The background is animated with images that fade in for an engaging experience.

<!--
## 🔌 Setup & Running the App

### Prerequisites

- Node.js v16+
- Yarn or npm
- Google Maps API key
- Firebase configuration

### Installation

```bash
git clone https://github.com/your-org/oneclinic.vet-frontend.git
cd oneclinic.vet-frontend
npm install

```

## 🚀 Run Locally

```bash
npm run start:local

```

## 🌐 Routing & Modules

This app uses `react-router-dom@6` and is structured by user roles:

- `/` – Public home
- `/login`, `/register`, `/reset` – Auth routes
- `/customer/*` – Patient owner dashboard, appointment management
- `/clinic/*` – Clinic owner dashboard and schedule setup
- `/search` – Search clinics and available times
- `/contact-us` – Static info page

---

## 🧠 State Management (Redux Toolkit)

Redux is set up in `src/app/store.js`.

### 🔍 Important Slices

- `UserInfoSlice` – User authentication and profile
- `SearchSlice` – Search filters and results
- `StepsSlice` – Multi-step form state
- `LanguageSlice` – i18n language preference
- `counterSlice` – (Demo/test purpose)

> Middleware includes `redux-persist` for persisting user sessions.

---

## 🎨 Styling

- TailwindCSS with optional `tailwind-scrollbar` plugin
- SCSS modules per section in `/styles/`
- Uses both `index.scss` and `App.scss` for global resets and base styles

---

## 📦 Key Dependencies

| Library                           | Purpose            |
| --------------------------------- | ------------------ |
| `@mui/material`, `@emotion/react` | UI components      |
| `@reduxjs/toolkit`, `react-redux` | Global state       |
| `react-router-dom`                | Routing            |
| `react-hook-form`                 | Form handling      |
| `firebase`                        | Auth, storage      |
| `@react-google-maps/api`          | Maps               |
| `axios`                           | HTTP requests      |
| `redux-persist`                   | State persistence  |
| `framer-motion`                   | Animations         |
| `react-toastify`                  | Notifications      |
| `nprogress`                       | Loading indicators |

---

## 🧪 Testing

Includes:

- `@testing-library/react`
- `@testing-library/user-event`
- `jest-dom`

## 🧼 Deployment

Use the included `deploy.sh` for deployment automation.

Ensure the proper `.env` values are set for the target environment.

---

## 📋 Known Issues / To-Dos

- Some components have duplicates (`copy Rendezvouz.js`, `Timetable copy.js`)
- Language switch is working but may need UX polish
- Some features are under construction
- Improve code reusability and cleanup unused assets

---

## ✅ Developer Tips

- Use components from `components/common` for shared UI
- All HTTP requests should use `config/axios.js`
- Use slices in `features/` to manage global state
- Upload static resources like pet avatars to `uploads/`
- Translations handled in `Fr.js` and `Translate.js`

---


_Feel free to reach out for questions about the codebase or architecture._ -->
