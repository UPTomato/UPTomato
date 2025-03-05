<!DOCTYPE html>
<html lang="en-GB">
<head>
    <!-- Google tag (gtag.js) -->
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

    <!-- App Icon -->
    <link rel="apple-touch-icon" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">
    <link rel="icon" type="image/png" sizes="192x192" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">
    <link rel="icon" type="image/png" sizes="512x512" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">

    <title>Barry 63 Fullscreen</title>

    <style>
        /* Global Reset and Layout */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
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

        /* Background container */
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

        /* Content Box */
        .content {
            text-align: center;
            z-index: 2;
            color: white;
            padding: 20px;
            backdrop-filter: blur(8px);
            background: rgba(0, 0, 0, 0.4);
            border-radius: 12px;
            width: 100%;
            max-width: 350px;
            margin: auto;
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

        /* Back Button (Floating Tab) */
        .back-tab {
            position: fixed;
            top: 20px;
            left: -80px;
            width: 100px;
            height: 40px;
            background: #333;
            color: white;
            font-size: 1em;
            font-weight: bold;
            border-radius: 5px 0 0 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease-in-out;
            z-index: 3;
        }

        .back-tab:hover {
            left: 0;
        }

        .back-tab span {
            margin-left: 5px;
        }

        /* Full-Screen Game Iframe */
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

        /* Cookie Consent Styles */
        .cookie-consent {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0, 0, 0, 0.8);
            color: white;
            padding: 15px;
            text-align: center;
            z-index: 10;
        }

        .cookie-consent button {
            margin-top: 10px;
            padding: 10px 20px;
            background: #32CD32;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }

        /* Responsive Design Adjustments */
        @media (max-width: 600px) {
            .content {
                padding: 10px;
                max-width: 90%;
            }

            h1 {
                font-size: 2em;
            }

            button {
                max-width: 90%;
            }

            .back-tab {
                width: 80px;
                left: -70px;
                font-size: 0.9em;
            }
        }
    </style>
</head>
<body>
    <!-- Background container -->
    <div class="container"></div>

    <!-- Back Button Tab -->
    <div class="back-tab" onclick="closeGame()">
        ← <span>Back</span>
    </div>

    <!-- Main Content -->
    <div class="content">
        <h1>Barry 63 Fullscreen</h1>

        <button onclick="startGame('./polytrack.html');"><span>Polytrack Fullscreen</span></button>
        <button onclick="startGame('./polytrack_server2.html');"><span>Polytrack (Server 2) Fullscreen</span></button>
        <button onclick="startGame('./ovo.html');"><span>OvO Fullscreen</span></button>
        <button onclick="startGame('./snowrider.html');"><span>Snow Rider Fullscreen</span></button>
        <button onclick="startGame('./run3.html');"><span>Run 3 Fullscreen</span></button>
    </div>

    <!-- Game Iframe -->
    <iframe id="game-frame"></iframe>

    <!-- Cookie Consent Box -->
    <div id="cookie-consent" class="cookie-consent" style="display:none;">
        This website uses cookies to save your game progress. By clicking "Accept", you agree to the use of cookies.
        <br><button onclick="acceptCookies();">Accept</button>
    </div>

    <script>
        // Functions for Cookie Consent
        function checkCookieConsent() {
            const cookiesAccepted = getCookie("cookiesAccepted");
            if (!cookiesAccepted) {
                document.getElementById('cookie-consent').style.display = 'block';
            }
        }

        function acceptCookies() {
            setCookie("cookiesAccepted", "true", 365);
            document.getElementById('cookie-consent').style.display = 'none';
        }

        // Cookie Helper Functions
        function setCookie(cname, cvalue, exdays) {
            let d = new Date();
            d.setTime(d.getTime() + (exdays * 24 * 60 * 60 * 1000));
            let expires = "expires=" + d.toUTCString();
            document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
        }

        function getCookie(cname) {
            let name = cname + "=";
            let decodedCookie = decodeURIComponent(document.cookie);
            let ca = decodedCookie.split(';');
            for (let i = 0; i < ca.length; i++) {
                let c = ca[i];
                while (c.charAt(0) == ' ') {
                    c = c.substring(1);
                }
                if (c.indexOf(name) == 0) {
                    return c.substring(name.length, c.length);
                }
            }
            return "";
        }

        // Start the game in an iframe
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

            const content = document.querySelector('.content');
            const backTab = document.querySelector('.back-tab');

            content.style.display = 'none';
            iframe.src = gameUrl;
            iframe.style.display = 'block';
            backTab.style.display = 'flex';
        }

        // Close the game and show the home menu again
        function closeGame() {
            const iframe = document.getElementById('game-frame');
            const content = document.querySelector('.content');
            const backTab = document.querySelector('.back-tab');

            if (iframe) {
                iframe.remove();
            }

            content.style.display = 'block';
            backTab.style.display = 'none';
        }

        // Check if the cookie consent has been accepted when the page loads
        window.onload = function() {
            checkCookieConsent();
        };
    </script>
</body>
</html>
