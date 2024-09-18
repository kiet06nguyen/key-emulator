<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <title>PEEK-VN Get Key</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, rgba(29, 29, 29, 0.984) 0%,rgba(29, 29, 29, 0.984) 100%);
            color: #000000;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }
        .container {
            background-color: rgba(45,45,45, 255);
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 10px 40px rgba(40,40,40, 0.5);
            text-align: center;
            max-width: 700px;
            width: 100%;
            position: relative;
            border: 1px solid rgb(45,45,45);
            overflow: hidden;
            transform: perspective(1000px);
            transition: transform 0.3s ease-in-out;
        }
        .container:hover {
            transform: perspective(1000px) scale(1.1); /* Zoom in effect */
        }
        .container:before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, rgba(235, 238, 238, 0.1), rgba(0, 0, 0, 0.1));
            z-index: -1;
            animation: rotateBg 20s infinite linear;
            transform-origin: center;
        }
        @keyframes rotateBg {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }
        .brand {
            font-size: 40px;
            font-weight: bold;
            color: #ffffff;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 5px;
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.8);
            position: relative;
            z-index: 1;
            transition: transform 0.5s ease-in-out;
        }
        .brand:hover {
            transform: scale(1.05);
        }
        .key-display {
            font-size: 56px;
            font-weight: bold;
            color: #ffffff;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(250, 250, 250, 0.8);
            animation: glow 1.5s infinite alternate;
            position: relative;
            z-index: 1;
        }
        @keyframes glow {
            from {
                text-shadow: 0 0 10px rgba(221, 211, 211, 0.5), 0 0 20px rgba(255, 255, 255, 0.5), 0 0 30px rgba(255, 255, 255, 0.7);
            }
            to {
                text-shadow: 0 0 20px rgba(255, 255, 255, 0.8), 0 0 30px rgba(255, 255, 255, 0.7), 0 0 40px rgb(206, 215, 216);
            }
        }
        .label {
            font-size: 28px;
            color: #04baf1;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 0 0 10px rgba(246, 247, 247, 0.7);
            position: relative;
            z-index: 1;
        }
        .links {
            margin-top: 20px;
        }
        .links a {
            color: #048cfc;
            text-decoration: none;
            font-size: 18px;
            margin: 0 10px;
            display: inline-block;
            text-shadow: 0 0 10px rgba(228, 234, 235, 0.7);
            transition: color 0.3s ease, transform 0.3s ease, background-color 0.3s ease;
            padding: 5px 10px;
            border-radius: 5px;
        }
        .links a:hover {
            text-decoration: underline;
            color: #ffffff;
            background-color: rgba(230, 239, 240, 0.2);
            transform: scale(1.1);
        }
        .particles {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 0;
        }
        .particle {
            position: absolute;
            width: 6px;
            height: 6px;
            background-color: #04b2f7;
            border-radius: 50%;
            opacity: 0.8;
            animation: drift 5s infinite ease-in-out;
        }
        @keyframes drift {
            from {
                transform: translateY(0) translateX(0);
                opacity: 0.8;
            }
            to {
                transform: translateY(-500px) translateX(300px);
                opacity: 0;
            }
        }
    </style>
    <script>
        function createParticles() {
            const container = document.querySelector('.particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                particle.style.top = `${Math.random() * 100}%`;
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.animationDuration = `${Math.random() * 3 + 2}s`;
                container.appendChild(particle);
            }
        }

        function getKeyFromUrl() {
            const urlParams = new URLSearchParams(window.location.search);
            return urlParams.get('key');
        }

        window.onload = function() {
            const key = getKeyFromUrl();
            if (key) {
               // document.getElementById('key-display').textContent = key; // LẤY KEY BẰNG ĐUÔI CUỐI URL
               
               document.getElementById('key-display').textContent = 'FPS-PEEK-4673';
            } else {
                document.getElementById('key-display').textContent = 'FPS-PEEK-4673';
            }
            createParticles();
        }
    </script>
</head>
<body>
    <div class="container">
        <div class="brand">PeekCheat-VN</div>
        <div class="label">Key License</div>
        <div id="key-display" class="key-display"></div>
        <div class="links">
            <a href="https://discord.gg/UsXtzJ3H2H" target="_blank">Discord</a>
            <a href="https://web.facebook.com/kiet06nguyen/" target="_blank">Facebook</a>
        </div>
        <div class="particles"></div>
    </div>
</body>
</html>
