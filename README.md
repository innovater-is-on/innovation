# innovation
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>My Website</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    body {
      min-height: 100vh;
      background: linear-gradient(135deg, #0f172a, #1e3a8a);
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    /* LOGIN PAGE */

    .login-container {
      width: 380px;
      padding: 40px;
      background: rgba(255, 255, 255, 0.1);
      border: 1px solid rgba(255, 255, 255, 0.2);
      border-radius: 20px;
      backdrop-filter: blur(15px);
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.4);
    }

    .logo {
      width: 80px;
      height: 80px;
      margin: 0 auto 20px;
      border-radius: 50%;
      background: #2563eb;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 35px;
      font-weight: bold;
    }

    h1 {
      text-align: center;
      margin-bottom: 10px;
    }

    .subtitle {
      text-align: center;
      color: #cbd5e1;
      margin-bottom: 30px;
    }

    .input-group {
      margin-bottom: 20px;
    }

    .input-group label {
      display: block;
      margin-bottom: 8px;
      color: #e2e8f0;
    }

    .input-group input {
      width: 100%;
      padding: 14px;
      border: none;
      border-radius: 10px;
      outline: none;
      background: rgba(255, 255, 255, 0.95);
      color: #111827;
      font-size: 16px;
    }

    .input-group input:focus {
      box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.5);
    }

    .login-button {
      width: 100%;
      padding: 14px;
      border: none;
      border-radius: 10px;
      background: #2563eb;
      color: white;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }

    .login-button:hover {
      background: #1d4ed8;
      transform: translateY(-2px);
    }

    #error {
      color: #f87171;
      text-align: center;
      margin-top: 15px;
      display: none;
    }

    /* HOME PAGE */

    .home-page {
      display: none;
      width: 100%;
      min-height: 100vh;
    }

    .navbar {
      height: 70px;
      padding: 0 40px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: rgba(15, 23, 42, 0.9);
      border-bottom: 1px solid rgba(255,255,255,0.1);
    }

    .navbar h2 {
      color: #60a5fa;
    }

    .logout-button {
      padding: 10px 18px;
      border: none;
      border-radius: 8px;
      background: #ef4444;
      color: white;
      cursor: pointer;
      font-weight: bold;
    }

    .logout-button:hover {
      background: #dc2626;
    }

    .hero {
      max-width: 1000px;
      margin: auto;
      padding: 100px 30px;
      text-align: center;
    }

    .hero h1 {
      font-size: 50px;
      margin-bottom: 20px;
    }

    .hero p {
      color: #cbd5e1;
      font-size: 20px;
      line-height: 1.6;
    }

    .cards {
      max-width: 1000px;
      margin: 0 auto;
      padding: 0 30px 50px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .card {
      padding: 30px;
      background: rgba(255,255,255,0.08);
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: 15px;
      text-align: center;
    }

    .card h3 {
      margin-bottom: 10px;
      color: #60a5fa;
    }

    .card p {
      color: #cbd5e1;
      line-height: 1.5;
    }

    @media (max-width: 700px) {
      .cards {
        grid-template-columns: 1fr;
      }

      .hero h1 {
        font-size: 38px;
      }

      .login-container {
        width: 90%;
      }
    }
  </style>
</head>

<body>

  <!-- LOGIN SCREEN -->

  <div class="login-container" id="loginPage">

    <div class="logo">
      🔐
    </div>

    <h1>Welcome</h1>

    <p class="subtitle">
      Please login to continue
    </p>

    <form id="loginForm">

      <div class="input-group">
        <label for="username">Username</label>

        <input
          type="text"
          id="username"
          placeholder="Enter username"
          required
        >
      </div>

      <div class="input-group">
        <label for="password">Password</label>

        <input
          type="password"
          id="password"
          placeholder="Enter password"
          required
        >
      </div>

      <button class="login-button" type="submit">
        Login
      </button>

      <p id="error">
        Incorrect username or password.
      </p>

    </form>

  </div>


  <!-- HOME PAGE AFTER LOGIN -->

  <div class="home-page" id="homePage">

    <nav class="navbar">

      <h2>My Website</h2>

      <button class="logout-button" onclick="logout()">
        Logout
      </button>

    </nav>


    <section class="hero">

      <h1>Welcome to My Website 🎉</h1>

      <p>
        You have successfully logged in.
        This is your private-looking homepage.
      </p>

    </section>


    <section class="cards">

      <div class="card">
        <h3>🚀 Projects</h3>
        <p>
          Add information about your projects here.
        </p>
      </div>

      <div class="card">
        <h3>💻 GitHub</h3>
        <p>
          Add links and information about your GitHub repositories here.
        </p>
      </div>

      <div class="card">
        <h3>📚 About</h3>
        <p>
          Add your personal information or website description here.
        </p>
      </div>

    </section>

  </div>


  <script>

    // DEMO LOGIN CREDENTIALS
    const correctUsername = "qwerty123";
    const correctPassword = "qwerty1234";


    const loginForm = document.getElementById("loginForm");

    loginForm.addEventListener("submit", function(event) {

      event.preventDefault();

      const username =
        document.getElementById("username").value;

      const password =
        document.getElementById("password").value;

      const error =
        document.getElementById("error");


      if (
        username === correctUsername &&
        password === correctPassword
      ) {

        // Hide login
        document.getElementById("loginPage").style.display = "none";

        // Show home page
        document.getElementById("homePage").style.display = "block";

      } else {

        error.style.display = "block";

      }

    });


    function logout() {

      // Hide home page
      document.getElementById("homePage").style.display = "none";

      // Show login page
      document.getElementById("loginPage").style.display = "block";

      // Clear inputs
      document.getElementById("username").value = "";
      document.getElementById("password").value = "";

      document.getElementById("error").style.display = "none";

    }

  </script>

</body>
</html>
