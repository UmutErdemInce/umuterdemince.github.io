<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Random User Profile</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: 'Arial', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      margin: 0;
      background: #f0f2f5;
    }
    .card {
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      text-align: center;
      max-width: 300px;
    }
    img {
      border-radius: 50%;
      width: 120px;
      height: 120px;
      object-fit: cover;
      margin-bottom: 20px;
    }
    h2 {
      margin: 10px 0 5px;
    }
    p {
      margin: 5px 0;
      color: #666;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 1em;
    }
    button:hover {
      background: #0056b3;
    }
  </style>
</head>
<body>

<div class="card" id="user-card">
  <img src="" alt="User Photo" id="user-photo">
  <h2 id="user-name">Loading...</h2>
  <p id="user-email"></p>
  <p id="user-country"></p>
  <button onclick="fetchUser()">Load New User</button>
</div>

<script>
  async function fetchUser() {
    try {
      const response = await fetch('https://randomuser.me/api/');
      const data = await response.json();
      const user = data.results[0];
      
      document.getElementById('user-photo').src = user.picture.large;
      document.getElementById('user-name').textContent = `${user.name.first} ${user.name.last}`;
      document.getElementById('user-email').textContent = user.email;
      document.getElementById('user-country').textContent = user.location.country;
    } catch (error) {
      console.error('Error fetching user:', error);
    }
  }

  // Fetch a user on page load
  fetchUser();
</script>

</body>
</html>

