<!DOCTYPE html>
<html lang="te">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Baby Boy Reveal</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            width: 100%;
            overflow: hidden;
            font-family: 'Arial', sans-serif;
            background-color: #000;
        }

        /* --- STAGE 1: THE CURTAINS --- */
        .curtain-wrapper {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            z-index: 10;
            transition: visibility 0s 2s; /* Hides the layer after animation */
        }

        .curtain {
            width: 50%;
            height: 100%;
            background: linear-gradient(to right, #4a0000, #800000, #600000);
            background-size: 100% 100%;
            box-shadow: inset 0 0 100px rgba(0,0,0,0.5);
            transition: transform 2s cubic-bezier(0.45, 0.05, 0.55, 0.95);
            position: relative;
        }

        /* Gold trim on the curtain edges */
        .left-curtain { border-right: 3px solid #ffd700; }
        .right-curtain { border-left: 3px solid #ffd700; }

        /* --- STAGE 2: THE GOLD BUTTON --- */
        #revealBtn {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 140px;
            height: 140px;
            border-radius: 50%;
            border: 5px solid #fff;
            background: radial-gradient(circle at 30% 30%, #ffd700, #b8860b);
            color: #fff;
            font-weight: bold;
            font-size: 18px;
            cursor: pointer;
            z-index: 20;
            box-shadow: 0 0 20px #ffd700, 0 10px 30px rgba(0,0,0,0.5);
            transition: 0.5s ease;
        }

        #revealBtn:hover { transform: translate(-50%, -50%) scale(1.1); box-shadow: 0 0 40px #ffd700; }

        /* --- STAGE 3: THE REVEAL CONTENT --- */
        .reveal-page {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: radial-gradient(circle, #e3f2fd, #bbdefb); /* Soft blue background */
            text-align: center;
            opacity: 0;
            transition: opacity 1.5s ease-in 1s;
        }

        .telugu-title {
            font-size: 4rem;
            color: #0d47a1;
            margin-bottom: 20px;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .baby-image {
            max-width: 90%;
            max-height: 70vh;
            border: 10px solid white;
            border-radius: 20px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.3);
        }

        /* Animation Classes triggered by JS */
        .open-l { transform: translateX(-100%); }
        .open-r { transform: translateX(100%); }
        .fade-btn { opacity: 0; pointer-events: none; }
        .show-page { opacity: 1; }

    </style>
</head>
<body>

    <button id="revealBtn">PRESS TO<br>REVEAL</button>

    <div class="curtain-wrapper" id="curtainWrapper">
        <div class="curtain left-curtain" id="lC"></div>
        <div class="curtain right-curtain" id="rC"></div>
    </div>

    <div class="reveal-page" id="revealPage">
        <h1 class="telugu-title">మా కన్నయ్య కి స్వాగతం</h1>
        
        <img src="https://via.placeholder.com/800x1000.png?text=Baby+Boy+Image" alt="Baby Boy" class="baby-image">
    </div>

    <script>
        const btn = document.getElementById('revealBtn');
        const lC = document.getElementById('lC');
        const rC = document.getElementById('rC');
        const revealPage = document.getElementById('revealPage');

        btn.addEventListener('click', () => {
            // 1. Hide the button
            btn.classList.add('fade-btn');
            
            // 2. Slide curtains to sides
            lC.classList.add('open-l');
            rC.classList.add('open-r');
            
            // 3. Show the reveal page
            revealPage.classList.add('show-page');
        });
    </script>
</body>
</html>
