🔥 React SPA – Aim, Procedure, Output & Result
🟦 AIM

To develop a Single Page Application (SPA) using React and React Router that includes a Home page, Login page, and a Dashboard section with nested routes such as Profile, Settings, and Notifications.
Protected routing must be implemented to ensure only logged-in users can access dashboard pages.

🟦 SOFTWARE / TECHNOLOGIES USED

React

Vite

React Router DOM

JavaScript

CSS

VS Code

🟦 PROCEDURE
1. Install Vite React project
npm create vite@latest react-spa-dashboard
cd react-spa-dashboard
npm install

2. Install required packages
npm install react-router-dom

3. Create folder structure

4. Implement Protected Route

Create a component:

const ProtectedRoute = ({ children }) => {
  const isLoggedIn = localStorage.getItem("loggedIn") === "true";
  return isLoggedIn ? children : <Navigate to="/login" />;
};

5. Create Pages (Home, Login, Dashboard, etc.)

Home page → simple welcome page

Login page → sets localStorage.loggedIn = true

Dashboard → contains Link navbar + nested routes

6. Setup Routing in App.jsx
<Router>
  <Routes>
    <Route path="/" element={<Home />} />
    <Route path="/login" element={<Login />} />

    <Route 
      path="/dashboard/*" 
      element={
        <ProtectedRoute>
          <Dashboard />
        </ProtectedRoute>
      } 
    />
  </Routes>
</Router>

7. Start the server
npm run dev

🟦 OUTPUT 
![unnamed](https://github.com/user-attachments/assets/9ad8ac8e-1b53-480f-9a56-50a52c746c9e)

![unnamed (1)](https://github.com/user-attachments/assets/8b519974-fa5b-41b3-b945-40e88584a769)

![unnamed (2)](https://github.com/user-attachments/assets/1ed34dcd-49da-4079-bf62-940fc4399e9d)

![unnamed (3)](https://github.com/user-attachments/assets/2630bedb-a0a2-4cc3-a5fe-a295291b9e2a)

🟦 RESULT

A fully functional Single Page Application (SPA) with a protected Dashboard was successfully created using React Router.
The application demonstrates:

client-side routing

nested routes

login-based access control

smooth navigation without page reload

clean UI and working authentication

The aim of developing a React SPA with protected and nested routing is successfully achieved.
