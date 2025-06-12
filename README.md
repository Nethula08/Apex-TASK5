# Apex-TASK5
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="K-pop Fan Web App">
  <title>K-Pop Galaxy</title>
  <link rel="stylesheet" href="style.css">
  <link rel="icon" href="favicon.ico">
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  <style>
    :root {
      --bg: #ffffff;
      --text: #111111;
      --primary: #e91e63;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background: linear-gradient(135deg, #ff80ab, #ffe0e0);
      background-size: 400% 400%;
      animation: gradientBG 15s ease infinite;
      color: var(--text);
      transition: background-color 0.3s, color 0.3s;
    }

    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    header {
      background-color: var(--primary);
      padding: 1.5em;
      color: white;
      text-align: center;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    nav ul {
      list-style: none;
      padding: 0;
      display: flex;
      justify-content: center;
      gap: 2em;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }

    section {
      padding: 3em;
      text-align: center;
    }

    .image-container {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 1.5em;
    }

    img {
      width: 220px;
      height: auto;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
      transition: transform 0.3s;
    }

    img:hover {
      transform: scale(1.05);
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 0.8em;
      max-width: 400px;
      margin: 0 auto;
    }

    input, textarea {
      padding: 1em;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 1em;
    }

    button {
      padding: 1em;
      background-color: var(--primary);
      border: none;
      color: white;
      cursor: pointer;
      border-radius: 6px;
      font-weight: bold;
      font-size: 1em;
      transition: background-color 0.3s, transform 0.2s;
    }

    button:hover {
      background-color: #c2185b;
      transform: scale(1.05);
    }

    #formStatus {
      margin-top: 1em;
      font-weight: bold;
      opacity: 0;
      transition: opacity 0.5s ease-in-out, transform 0.3s;
    }

    .popup {
      opacity: 1 !important;
      transform: scale(1.2);
      color: var(--primary);
    }

    .hidden {
      display: none;
    }

    footer {
      background-color: #222;
      color: white;
      text-align: center;
      padding: 1.5em 0;
    }

    .dark-mode {
      --bg: #111111;
      --text: #ffffff;
    }

    @media (max-width: 600px) {
      nav ul {
        flex-direction: column;
        gap: 1em;
      }

      .image-container {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>

<body>
  <header>
    <h1>K-Pop Galaxy</h1>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#artists">Artists</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <section id="home">
    <h2>Welcome to K-Pop Galaxy</h2>
    <p>Your one-stop fan page for all things K-Pop!</p>
    <button id="darkModeToggle">Toggle Dark Mode</button>
  </section>

  <section id="artists">
    <h2>Featured Artists</h2>
    <ul>
      <li>BTS</li>
      <li>Blackpink</li>
      <li>Twice</li>
      <li>EXO</li>
    </ul>
  </section>

  <section id="gallery">
    <h2>K-Pop Gallery</h2>
    <div class="image-container">
      <a href="https://www.pinterest.com/search/pins/?q=bts%20kpop" target="_blank">
        <img src="bts.jpg" alt="BTS" loading="lazy">
      </a>
      <a href="https://www.pinterest.com/search/pins/?q=blackpink%20kpop" target="_blank">
        <img src="blackpink.jpg" alt="Blackpink" loading="lazy">
      </a>
    </div>
  </section>

  <section id="contact">
    <h2>Contact Us</h2>
    <form id="contactForm">
      <input type="text" placeholder="Your Name" required>
      <input type="email" placeholder="Your Email" required>
      <textarea placeholder="Your Message"></textarea>
      <button type="submit">Send</button>
    </form>
    <p id="formStatus" class="hidden"></p>
  </section>

  <footer>
    <p>&copy; 2025 K-Pop Galaxy. All rights reserved.</p>
  </footer>

  <script>
    // Dark Mode Toggle
    document.getElementById('darkModeToggle').addEventListener('click', () => {
      document.body.classList.toggle('dark-mode');
    });

    // Contact Form Handling with Animation + Confetti
    document.getElementById('contactForm').addEventListener('submit', function (e) {
      e.preventDefault();
      const status = document.getElementById('formStatus');
      status.textContent = 'Message sent! Thank you 💌';
      status.classList.remove('hidden');
      status.classList.add('popup');

      // Confetti effect
      confetti({
        particleCount: 100,
        spread: 70,
        origin: { y: 0.6 }
      });

      setTimeout(() => {
        status.classList.remove('popup');
        status.classList.add('hidden');
      }, 3000);

      this.reset();
    });
  </script>
</body>

</html>
