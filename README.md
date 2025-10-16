# RelayHackathone
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mediumish Blog</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
    <div>
        <header>
    <div class="logo">Mediumish</div>
    <nav>
      <ul>
        <li><a id="homeLink">Home</a></li>
        <li><a id="aboutLink">About</a></li>
      </ul>
    </nav>
  </header>

  <main  id="homePage" class="page">
    <section class="posts">
        <div id="articleContent">
      <article class="post" onclick="openArticle(0)">
        <h2>The Art of Simplicity</h2>
        <p class="subtitle">Why less really is more.</p>
      </article>

      <article class="post" onclick="openArticle(1)">
        <h2>Focus in a Distracted World</h2>
        <p class="subtitle">Learning to stay present in chaos.</p>
      </article>

      <article class="post" onclick="openArticle(2)">
        <h2>Designing Without Color</h2>
        <p class="subtitle">The elegance of grayscale aesthetics.</p>
      </article>

        <section id="aboutLink" class="pagehidden">
    <p>This minimalist blog celebrates clean, distraction-free design.</p>
        </section>
      </div>


  </main>
<br><br><br><br><br><br>
  

   

  <section id="articlePage" class="page hidden">
    
    <footer>
      <p>© <span id="footerYear"></span> Mediumish Blog</p>
      
    </footer>
  </section>
   <button id="backBtn">← Back to Home</button>

  <script src="script.js"></script>
</body>
</html>

    </div>
  
<div>

    <br>
    <br><br><br><br><br><br><br><br><br><br><br>
  <br><br><br><br><br><br><br><br><br><br>
  <br><br><br><br><br><br><br><br><br><br>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Club Event Sign-up</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="form-container">
        <h2>Music Club Event Sign-up</h2>
        <form id="music-club-form">
            <div class="form-group">
                <label for="name">Full Name</label>
                <input type="text" id="name" name="Name" required>
            </div>
            
            <div class="form-group">
                <label for="email">Email Address</label>
                <input type="email" id="email" name="Email" required>
            </div>
            
            <div class="form-group">
                <label for="event">Select an Event</label>
                <select id="event" name="Event Selection" required>
                    <option value="" disabled selected>-- Choose an event --</option>
                    <option value="Acoustic Night">Acoustic Night</option>
                    <option value="Jazz Jam Session">Jazz Jam Session</option>
                    <option value="Open Mic Night">Open Mic Night</option>
                    <option value="Club Concert">Club Concert</option>
                </select>
            </div>
            
            <button type="submit">Sign Up</button>
        </form>
        <div id="status-message" class="status-message"></div>
    </div>

    <script src="script.js"></script>
</body>
</html>


</div>


body {
  font-family: Georgia, serif;
  margin: 0;
  padding: 0;
  background-color: #fff;
  color: #000;
}

header {
  border-bottom: 1px solid #ccc;
  padding: 10px 20px;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
  transform: scaleX(1);
}

#homeLink{
    position: absolute;
    right:200px;
    top:10px;
}

#aboutLink{
    position: absolute;
    right:100px;
    top:10px;
}

nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

nav li {
  margin: 5px 0;
}

main {
  max-width: 800px;
  margin: 20px auto;
  padding: 20px;
}

.post {
  border-bottom: 1px solid #ddd;
  padding: 10px 0;
  cursor: pointer;
}

.posts:hover {
  background: #f5f5f5;
}

.pagehidden p{
  position:relative;
  top:500px;
  right:500px;
  text-align: center;
}

footer {
  border-top: 1px solid #ccc;
  padding: 10px;
  text-align: center;
  position:relative;
     top:215px;
}

#backBtn{
     position:relative;
     top:170px;
}

#articlePage {
  margin-top: 150px;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.form-container {
    background-color: #fff;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 400px;
    box-sizing: border-box;
}

h2 {
    text-align: center;
    color: #333;
    margin-bottom: 20px;
}

.form-group {
    margin-bottom: 15px;
}

label {
    display: block;
    margin-bottom: 5px;
    color: #555;
}

input[type="text"],
input[type="email"],
select {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

button {
    width: 100%;
    padding: 12px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #2980b9;
}

.status-message {
    margin-top: 20px;
    text-align: center;
    font-weight: bold;
}

.status-message.success {
    color: #27ae60;
}

.status-message.error {
    color: #c0392b;
}



const pages = document.querySelectorAll('.page');
const homeLink = document.getElementById('homeLink');
const aboutLink = document.getElementById('aboutLink');
const backBtn = document.getElementById('backBtn');
const yearEl = document.getElementById('footerYear');
const articlePage = document.getElementById('articlePage');
const homePage = document.getElementById('homePage');
const articles = [
  {
    title: "The Art of Simplicity",
    content: "<p>Simplicity is the ultimate sophistication...</p>"
  },
  {
    title: "Focus in a Distracted World",
    content: "<p>In a world filled with noise, true focus is rare...</p>"
  },
  {
    title: "Designing Without Color",
    content: "<p>Sometimes grayscale can speak louder than colors...</p>"
  }
]

if (yearEl) {
  yearEl.textContent = new Date().getFullYear();
}

function showPage(id) {
  id.forEach(page => {
    page.style.visibility = 'visible';
  });
  document.getElementById(id).style.visibility = 'visible';
}

homeLink.onclick = () => showPage(homePage);
aboutLink.onclick = () => showPage(aboutPage);
backBtn.onclick = () => showPage(homePage);

function openArticle(id) {
  const article = articles[id];
  const content = document.getElementById('articleContent');
  content.innerHTML = `<h2>${article.title}</h2>${article.content}`;
  showPage('articlePage');
}

const form = document.getElementById('music-club-form');
const statusMessage = document.getElementById('status-message');

const formEndpoint = "https://formsubmit.co/your@email.com"; 

form.addEventListener('submit', function(event) {
    event.preventDefault(); // Prevent the default form submission

    const formData = new FormData(form);
    const data = Object.fromEntries(formData.entries());
    
    fetch(formEndpoint, {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
            'Accept': 'application/json'
        },
        body: JSON.stringify(data)
    })
    .then(response => {
        if (response.ok) {
            form.reset(); 
            statusMessage.textContent = "Sign-up successful! We'll see you there.";
            statusMessage.className = 'status-message success';
        } else {
            statusMessage.textContent = "There was an error submitting your request. Please try again.";
            statusMessage.className = 'status-message error';
        }
    })
    .catch(error => {
        console.error('Error:', error);
        statusMessage.textContent = "There was an error submitting your request. Please try again.";
        statusMessage.className = 'status-message error';
    });
});

