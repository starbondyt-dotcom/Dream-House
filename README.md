<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Your Dream House</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: url('https://images.unsplash.com/photo-1568605114967-8130f3a36994') no-repeat center center/cover;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  background: rgba(0,0,0,0.75);
  padding: 30px;
  border-radius: 15px;
  width: 90%;
  max-width: 400px;
  text-align: center;
  color: white;
  box-shadow: 0 0 20px rgba(0,0,0,0.6);
}

h1 {
  margin-bottom: 10px;
}

input {
  width: 90%;
  padding: 10px;
  margin: 10px 0;
  border-radius: 5px;
  border: none;
}

button {
  background: #00c853;
  color: white;
  padding: 12px;
  width: 95%;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  background: #009624;
}

.success {
  margin-top: 15px;
  color: #00ff95;
  font-weight: bold;
}
</style>
</head>

<body>

<div class="container">
  <h1>Your Dream House</h1>
  <p>Register & Confirm Your Stay</p>

  <input type="text" id="name" placeholder="Enter Your Name" required>
  <input type="number" id="phone" placeholder="Enter Mobile Number" required>

  <!-- 🔥 Yaha apna QR code image ka link daal dena -->
  <img src="your-qr-code.png" width="200" style="margin:15px 0;">
  <p>Scan & Pay to Confirm</p>

  <button onclick="register()">Submit Registration</button>

  <div class="success" id="message"></div>
</div>

<script>
let ticketNumber = localStorage.getItem("ticket") || 0;

function register() {
  let name = document.getElementById("name").value;
  let phone = document.getElementById("phone").value;

  if(name === "" || phone === "") {
    alert("Please fill all details");
    return;
  }

  ticketNumber++;
  localStorage.setItem("ticket", ticketNumber);

  document.getElementById("message").innerHTML =
    "🎉 Congratulations! Registration successful.<br>" +
    "Your ticket number is " + ticketNumber +
    "<br>Please take a screenshot.";
}
</script>

</body>
</html>
