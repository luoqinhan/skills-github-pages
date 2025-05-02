---
title: Welcome to my blog
---
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday!</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap');

        body {
            background: radial-gradient(circle, #ffb6c1, #ffd700);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }

        h1 {
            font-family: 'Dancing Script', cursive;
            color: white;
            font-size: 60px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            animation: pulse 0.5s infinite alternate;
        }

        @keyframes pulse {
            from {
                transform: scale(1);
            }

            to {
                transform: scale(1.1);
            }
        }

        #message {
            font-family: YouYuan;
            font-size: 24px;
            margin: 20px 0;
        }

        #image {
            width: 300px;
            height: auto;
        }

        .falling {
            position: absolute;
            top: -50px;
            animation: fall linear infinite;
        }

        @keyframes fall {
            to {
                top: 100vh;
            }
        }
    </style>
</head>

<body>
    <h1>Happy Birthday!</h1>
    <div id="message">愿你的生日如璀璨星辰般闪耀，幸福永远与你相伴！</div>
    <img id="image" src="https://p9-flow-imagex-sign.byteimg.com/ocean-cloud-tos/image_generation/6a30c75a0b0b77cb595a1b3362796d3b_1741678103707880520.png~tplv-a9rns2rl98-image.png?rk3s=25bff839&x-expires=1773214103&x-signature=5jO6t3cI6T8Ksk9oeiKTkDnP%2BOY%3D" alt="Birthday Image">
    <audio id="birthday-song" autoplay loop>
        <source src="https://www.kugou.com/mixsong/99zs5r95.html?fromsearch=happy%20birthday" type="audio/mpeg">
        你的浏览器不支持音频播放。
    </audio>

    <script>
        const emojis = ['💖', '🎈', '⭐', '🍰'];
        const messages = [
            '愿你的生日如璀璨星辰般闪耀，幸福永远与你相伴！',
            '在这个特别的日子里，祝你生日快乐，梦想成真！',
            '生日快乐！愿生活的每一天都充满阳光和欢笑。',
            '愿你的生日是一场奇妙的冒险，快乐永不止步！',
            '祝你生日快乐，岁岁年年都有今朝的快乐！'
        ];
        const messageElement = document.getElementById('message');

        document.addEventListener('click', () => {
            const randomIndex = Math.floor(Math.random() * messages.length);
            messageElement.textContent = messages[randomIndex];
        });

        function createFallingEmoji() {
            const emoji = document.createElement('span');
            emoji.classList.add('falling');
            emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];
            emoji.style.left = Math.random() * window.innerWidth + 'px';
            emoji.style.animationDuration = Math.random() * 3 + 2 + 's';
            document.body.appendChild(emoji);

            setTimeout(() => {
                document.body.removeChild(emoji);
            }, 5000);
        }

        setInterval(createFallingEmoji, 500);

        document.addEventListener('mousemove', (e) => {
            const cake = document.createElement('span');
            cake.classList.add('falling');
            cake.textContent = '🍰';
            cake.style.left = e.clientX + 'px';
            cake.style.top = e.clientY + 'px';
            cake.style.animationDuration = Math.random() * 3 + 2 + 's';
            document.body.appendChild(cake);

            setTimeout(() => {
                document.body.removeChild(cake);
            }, 5000);
        });
    </script>
</body>

</html>
    
