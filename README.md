<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Barbearia Fernando Souza</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #0d0d0d;
      color: #fff;
      margin: 0;
      padding: 0;
    }

    header {
      background: #000;
      padding: 20px;
      text-align: center;
      border-bottom: 2px solid gold;
    }

    header h1 {
      color: gold;
      margin: 0;
    }

    .container {
      max-width: 500px;
      margin: 40px auto;
      background: #1a1a1a;
      padding: 25px;
      border-radius: 10px;
    }

    h2 {
      text-align: center;
      color: gold;
    }

    input, select, button {
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      border-radius: 6px;
      border: none;
      font-size: 15px;
    }

    button {
      background: gold;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background: #d4af37;
    }

    .info {
      text-align: center;
      margin-bottom: 20px;
      font-size: 14px;
      color: #ccc;
    }

  </style>
</head>
<body>

<header>
  <h1>💈 Barbearia Fernando Souza</h1>
</header>

<div class="container">
  <h2>Agende seu horário</h2>

  <div class="info">
    Atendimento: Segunda a Sexta <br>
    ⏰ 07:30 às 19:30
  </div>

  <input type="text" id="nome" placeholder="Seu nome">

  <select id="servico">
    <option>Corte</option>
    <option>Barba</option>
    <option>Sobrancelha</option>
    <option>Depilação (ouvido e nariz)</option>
  </select>

  <input type="date" id="data">
  <input type="time" id="hora">

  <input type="text" id="whatsapp" placeholder="Seu WhatsApp">

  <button onclick="agendar()">Agendar via WhatsApp</button>
</div>

<script>
  function agendar() {
    const nome = document.getElementById("nome").value;
    const servico = document.getElementById("servico").value;
    const data = document.getElementById("data").value;
    const hora = document.getElementById("hora").value;
    const whatsapp = document.getElementById("whatsapp").value;

    if (!nome || !data || !hora || !whatsapp) {
      alert("Preencha todos os campos!");
      return;
    }

    const mensagem = `Olá! Meu nome é ${nome}. Quero agendar um *${servico}* no dia ${data} às ${hora}. Meu WhatsApp: ${whatsapp}`;

    const numeroBarbearia = "SEU_NUMERO_AQUI"; 

    const url = `https://wa.me/${numeroBarbearia}?text=${encodeURIComponent(mensagem)}`;

    window.open(url, "_blank");
  }
</script>

</body>
</html>
