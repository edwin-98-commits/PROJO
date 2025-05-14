 index.html and style.css.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My GitHub Website</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <nav class="navbar">
      <div class="logo">
        <img src="logo.png" alt="My Logo" />
      </div>
      <ul class="nav-links">
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
    <div class="hero-text">
      <h1>Welcome to My Website!</h1>
      <p>This is a simple site hosted on GitHub Pages.</p>
    </div>
  </header>

  <main>
    <section id="about">
      <h2>About</h2>
      <p>This site was created to learn GitHub Pages and basic web development.</p>
    </section>

    <section id="contact">
      <h2>Contact</h2>
      <p>You can reach me via <a href="https://github.com/">GitHub</a>.</p>
    </section>
  </main>

  <footer>
    <p>© 2025 Your Name. All rights reserved.</p>
  </footer>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f7f7f7;
  color: #333;
}

header {
  background-color: #4a90e2;
  color: white;
  padding-bottom: 1rem;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #3a78c2;
}

.logo img {
  height: 50px;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1.5rem;
}

.nav-links li a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.nav-links li a:hover {
  text-decoration: underline;
}

.hero-text {
  text-align: center;
  padding: 2rem;
}

main {
  padding: 2rem;
}

section {
  margin-bottom: 2rem;
}

footer {
  background-color: #222;
  color: white;
  text-align: center;
  padding: 1rem;
}


