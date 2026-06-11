<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 Namora Comigo? 💖</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #ff758c, #ff7eb3, #ffc2d1);
            overflow: hidden;
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(15px);
            padding: 40px;
            border-radius: 25px;
            box-shadow: 0 8px 30px rgba(0,0,0,0.2);
            max-width: 500px;
        }

        .heart {
            font-size: 80px;
            animation: pulse 1.2s infinite;
            margin-bottom: 15px;
        }

        h1 {
            color: white;
            font-size: 2.2rem;
            margin-bottom: 15px;
        }

        p {
            color: white;
            font-size: 1.1rem;
            margin-bottom: 30px;
            line-height: 1.6;
        }

        .btn {
            border: none;
            padding: 14px 30px;
            border-radius: 50px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }

        .sim {
            background: #ff2d55;
            color: white;
            box-shadow: 0 4px 15px rgba(255,45,85,.5);
        }

        .sim:hover {
            transform: scale(1.08);
        }

        .nao {
            background: white;
            color: #ff2d55;
            position: absolute;
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.15);
            }
            100% {
                transform: scale(1);
            }
        }

        .floating-heart {
            position: absolute;
            color: rgba(255,255,255,0.7);
            animation: float 8s linear infinite;
            font-size: 25px;
        }

        @keyframes float {
            from {
                transform: translateY(100vh);
                opacity: 1;
            }
            to {
                transform: translateY(-100px);
                opacity: 0;
            }
        }
    </style>
</head>

<body>

    <div class="container">
        <div class="heart">❤️</div>

        <h1>Marina, aceita namorar comigo?</h1>

        <p>
            Desde que você entrou na minha vida, meus dias ficaram mais leves,
            minhas risadas mais sinceras e meu coração mais feliz.
            💖
            <br><br>
            Então eu preciso te perguntar...
        </p>

        <button class="btn sim" onclick="sim()">💍 SIM</button>
        <button class="btn nao" onclick="desvia(this)" onmouseover="desvia(this)">😅 NÃO</button>
    </div>

    <script>
        function sim() {
            alert("❤️ Você aceitou namorar comigo! ❤️");

            location.href =
                "https://music.youtube.com/watch?v=izGwDsrQ1eQ";
        }

        function desvia(btn) {
            btn.style.top = geraPosicao(10, 80);
            btn.style.left = geraPosicao(10, 80);
        }

        function geraPosicao(min, max) {
            return (Math.random() * (max - min) + min) + "%";
        }

        function criarCoracao() {
            const heart = document.createElement("div");

            heart.classList.add("floating-heart");
            heart.innerHTML = "❤️";

            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration =
                (Math.random() * 3 + 5) + "s";

            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 8000);
        }

        setInterval(criarCoracao, 400);
    </script>

</body>

</html>
