<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Rumi 學習大廳</title>
    <style>
        :root {
            --pink: #FFD1DC;
            --blue: #BFEAF2;
            --yellow: #FFF4BD;
            --text-color: #7B5E57;
            --bg-color: #FFFBFA;
        }

        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: "Microsoft JhengHei", sans-serif;
            background-color: var(--bg-color);
            margin: 0;
            display: flex;
            flex-direction: column;
            height: 100vh;
            width: 100vw;
            overflow: hidden;
        }

        /* 頂部選單 */
        .header {
            background-color: white;
            border-bottom: 4px solid var(--pink);
            padding: 10px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            flex-shrink: 0;
        }

        .header h2 {
            margin: 5px 0;
            font-size: 1.2rem;
            background: var(--yellow);
            padding: 5px 15px;
            border-radius: 20px;
            border: 2px dashed #FFB7C5;
        }

        .button-group {
            display: flex;
            gap: 10px;
            width: 100%;
            justify-content: center;
        }

        .menu-btn {
            flex: 1;
            max-width: 200px;
            padding: 12px 5px;
            border: none;
            border-radius: 15px;
            font-size: 0.9rem;
            font-weight: bold;
            color: var(--text-color);
            box-shadow: 0 3px 0px rgba(0,0,0,0.1);
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 5px;
        }

        .btn-spell { background-color: var(--pink); }
        .btn-bubble { background-color: var(--blue); }

        .active {
            background-color: white !important;
            border: 2px solid var(--pink);
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);
        }

        /* 遊戲區域 - 確保不縮放 */
        .game-container {
            flex-grow: 1;
            width: 100%;
            background: white;
            position: relative;
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
            color: #FFB7C5;
        }
    </style>
</head>
<body>

    <div class="header">
        <h2>✨ Rumi 學習大廳</h2>
        <div class="button-group">
            <button class="menu-btn btn-spell" onclick="loadGame('https://liliancir0125.github.io/spell-game/spell_game.html', this)">
                🔤 拼字遊戲
            </button>
            <button class="menu-btn btn-bubble" onclick="loadGame('https://liliancir0125.github.io/jp-bubble-game/', this)">
                🫧 泡泡遊戲
            </button>
        </div>
    </div>

    <div class="game-container">
        <div id="welcome" class="placeholder">
            <p style="font-size: 1.5rem; font-weight: bold;">今天想要學習什麼呢？✨</p>
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
