
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>UMUT ERDEM INCE | GitHub Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: 'Arial', sans-serif;
      margin: 0;
      padding: 0;
      background: #f0f2f5;
      color: #333;
    }
    header {
      background: #24292e;
      color: white;
      padding: 40px 20px;
      text-align: center;
    }
    header h1 {
      margin: 0;
      font-size: 2.5em;
    }
    header p {
      margin-top: 10px;
      font-size: 1.2em;
    }
    main {
      padding: 30px 20px;
      max-width: 1000px;
      margin: auto;
    }
    section {
      margin-bottom: 40px;
    }
    h2 {
      color: #24292e;
      margin-bottom: 10px;
    }
    p {
      line-height: 1.6;
    }
    .card {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      text-align: center;
      max-width: 300px;
      margin: 20px auto;
    }
    img {
      border-radius: 50%;
      width: 120px;
      height: 120px;
      object-fit: cover;
      margin-bottom: 15px;
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
    .social-links a {
      margin-right: 10px;
      color: #0366d6;
      text-decoration: none;
    }
    .social-links a:hover {
      text-decoration: underline;
    }
    footer {
      text-align: center;
      padding: 20px;
      font-size: 0.9em;
      color: #666;
    }
  </style>
</head>
<body>

<header>
  <h1>Hello, I'm Umut Erdem Ince</h1>
  <p>Welcome to my GitHub Portfolio Website</p>
</header>

<main>
  <section id="about">
    <h2>About Me</h2>
    <p>I'm a passionate Java Developing and focused on building creative and impactful projects. I love coding, learning new technologies, and contributing to open-source.</p>
  </section>

  <section id="skills">
    <h2>Skills</h2>
    <ul>
      <li>Programming: Python, Java</li>
      <li>Web Development: HTML, CSS, React.js</li>
      <li>Tools: Git, Docker, VS Code</li>
    </ul>
  </section>

 
 <section id="contact">
    <h2>Contact</h2>
    <p>Feel free to reach out to me!</p>
    <div class="social-links">
      <a href="mailto:umuterdem2001@gmail.com">Email</a> |
      <a href="https://github.com/UmutErdemInce" target="_blank">GitHub</a>
    </div>
  </section>

  <section id="random-user">
    <h2>Explore Random Profiles</h2>
    <div class="card" id="user-card">
      <img src="" alt="User Photo" id="user-photo">
      <h3 id="user-name">Loading...</h3>
      <p id="user-email"></p>
      <p id="user-country"></p>
      <button onclick="fetchUser()">Load New User</button>
    </div>
  </section>
</main>

<footer>
  &copy; 2025 [Your Name]. Built with ❤️ using GitHub Pages.
</footer>

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

  fetchUser();
</script>

</body>
</html>
