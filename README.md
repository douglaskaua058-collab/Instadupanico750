<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title> de Mensagem Flutuante</title>
  <style>
    body { font-family: sans-serif; padding: 40px; text-align: center; }
    a.fakeLink { color: #007bff; text-decoration: none; cursor: pointer; font-size: 1.2em; }
    .overlay {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.7);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 9999;
      color: white;
      font-size: 1.5em;
      text-align: center;
      padding: 20px;
    }
    .overlay .box {
      background: #222;
      padding: 30px;
      border-radius: 10px;
    }
    .overlay button {
      margin-top: 20px;
      padding: 8px 16px;
      font-size: 1em;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <p>Brincadeira — <a id="brincalink" class="fakeLink">Clique aqui</a></p>

  <div id="overlay" class="overlay">
    <div class="box">
      <p>Outra pessoa está pegando seus dados…</p>
      <button id="closeBtn">OK</button>
    </div>
  </div>

  <script>
    const link = document.getElementById('brincalink');
    const overlay = document.getElementById('overlay');
    const closeBtn = document.getElementById('closeBtn');

    link.addEventListener('click', function(e){
      e.preventDefault(); // evita comportamento padrão de link
      overlay.style.display = 'flex';
    });

    closeBtn.addEventListener('click', function(){
      overlay.style.display = 'none';
    });
  </script>

</body>
</html>
