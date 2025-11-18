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
<img width="1919" height="1131" alt="image" src="https://github.com/user-attachments/assets/4d64c44e-d30c-4664-97e2-a8e0307ce7c2" />

<img width="1917" height="1140" alt="image" src="https://github.com/user-attachments/assets/5fbaad53-f2f3-4f3c-8821-30e26bd52436" />

<img width="1919" height="1134" alt="image" src="https://github.com/user-attachments/assets/7e7b461b-cb38-4650-98d1-1753ffb36a53" />

<img width="1919" height="1137" alt="image" src="https://github.com/user-attachments/assets/881cab49-9911-4976-9abc-1b031bd92060" />

🟦 RESULT

A fully functional Single Page Application (SPA) with a protected Dashboard was successfully created using React Router.
The application demonstrates:

client-side routing

nested routes

login-based access control

smooth navigation without page reload

clean UI and working authentication

The aim of developing a React SPA with protected and nested routing is successfully achieved.
