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
      </div>
  </main>

  <section id="aboutLink" class="pagehidden">
    <p>This minimalist blog celebrates clean, distraction-free design.</p>
  </section>

  <section id="articlePage" class="page hidden">
    
    <footer>
      <p>© <span id="footerYear"></span> Mediumish Blog</p>
    </footer>
  </section>
   <button id="backBtn">← Back to Home</button>

  <script src="script.js"></script>
</body>
</html>

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
