<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rumi 學習大廳</title>
    <style>
        :root {
            --pink: #FFD1DC; /* 吉依卡哇粉 */
            --blue: #BFEAF2; /* 小八貓藍 */
            --yellow: #FFF4BD; /* 兔兔黃 */
            --text-color: #7B5E57; /* 溫柔深咖啡 */
            --bg-color: #FFFBFA;
        }

        body {
            font-family: "Microsoft JhengHei", "PingFang TC", sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            display: flex;
            height: 100vh;
            overflow: hidden;
        }

        /* 左側選單 */
        .sidebar {
            width: 260px;
            background-color: white;
            border-right: 6px solid var(--pink);
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 25px 15px;
            box-shadow: 4px 0 15px rgba(0,0,0,0.05);
            z-index: 10;
        }

        .sidebar h2 {
            font-size: 1.4rem;
            margin-bottom: 35px;
            background: var(--yellow);
            padding: 12px 25px;
            border-radius: 30px;
            border: 3px dashed #FFB7C5;
            text-align: center;
        }

        .menu-btn {
            width: 100%;
            padding: 18px;
            margin-bottom: 18px;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            font-size: 1.05rem;
            font-weight: bold;
            color: var(--text-color);
            transition: all 0.2s ease-in-out;
            box-shadow: 0 4px 0px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .btn-spell { background-color: var(--pink); }
        .btn-bubble { background-color: var(--blue); }

        .menu-btn:hover {
            transform: scale(1.02);
            filter: brightness(1.03);
            box-shadow: 0 6px 0px rgba(0,0,0,0.1);
        }

        .menu-btn:active {
            transform: translateY(3px);
            box-shadow: 0 1px 0px rgba(0,0,0,0.1);
        }

        .active {
            outline: 4px solid #FFB7C5;
            background-color: #ffffff !important;
            border: 2px solid var(--pink);
        }

        /* 右側顯示區 */
        .content {
            flex-grow: 1;
            position: relative;
            background: #fff;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        .placeholder {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100%;
            text-align: center;
            background: linear-gradient(135deg, #fffafa 0%, #fff4f7 100%);
        }

        .placeholder p {
            font-size: 1.8rem;
            color: #FFB7C5;
            font-weight: bold;
            text-shadow: 1px 1px 0px white;
        }

        .footer-msg {
            margin-top: auto;
            font-size: 0.9rem;
            padding: 10px;
            background: var(--yellow);
            border-radius: 10px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="sidebar">
        <h2>✨ Rumi 學習大廳</h2>
        
        <button class="menu-btn btn-spell" onclick="loadGame('https://liliancir0125.github.io/spell-game/spell_game.html', this)">
            <span>🔤</span> 拼字小遊戲
        </button>

        <button class="menu-btn btn-bubble" onclick="loadGame('https://liliancir0125.github.io/jp-bubble-game/', this)">
            <span>🫧</span> 日語泡泡遊戲
        </button>

        <div class="footer-msg">
            加油 Rumi！( ˊᗜˋ )و
        </div>
    </div>

    <div class="content">
        <div id="welcome" class="placeholder">
            <p>今天想要學習什麼呢？✨</p>
            <span style="font-size: 3rem;">₍ᐢ.ˬ.ᐢ₎</span>
        </div>
        <iframe id="game-frame" src="" style="display:none;"></iframe>
    </div>

    <script>
        function loadGame(url, btn) {
            document.getElementById('welcome').style.display = 'none';
            const frame = document.getElementById('game-frame');
            frame.style.display = 'block';
            frame.src = url;

            const btns = document.querySelectorAll('.menu-btn');
            btns.forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
        }
    </script>

</body>
</html>
