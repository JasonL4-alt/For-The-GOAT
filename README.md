<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Love 💗</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            background: #ffe6f2;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: Arial, sans-serif;
            overflow: hidden;
        }
        .container {
            text-align: center;
        }
        .heart {
            width: 100px;
            height: 100px;
            background: #ff69b4;
            position: relative;
            transform: rotate(-45deg);
            margin: 0 auto 60px;
            cursor: pointer;
            animation: heartbeat 1.2s infinite;
            box-shadow: 0 0 30px rgba(255, 105, 180, 0.6);
        }
        .heart::before,
        .heart::after {
            content: "";
            width: 100px;
            height: 100px;
            background: #ff69b4;
            border-radius: 50%;
            position: absolute;
        }
        .heart::before {
            top: -50px;
            left: 0;
        }
        .heart::after {
            left: 50px;
            top: 0;
        }
        @keyframes heartbeat {
            0%, 100% {
                transform: rotate(-45deg) scale(1);
            }
            50% {
                transform: rotate(-45deg) scale(1.15);
            }
        }
        button {
            border: none;
            background: #ff69b4;
            color: white;
            padding: 14px 25px;
            border-radius: 25px;
            font-size: 17px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(255, 105, 180, 0.3);
        }
        button:hover {
            background: #ff4fa3;
        }
        #message {
            display: none;
            margin-top: 25px;
            max-width: 350px;
            color: #d63384;
            font-size: 20px;
            line-height: 1.5;
            animation: fadeIn 1.5s ease;
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(15px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        .floating-heart {
            position: absolute;
            color: #ff69b4;
            font-size: 25px;
            animation: floatUp 4s linear forwards;
            pointer-events: none;
        }
        @keyframes floatUp {
            from {
                transform: translateY(0);
                opacity: 1;
            }
            to {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="heart" onclick="showLove()"></div>
        <button onclick="showLove()">
            Click me 💗
        </button>
        <div id="message">
            💕 My love, you mean more to me than I could ever explain.
            You make me smile, you make my days better, and I'm so grateful
            that I get to call you mine. I would choose you over and over
            again, every single time. I love you more than you know. 🥹💗
            <br><br>
            Forever yours, ❤️
        </div>
    </div>
    <script>
        function showLove() {
            document.getElementById("message").style.display = "block";
            for (let i = 0; i < 20; i++) {
                createHeart();
            }
        }
        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("floating-heart");
            heart.innerHTML = "💗";
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.top = (80 + Math.random() * 20) + "vh";
            heart.style.fontSize = (15 + Math.random() * 25) + "px";
            heart.style.animationDuration = (3 + Math.random() * 3) + "s";
            document.body.appendChild(heart);
            setTimeout(() => {
                heart.remove();
            }, 6000);
        }
    </script>
</body>
</html>

