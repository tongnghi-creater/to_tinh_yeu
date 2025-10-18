<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Lời tỏ tình dễ thương</title>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Quicksand:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      min-height: 100vh;
      margin: 0;
      font-family: 'Quicksand', Arial, sans-serif;
      background: linear-gradient(120deg, #f6d7fd 0%, #ffe6ec 55%, #c7d6ff 100%);
      overflow-x: hidden;
      position: relative;
      text-align: center;
      animation: gradientMove 12s ease-in-out infinite alternate;
    }
    @keyframes gradientMove {
      0% { background-position: 0% 50%; }
      100% { background-position: 100% 50%; }
    }
    .bg-glow {
      position: absolute;
      top: 10%;
      left: 50%;
      transform: translateX(-50%);
      width: 530px;
      height: 420px;
      background: radial-gradient(circle, #ffe6ec88 0%, #c9c0fc00 80%);
      filter: blur(60px);
      z-index: 0;
      pointer-events: none;
      animation: glowPulse 4s infinite alternate;
    }
    @keyframes glowPulse {
      0% { opacity: 0.7; }
      100% { opacity: 1; }
    }
    /* Sticker nền động */
    .bg-sticker {
      position: absolute;
      z-index: 1;
      opacity: 0.5;
      pointer-events: none;
      transition: transform 0.2s;
      filter: drop-shadow(0 6px 20px #eeb4c9);
      animation: stickerFloat 6s ease-in-out infinite alternate;
    }
    @keyframes stickerFloat {
      0% { transform: translateY(0px) scale(1); }
      100% { transform: translateY(24px) scale(1.08); }
    }
    .bg-sticker1 { top: 28px; left: 16px; width: 65px; animation-delay: 0.5s;}
    .bg-sticker2 { top: 44px; right: 18px; width: 59px; animation-delay: 2.2s;}
    .bg-sticker3 { bottom: 40px; left: 22px; width: 62px; animation-delay: 0.8s;}
    .bg-sticker4 { bottom: 38px; right: 22px; width: 70px; animation-delay: 1.8s;}
    .bg-sticker5 { top: 46%; left: 0; width: 50px; animation-delay: 1.2s;}
    .bg-sticker6 { bottom: 68px; right: 13%; width: 66px; animation-delay: 2.7s;}
    .bg-sticker7 { top: 52%; right: 0; width: 54px; animation-delay: 0.9s;}
    .container {
      position: relative;
      z-index: 2;
      max-width: 420px;
      margin: 80px auto 0 auto;
      background: rgba(255,255,255,0.95);
      border-radius: 38px;
      box-shadow: 0 12px 48px #e1b0f799, 0 1px 0 #fff;
      padding: 44px 24px 48px 24px;
      backdrop-filter: blur(9px);
      border: 2.5px solid #ffb7eb66;
      position: relative;
    }
    .container:after {
      content: '';
      position: absolute;
      left: 12px; right: 12px; top: 12px; bottom: 12px;
      border-radius: 32px;
      pointer-events: none;
      border: 1.5px dashed #e273b333;
      z-index: 0;
    }
    .heart {
      color: #e273b3;
      font-size: 5em;
      animation: heartbeat 1s infinite;
      margin: 14px 0 2px 0;
      text-shadow: 0 4px 32px #ffb7eb77, 0 1px 0 #fff;
      font-family: 'Pacifico', cursive;
      letter-spacing: 2px;
      z-index: 2;
      position: relative;
    }
    @keyframes heartbeat {
      0% { transform: scale(1); }
      20% { transform: scale(1.17); }
      40% { transform: scale(1); }
      60% { transform: scale(1.17); }
      80% { transform: scale(1); }
    }
    .stickers {
      margin: 0 0 10px 0;
      display: flex;
      justify-content: center;
      gap: 10px;
      z-index: 2;
      position: relative;
    }
    .stickers img {
      margin: 0;
      border-radius: 16px;
      box-shadow: 0 2px 16px rgba(255, 102, 153, 0.14);
      transition: transform 0.18s;
      background: #fff6fa;
      border: 2px solid #fae2f3;
      width: 80px;
      height: 80px;
      object-fit: cover;
    }
    .stickers img:hover {
      transform: scale(1.14) rotate(-3deg);
      box-shadow: 0 4px 24px #ffb7eb77;
    }
    .message {
      font-size: 1.7em;
      color: #d6336c;
      margin: 14px 0 28px 0;
      font-family: 'Pacifico', cursive;
      text-shadow: 0 2px 16px #ffb7eb44;
      letter-spacing: 1px;
      line-height: 1.35;
      z-index: 2;
      position: relative;
    }
    button {
      padding: 17px 40px;
      font-size: 1.23em;
      color: white;
      background: linear-gradient(90deg, #e273b3 30%, #c782d2 100%);
      border: none;
      border-radius: 18px;
      cursor: pointer;
      margin-top: 14px;
      transition: background 0.18s, transform 0.18s, box-shadow 0.18s;
      box-shadow: 0 2px 18px #d6336c33;
      font-family: 'Quicksand', Arial, sans-serif;
      font-weight: bold;
      letter-spacing: 1px;
      z-index: 2;
      position: relative;
    }
    button:hover {
      background: linear-gradient(90deg, #c782d2 20%, #e273b3 100%);
      transform: scale(1.07);
      box-shadow: 0 8px 24px #e273b366;
    }
    /* Trái tim rơi */
    .falling-heart {
      position: fixed;
      top: -50px;
      font-size: 2em;
      pointer-events: none;
      animation: fall 3.6s linear forwards;
      z-index: 5;
      color: #e273b3;
      text-shadow: 0 2px 12px #ffb7eb55;
      will-change: transform, opacity;
    }
    @keyframes fall {
      to {
        transform: translateY(100vh) rotate(360deg) scale(0.75);
        opacity: 0.6;
      }
    }
    /* Cánh hoa rơi */
    .falling-flower {
      position: fixed;
      top: -50px;
      width: 32px;
      height: 32px;
      pointer-events: none;
      animation: flowerfall 6s linear forwards;
      z-index: 5;
      opacity: 0.9;
      will-change: transform, opacity;
      filter: drop-shadow(0 4px 16px #eeb4c9);
    }
    @keyframes flowerfall {
      to {
        transform: translateY(105vh) rotate(360deg) scale(0.85);
        opacity: 0.38;
      }
    }
    /* Responsive */
    @media(max-width: 500px) {
      .container {
        max-width: 98vw;
        padding: 18px 3vw 30px 3vw;
      }
      .stickers img { width: 54px; height: 54px; }
      .bg-glow { width: 74vw; height: 56vw; }
      .bg-sticker { width: 36px !important; }
    }
  </style>
</head>
<body>
  <!-- background glow and cute stickers -->
  <div class="bg-glow"></div>
  <img class="bg-sticker bg-sticker1" src="https://cdn.pixabay.com/photo/2017/01/31/21/22/cat-2022343_1280.png" alt="Mèo cute"/>
  <img class="bg-sticker bg-sticker2" src="https://cdn.pixabay.com/photo/2016/03/31/19/56/bunny-1296276_1280.png" alt="Thỏ dễ thương"/>
  <img class="bg-sticker bg-sticker3" src="https://cdn.pixabay.com/photo/2021/12/21/15/11/bear-6887787_1280.png" alt="Gấu con"/>
  <img class="bg-sticker bg-sticker4" src="https://cdn.pixabay.com/photo/2022/06/12/07/42/cat-7257760_1280.png" alt="Mèo hồng"/>
  <img class="bg-sticker bg-sticker5" src="https://cdn.pixabay.com/photo/2022/02/17/20/08/hamster-7018219_1280.png" alt="Hamster cute"/>
  <img class="bg-sticker bg-sticker6" src="https://cdn.pixabay.com/photo/2017/01/31/21/22/cat-2022343_1280.png" alt="Mèo cute"/>
  <img class="bg-sticker bg-sticker7" src="https://cdn.pixabay.com/photo/2016/03/31/19/56/bunny-1296276_1280.png" alt="Thỏ dễ thương"/>

  <div class="container" id="love-container">
    <div class="heart">❤️</div>
    <div class="stickers">
      <img src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" alt="Sticker dễ thương"/>
      <img src="https://media.giphy.com/media/l0MYRzcWP6o8z4RtG/giphy.gif" alt="Sticker dễ thương"/>
      <img src="https://media.giphy.com/media/26BRrSvJUa0crqw4E/giphy.gif" alt="Sticker dễ thương"/>
    </div>
    <div class="message">Em/Anh có đồng ý làm người yêu anh/em không? 🥰</div>
    <button onclick="showLove()">Đồng ý ❤️</button>
  </div>
  <script>
    // Hiệu ứng trái tim rơi
    function createFallingHeart() {
      const heart = document.createElement('div');
      heart.className = 'falling-heart';
      const hearts = ['❤️','💖','💕','💘','💗','💓','💞'];
      heart.textContent = hearts[Math.floor(Math.random() * hearts.length)];
      heart.style.left = Math.random() * (window.innerWidth - 30) + 'px';
      heart.style.fontSize = (Math.random() * 1.2 + 1.5) + 'em';
      document.body.appendChild(heart);
      heart.addEventListener('animationend', () => heart.remove());
    }
    // Hiệu ứng cánh hoa rơi
    function createFallingFlower() {
      const flower = document.createElement('img');
      flower.className = 'falling-flower';
      // Ảnh PNG cánh hoa nền trong suốt
      const flowerImages = [
        'https://pngimg.com/uploads/sakura/sakura_PNG17.png',
        'https://pngimg.com/uploads/sakura/sakura_PNG8.png',
        'https://pngimg.com/uploads/sakura/sakura_PNG21.png'
      ];
      flower.src = flowerImages[Math.floor(Math.random() * flowerImages.length)];
      flower.style.left = Math.random() * (window.innerWidth - 32) + 'px';
      flower.style.transform = `rotate(${Math.random()*360}deg) scale(${Math.random()*0.3+0.8})`;
      document.body.appendChild(flower);
      flower.addEventListener('animationend', () => flower.remove());
    }
    setInterval(createFallingHeart, 700);
    setInterval(createFallingFlower, 400);

    // Khi bấm nút Đồng ý
    function showLove() {
      document.getElementById("love-container").innerHTML = `
        <div class="heart">💖</div>
        <div class="stickers">
          <img src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" alt="Sticker dễ thương"/>
          <img src="https://media.giphy.com/media/l0MYRzcWP6o8z4RtG/giphy.gif" alt="Sticker dễ thương"/>
          <img src="https://media.giphy.com/media/26BRrSvJUa0crqw4E/giphy.gif" alt="Sticker dễ thương"/>
        </div>
        <div class="message">Anh/Em yêu em/anh rất nhiều! Cảm ơn vì đã đồng ý nhé! 😍</div>
        <button onclick="location.reload()">Xem lại lời tỏ tình</button>
      `;
    }
  </script>
</body>
</html>
