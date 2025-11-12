<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>How Websites Work - Book</title>

  <!-- ✅ Favicon (Computer Icon) -->
  <link rel="icon" href="https://em-content.zobj.net/source/microsoft-teams/363/laptop_1f4bb.png" type="image/png">

  <style>
    body {
      margin: 0;
      padding: 0;
      background: #f2efe9;
      font-family: 'Georgia', serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .book-container {
      width: 90%;
      max-width: 800px;
      aspect-ratio: 4 / 3;
      background: #fff;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
      display: flex;
      flex-direction: column;
      border-radius: 8px;
      overflow: hidden;
      position: relative;
    }

    .page {
      flex: 1;
      padding: 30px;
      display: none;
      overflow-y: auto;
    }

    .page.active {
      display: block;
    }

    h2 {
      color: #2e86c1;
      margin-top: 0;
    }

    .buttons {
      position: absolute;
      bottom: 10px;
      width: 100%;
      display: flex;
      justify-content: space-between;
      padding: 0 20px;
    }

    button {
      padding: 10px 18px;
      font-size: 1rem;
      background: #3498db;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.2s;
    }

    button:disabled {
      background: #bbb;
      cursor: not-allowed;
    }

    pre {
      background: #f8f9fa;
      padding: 10px;
      border-radius: 5px;
      overflow-x: auto;
    }

    code {
      font-family: Consolas, monospace;
    }

    /* 🎨 Color classes for each technology */
    .html-color {
      color: #7f8c8d; /* Neutral gray – solid base */
    }

    .css-color {
      color: #3498db; /* Bright blue – stylish and vibrant */
    }

    .js-color {
      color: #27ae60; /* Fresh green – dynamic and interactive */
    }
  </style>
</head>
<body>

<div class="book-container">
  <div class="page active">
    <h2>What Makes Up a Website?</h2>
    <p>Websites are built using 3 core technologies:</p>
    <ul>
      <li class="html-color"><strong>HTML</strong> – Structure and content</li>
      <li class="css-color"><strong>CSS</strong> – Style and layout</li>
      <li class="js-color"><strong>JavaScript</strong> – Interactivity</li>
    </ul>
    <p>Together, they form the building blocks of all modern websites.</p>
  </div>

  <div class="page">
    <h2>What is HTML?</h2>
    <p><strong>HTML (HyperText Markup Language)</strong> is used to structure content on the web.</p>
    <p>Example:</p>
    <pre><code>&lt;h1&gt;Welcome!&lt;/h1&gt;
&lt;p&gt;This is a website.&lt;/p&gt;</code></pre>
    <p>This creates a heading and a paragraph.</p>
  </div>

  <div class="page">
    <h2>What is CSS?</h2>
    <p><strong>CSS (Cascading Style Sheets)</strong> controls how your website looks. Example:</p>
    <pre><code>h1 {
  color: blue;
  font-size: 2em;
}</code></pre>
    <p>This makes all <code>&lt;h1&gt;</code> text blue and larger.</p>
  </div>

  <div class="page">
    <h2>What is JavaScript?</h2>
    <p><strong>JavaScript</strong> adds interactivity like buttons, sliders, games, and more.</p>
    <p>Example:</p>
    <pre><code>alert("Hello!");</code></pre>
    <p>This would pop up a message when a user visits the page or clicks something.</p>
  </div>

  <div class="page">
    <h2>How It All Works Together</h2>
    <p>In a real website:</p>
    <ul>
      <li class="html-color"><strong>HTML</strong> creates the structure</li>
      <li class="css-color"><strong>CSS</strong> styles it beautifully</li>
      <li class="js-color"><strong>JavaScript</strong> makes it interactive</li>
    </ul>
    <p>You now understand the basics of how websites work!</p>
  </div>

  <div class="buttons">
    <button id="prevBtn" onclick="changePage(-1)">⬅ Prev</button>
    <button id="nextBtn" onclick="changePage(1)">Next ➡</button>
  </div>
</div>

<script>
  const pages = document.querySelectorAll('.page');
  let currentPage = 0;

  function showPage(index) {
    pages.forEach((page, i) => {
      page.classList.toggle('active', i === index);
    });

    document.getElementById('prevBtn').disabled = index === 0;
    document.getElementById('nextBtn').disabled = index === pages.length - 1;
  }

  function changePage(direction) {
    currentPage += direction;
    if (currentPage < 0) currentPage = 0;
    if (currentPage >= pages.length) currentPage = pages.length - 1;
    showPage(currentPage);
  }

  // Initial display
  showPage(currentPage);
</script>

</body>
</html>


