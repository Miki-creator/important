<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Card</title>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Press Start 2P', cursive;
            overflow: hidden;
        }

        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            position: relative;
        }

        .intro-page {
            background: linear-gradient(to right, #bfdbfe, #fbcfe8);
            color: #374151;
        }

        .gift-page {
            background: linear-gradient(to bottom, #bae6fd, #fef3c7, #bbf7d0);
            color: #374151;
            overflow: hidden;
        }

        .title {
            font-size: 2rem;
            font-weight: 800;
            margin-bottom: 3rem;
            text-align: center;
            text-shadow: 0 10px 15px rgba(0, 0, 0, 0.3);
            letter-spacing: -0.025em;
            animation: fadeInDown 1s ease-out;
        }

        .gift-title {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 2.5rem;
            text-align: center;
            color: #dc2626;
            text-shadow: 0 25px 50px rgba(0, 0, 0, 0.25);
            letter-spacing: -0.025em;
            z-index: 10;
            position: relative;
            animation: fadeInDown 1s ease-out;
        }

        .yes-button {
            padding: 1rem 2rem;
            background-color: #22c55e;
            color: white;
            border: none;
            border-radius: 0.75rem;
            font-size: 1.25rem;
            font-weight: 700;
            font-family: inherit;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.25);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .yes-button:hover {
            background-color: #16a34a;
            transform: scale(1.1);
        }

        .no-button {
            position: absolute;
            padding: 1rem 2rem;
            background-color: #ef4444;
            color: white;
            border: none;
            border-radius: 0.75rem;
            font-size: 1.25rem;
            font-weight: 700;
            font-family: inherit;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.25);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .clouds {
            position: absolute;
            font-size: 4rem;
            opacity: 0.6;
            animation: moveRight 30s linear infinite;
        }

        .clouds-2 {
            position: absolute;
            top: 10rem;
            font-size: 3rem;
            opacity: 0.5;
            animation: moveRight 40s linear infinite;
        }

        .track {
            position: absolute;
            bottom: 0;
            width: 100%;
            height: 6rem;
            background-color: #374151;
            display: flex;
            align-items: center;
        }

        .track-line {
            width: 100%;
            height: 0.5rem;
            background-color: #fde047;
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }

        .coin {
            position: absolute;
            bottom: 9rem;
            font-size: 2.5rem;
            animation: moveCoins 10s linear infinite;
        }

        .coin:nth-child(n+1) { animation-delay: 0s; animation-duration: 10s; }
        .coin:nth-child(n+2) { animation-delay: 2s; animation-duration: 12s; }
        .coin:nth-child(n+3) { animation-delay: 4s; animation-duration: 14s; }
        .coin:nth-child(n+4) { animation-delay: 6s; animation-duration: 16s; }
        .coin:nth-child(n+5) { animation-delay: 8s; animation-duration: 18s; }

        .range-rover {
            position: absolute;
            bottom: 4rem;
            width: 16rem;
            filter: drop-shadow(0 25px 25px rgba(0, 0, 0, 0.15));
            animation: driveRover 8s linear infinite;
        }

        .gift-description {
            margin-top: 3rem;
            font-size: 1.125rem;
            text-align: center;
            color: #111827;
            font-weight: 600;
            letter-spacing: -0.025em;
            text-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            z-index: 10;
            position: relative;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-3rem);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes moveRight {
            from {
                transform: translateX(-10%);
            }
            to {
                transform: translateX(110%);
            }
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.5;
            }
        }

        @keyframes moveCoins {
            from {
                transform: translateX(120%);
            }
            to {
                transform: translateX(-20%);
            }
        }

        @keyframes driveRover {
            from {
                transform: translateX(-100%) translateY(0);
            }
            12.5% {
                transform: translateX(-50%) translateY(-0.625rem);
            }
            25% {
                transform: translateX(0%) translateY(0);
            }
            37.5% {
                transform: translateX(50%) translateY(-0.375rem);
            }
            50% {
                transform: translateX(100%) translateY(0);
            }
            to {
                transform: translateX(100vw) translateY(0);
            }
        }

        .hidden {
            display: none;
        }

        @media (min-width: 768px) {
            .title {
                font-size: 3rem;
            }
            .gift-title {
                font-size: 4rem;
            }
            .range-rover {
                width: 20rem;
            }
            .gift-description {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Intro Page -->
    <div id="intro-page" class="container intro-page">
        <h1 class="title">Do you want to receive your gift? 🎁</h1>
        <button id="yes-button" class="yes-button">Yes ✅</button>
        <button id="no-button" class="no-button" style="top: 60%; left: 55%;">No ❌</button>
    </div>

    <!-- Gift Page -->
    <div id="gift-page" class="container gift-page hidden">
        <!-- Background Clouds -->
        <div class="clouds" style="top: 5rem; left: 0;">☁️ ☁️ ☁️</div>
        <div class="clouds-2" style="left: 0;">☁️ ☁️</div>

        <!-- Track Line -->
        <div class="track">
            <div class="track-line"></div>
        </div>

        <!-- Coins -->
        <div class="coin" style="left: 120%;">🪙</div>
        <div class="coin" style="left: 140%;">🪙</div>
        <div class="coin" style="left: 160%;">🪙</div>
        <div class="coin" style="left: 180%;">🪙</div>
        <div class="coin" style="left: 200%;">🪙</div>

        <!-- Birthday Title -->
        <h1 class="gift-title">🎉 Happy Birthday, Bro! 🎉</h1>

        <!-- Animated Range Rover -->
        <img src="pic.png" alt="Range Rover Driver" class="range-rover" onerror="this.style.display='none'; this.nextElementSibling.style.display='block';">
        <div class="range-rover" style="display: none; background: #374151; border-radius: 0.5rem; display: flex; align-items: center; justify-content: center; color: white; font-size: 1rem;"></div>

        <p class="gift-description">
            Here's your  gift — a custom Range Rover ride 🚙💨
        </p>
    </div>

    <script>
        let currentPage = "intro";
        let noButtonPosition = { top: "60%", left: "55%" };

        const introPage = document.getElementById("intro-page");
        const giftPage = document.getElementById("gift-page");
        const yesButton = document.getElementById("yes-button");
        const noButton = document.getElementById("no-button");

        function showGiftPage() {
            currentPage = "gift";
            introPage.classList.add("hidden");
            giftPage.classList.remove("hidden");
        }

        function moveNoButton() {
            const randTop = Math.floor(Math.random() * 80) + 10;
            const randLeft = Math.floor(Math.random() * 80) + 10;
            noButtonPosition = { top: `${randTop}%`, left: `${randLeft}%` };
            
            noButton.style.top = noButtonPosition.top;
            noButton.style.left = noButtonPosition.left;
        }

        // Event listeners
        yesButton.addEventListener("click", showGiftPage);
        noButton.addEventListener("mouseenter", moveNoButton);
        noButton.addEventListener("touchstart", moveNoButton);

        // Prevent context menu on no button for mobile
        noButton.addEventListener("contextmenu", function(e) {
            e.preventDefault();
            moveNoButton();
        });
    </script>
</body>
</html>
