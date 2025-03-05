<!DOCTYPE html>
<html lang="en-GB">
<head>
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-Z0DW0ZG97K"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-Z0DW0ZG97K');
    </script>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <meta name="apple-mobile-web-app-title" content="Barry 63 Fullscreen">
    <meta name="theme-color" content="#000000">

    <link rel="apple-touch-icon" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">
    <link rel="icon" type="image/png" sizes="192x192" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">
    <link rel="icon" type="image/png" sizes="512x512" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">

    <title>Barry 63 Fullscreen</title>

    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        .container {
            width: 100%;
            height: 100%;
            background: repeating-conic-gradient(
                    from 30deg,
                    #0000 0 120deg,
                    #3c3c3c 0 180deg
                )
                calc(0.5 * 200px) calc(0.5 * 200px * 0.577),
            repeating-conic-gradient(
                from 30deg,
                #1d1d1d 0 60deg,
                #4e4f51 0 120deg,
                #3c3c3c 0 180deg
            );
            background-size: 200px calc(200px * 0.577);
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }

        .content {
            text-align: center;
            z-index: 2;
            color: white;
            padding: 20px;
            backdrop-filter: blur(8px);
            background: rgba(0, 0, 0, 0.4);
            border-radius: 12px;
        }

        h1 {
            font-size: 2.8em;
            margin-bottom: 20px;
        }

        button {
            display: block;
            width: 100%;
            max-width: 300px;
            padding: 15px;
            margin: 15px auto;
            font-size: 1em;
            font-weight: bold;
            color: white;
            background: linear-gradient(90deg, #32CD32, #7FFF00);
            border: none;
            border-radius: 8px;
            cursor: pointer;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease-in-out;
        }

        button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 200%;
            height: 100%;
            background: rgba(255, 255, 255, 0.2);
            transform: skewX(-45deg);
            transition: all 0.6s ease-in-out;
        }

        button:hover::before {
            left: 100%;
        }

        button:hover {
            transform: translateY(-5px);
            box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.3);
        }

        button:active {
            transform: translateY(2px);
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
        }

        button span {
            position: relative;
            z-index: 1;
            animation: bounceText 0.3s ease-in-out;
        }

        button:hover span {
            animation: bounceText 0.6s ease-in-out;
        }

        @keyframes bounceText {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
        }

        .back-tab {
            position: absolute;
            top: 20px;
            left: 20px;
            width: 100px;
            height: 40px;
            background: #333;
            color: white;
            font-size: 1em;
            font-weight: bold;
            border-radius: 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease-in-out;
            z-index: 3;
            display: none;
        }

        .back-tab:hover {
            background-color: #555;
        }

        iframe {
            display: none;
            width: 100vw;
            height: 100vh;
            border: none;
            position: absolute;
            top: 0;
            left: 0;
            z-index: 2;
        }

        /* Cookie consent */
        .cookie-consent {
            position: fixed;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(0, 0, 0, 0.8);
            color: white;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            width: auto;
            max-width: 400px;
            z-index: 9999;
        }

        .cookie-consent button {
            background: #32CD32;
            color: white;
            padding: 8px 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
        }

        .cookie-consent button:hover {
            background: #28a745;
        }
    </style>
</head>
<body>
    <div class="container"></div>

    <!-- Back button for game -->
    <div class="back-tab" onclick="closeGame()">← Back</div>

    <!-- Main content with buttons -->
    <div class="content">
        <h1>Barry 63 Fullscreen</h1>
        <button onclick="startGame('./polytrack.html');"><span>Polytrack Fullscreen</span></button>
        <button onclick="startGame('./polytrack_server2.html');"><span>Polytrack (Server 2) Fullscreen</span></button>
        <button onclick="startGame('./ovo.html');"><span>OvO Fullscreen</span></button>
        <button onclick="startGame('./snowrider.html');"><span>Snow Rider Fullscreen</span></button>
        <button onclick="startGame('./run3.html');"><span>Run 3 Fullscreen</span></button>
    </div>

    <!-- Game iframe -->
    <iframe id="game-frame"></iframe>

    <!-- Cookie consent popup -->
    <div class="cookie-consent" id="cookie-consent">
        We use cookies to save your game progress. <button onclick="acceptCookies()">I Agree</button>
    </div>

    <script>
        function startGame(gameUrl) {
            let iframe = document.getElementById('game-frame');
            if (!iframe) {
                iframe = document.createElement('iframe');
                iframe.id = 'game-frame';
                iframe.style.display = 'block';
                iframe.style.width = '100vw';
                iframe.style.height = '100vh';
                iframe.style.border = 'none';
                iframe.style.position = 'absolute';
                iframe.style.top = '0';
                iframe.style.left = '0';
                iframe.style.zIndex = '2';
                document.body.appendChild(iframe);
            }

            // Hide the home menu and show the back button
            document.querySelector('.content').style.display = 'none';
            document.querySelector('.back-tab').style.display = 'flex';

            iframe.src = gameUrl;
            iframe.style.display = 'block';
        }

        function closeGame() {
            const iframe = document.getElementById('game-frame');
            if (iframe) {
                iframe.remove();
            }

            document.querySelector('.content').style.display = 'block';
            document.querySelector('.back-tab').style.display = 'none';
        }

        function acceptCookies() {
            // Set a cookie indicating that the user has accepted cookies
            document.cookie = "cookies_accepted=true; path=/; max-age=" + 60 * 60 * 24 * 365;
            document.getElementById('cookie-consent').style.display = 'none';
        }

        // Check if cookies are accepted on page load
        window.onload = function() {
            if (document.cookie.includes("cookies_accepted=true")) {
                document.getElementById('cookie-consent').style.display = 'none';
            }
        }
    </script>
</body>
</html>
