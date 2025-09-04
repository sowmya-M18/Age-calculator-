# Age-calculator-
Mini project on age calculator 📟.
<!DOCTYPE html>
<html>
<head>
  <title>Pastel Age Calculator</title>
  <style>
    body {
      font-family: "Poppins", sans-serif;
      text-align: center;
      margin: 0;
      padding: 0;
      background: #fdf6f0;
    }
    #welcomePage, #formPage {
      height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    button {
      margin-top: 20px;
      padding: 12px 24px;
      border: none;
      border-radius: 25px;
      font-size: 16px;
      cursor: pointer;
      background: #a3d2ca;
      color: #fff;
      transition: transform 0.3s ease, background 0.3s ease;
    }
    button:hover {
      background: #5eaaa8;
      transform: scale(1.1);
    }
    input {
      margin: 10px;
      padding: 10px;
      border-radius: 15px;
      border: 1px solid #ccc;
      background: #f9f9f9;
    }
    #formPage {
      display: none;
      animation: fadeIn 1s ease;
      background: #e8ded2;
    }
    #result {
      margin-top: 20px;
      font-size: 18px;
      color: #444;
    }
    /* Animation */
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(50px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .login-animation {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: #a3d2ca;
      margin-bottom: 20px;
      position: relative;
      overflow: hidden;
      animation: bounce 1s ease;
    }
    .login-animation::before {
      content: "";
      position: absolute;
      top: 15px;
      left: 20px;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      background: #fff;
    }
    .login-animation::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 10px;
      width: 60px;
      height: 35px;
      border-radius: 50% 50% 0 0;
      background: #fff;
    }
    @keyframes bounce {
      0% { transform: scale(0.5); opacity: 0; }
      50% { transform: scale(1.1); opacity: 1; }
      100% { transform: scale(1); }
    }
  </style>
</head>
<body>

  <!-- First Page -->
  <div id="welcomePage">
    <h1 style="color:#5eaaa8;">Welcome!</h1>
    <button onclick="showForm()">Enter</button>
  </div>

  <!-- Second Page (Form Page) -->
  <div id="formPage">
    <div class="login-animation"></div>
    <h2 style="color:#444;">Fill Your Details</h2>
    <input type="text" id="name" placeholder="Enter your name"><br>
    <input type="number" id="birthYear" placeholder="Enter your year of birth"><br>
    <button onclick="calculateAge()">Submit</button>
    <p id="result"></p>
  </div>

  <script>
    function showForm() {
      document.getElementById("welcomePage").style.display = "none";
      document.getElementById("formPage").style.display = "flex";
    }

    function calculateAge() {
      let name = document.getElementById("name").value;
      let birthYear = document.getElementById("birthYear").value;
      let currentYear = new Date().getFullYear();
      let age = currentYear - birthYear;

      if (name && birthYear) {
        document.getElementById("result").innerText = 
          "Hi " + name + "! Your age is " + age + " years.";
      } else {
        document.getElementById("result").innerText = "Please enter all details.";
      }
    }
  </script>

</body>
</html>
