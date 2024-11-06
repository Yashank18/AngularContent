# Assignment: Student Portal App

## Objective
Create a simple "Student Portal" application where students can:
- View and edit their profile
- Register for courses
- Check notifications

The app should implement:
- **Template Interpolation** for dynamic data display.
- **Reactive Forms** for user input and validation.
- **Routing** to navigate between different sections.
- **Services and Dependency Injection** to manage and retrieve data.
- **Animations** for smooth transitions.
- **Control Flow** to manage component display logic.

---

## Functional Requirements

### Home Page
- Display a welcome message with template interpolation that includes the user’s name and upcoming courses.

### Profile Page
- Allow the user to edit and update their profile using reactive forms.

### Courses Page
- List available courses and let students register/unregister for courses.

### Notifications Page
- Display a list of notifications with simple animations when they appear or disappear.

### Service-Driven Data Management
- Use services to handle student data, course data, and notifications.

---

## Application Structure

### Root Module
- `app.module.ts`

### Routing Module
- `app-routing.module.ts`

### Components
- **HomeComponent**
- **ProfileComponent**
- **CoursesComponent**
- **NotificationsComponent**

### Services
- **StudentService**: Manages student profile data.
- **CourseService**: Manages course-related data.
- **NotificationService**: Manages notifications.

---

## Detailed Instructions

### 1. Home Page (`HomeComponent`)
- **Template Interpolation**: Display a welcome message using the student’s name and list any upcoming courses.
- **Navigation**: Provide buttons to navigate to Profile, Courses, and Notifications pages.

### 2. Profile Page (`ProfileComponent`)
- **Reactive Form**:
  - Set up a form with fields like name, email, age, and address.
  - Include basic validation (e.g., required fields, minimum age).
- **Service Dependency Injection**:
  - Inject `StudentService` to retrieve and save the student’s profile data.
  - Populate the form with data from `StudentService` and allow the user to update it.
- **Form Submission**:
  - On submission, display a success message and update the student data in the service.

### 3. Courses Page (`CoursesComponent`)
- **Service Dependency Injection**:
  - Use `CourseService` to fetch a list of available courses.
  - Display courses with a Register/Unregister button for each course.
- **Control Flow and Template Interpolation**:
  - Display "Register" if the student is not enrolled in the course, and "Unregister" if they are.
- **Method Handling**:
  - When a course is registered or unregistered, update the student’s enrolled courses list and display a confirmation message.

### 4. Notifications Page (`NotificationsComponent`)
- **Service Dependency Injection**:
  - Inject `NotificationService` to fetch a list of notifications.
- **Simple Animations**:
  - Add an animation to make notifications slide in when they are added and fade out when they are removed.
- **Control Flow**:
  - Use `*ngIf` or `*ngFor` to conditionally display notifications.
  - Optionally, include a "Clear All" button to remove all notifications with a smooth fade-out effect.

### 5. Services and Dependency Injection
- **StudentService**:
  - Manages data for the student profile, including name, email, age, and enrolled courses.
- **CourseService**:
  - Provides a list of available courses and manages the registration status for each course.
- **NotificationService**:
  - Handles notifications related to course registration and profile updates.
  - Generates a new notification when the student registers or unregisters from a course.

### 6. Routing
- Set up routes for each component (`HomeComponent`, `ProfileComponent`, `CoursesComponent`, `NotificationsComponent`) in `app-routing.module.ts`.
- Create navigation links to allow users to move between pages without refreshing the app.

---

## Bonus Features (Optional)
- **HTTP Client**: Replace the static services with HTTP calls to fetch data from an external API.
- **Guarded Routing**: Protect the `ProfileComponent` with a route guard that checks if the user is logged in.
- **Custom Animations**: Add custom animations for routing transitions, such as fading between pages.
