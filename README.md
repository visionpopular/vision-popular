<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Vision Popular</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: #f4f4f4;
    }

    header {
      background: black;
      color: white;
      padding: 20px;
      text-align: center;
    }

    .container {
      width: 80%;
      margin: auto;
      padding: 20px;
    }

    .news {
      background: white;
      margin-bottom: 20px;
      padding: 15px;
      border-radius: 8px;
      box-shadow: 0px 2px 5px rgba(0,0,0,0.1);
    }

    .title {
      font-size: 22px;
      font-weight: bold;
      margin-bottom: 10px;
    }
  </style>
</head>

<body>

<header>
  <h1>📰 Vision Popular</h1>
  <p>Tu periódico digital</p>
</header>

<div class="container" id="news">
  Cargando noticias...
</div>

<script>
fetch('/posts.json')
.then(res => res.json())
.then(data => {
  let html = '';

  data.reverse().forEach(post => {
    html += `
      <div class="news">
        <div class="title">${post.title}</div>
        <div>${post.content}</div>
      </div>
    `;
  });

  document.getElementById('news').innerHTML = html;
});
</script>

</body>
</html>
