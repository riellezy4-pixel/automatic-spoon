<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Favorite Person 🤍</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Montserrat:wght@300;400&display=swap" rel="stylesheet">
    <style>
        :root { --pink: #ff85a1; --soft: #fff5f7; --text: #4a4a4a; }
        body { margin: 0; font-family: 'Montserrat', sans-serif; background: var(--soft); color: var(--text); overflow-x: hidden; }
        
        /* Access Screen */
        #lock { position: fixed; inset: 0; background: white; z-index: 100; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; }
        input { padding: 12px; border: 2px solid var(--pink); border-radius: 25px; margin: 10px; outline: none; text-align: center; font-size: 16px; }
        
        .container { max-width: 600px; margin: 0 auto; padding: 40px 20px; text-align: center; }
        h1 { font-family: 'Dancing Script', cursive; font-size: 2.5rem; color: var(--pink); }
        
        /* Buttons */
        .btn-group { margin-top: 30px; position: relative; height: 120px; }
        button { padding: 15px 35px; border-radius: 50px; border: none; font-weight: bold; cursor: pointer; transition: 0.3s; touch-action: manipulation; }
        #yesBtn { background: var(--pink); color: white; font-size: 1.2rem; position: relative; z-index: 10; }
        #noBtn { background: #eee; color: #888; position: absolute; left: 50%; transform: translateX(-50%); top: 60px; }

        #content { display: none; opacity: 0; transition: 1s; }
        
        /* The Letter Box */
        .letter-paper { 
            background: white; 
            padding: 30px; 
            border-radius: 15px; 
            box-shadow: 0 10px 30px rgba(0,0,0,0.05); 
            text-align: left; 
            line-height: 1.8; 
            font-family: 'Dancing Script', cursive; 
            font-size: 1.3rem; 
            white-space: pre-line;
            margin-top: 30px;
            border: 2px dashed var(--pink);
        }

        .spotify-container { margin-top: 30px; border-radius: 15px; overflow: hidden; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        
        .floating-heart { position: fixed; color: var(--pink); pointer-events: none; z-index: -1; animation: float 4s linear infinite; }
        @keyframes float { 0% { transform: translateY(100vh) scale(1); opacity: 1; } 100% { transform: translateY(-10vh) scale(1.5); opacity: 0; } }
    </style>
</head>
<body>

    <div id="lock">
        <h1>A message for you... ✨</h1>
        <input type="password" id="pass" placeholder="Secret password">
        <button onclick="unlock()" style="background: var(--pink); color: white;">Open 🤍</button>
        <p style="font-size: 0.7rem; color: #ccc; margin-top: 15px;">Hint: mylove</p>
    </div>

    <div class="container">
        <div id="question-area">
            <h1>Will you be my Valentine, My Love? 🌹</h1>
            <div class="btn-group">
                <button id="yesBtn" onclick="reveal()">YES!</button>
                <button id="noBtn" onmouseover="moveNo()" onclick="moveNo()">No</button>
            </div>
        </div>

        <div id="content">
            <h1>For You, Always 🤍</h1>

            <div class="spotify-container">
                <iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/1yYmP6pG9vX9YvS9vX9YvS" width="100%" height="152" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
            </div>

            <div class="letter-paper" id="letterText"></div>
            
            <p style="margin-top: 40px; font-family: 'Dancing Script'; font-size: 1.5rem; color: var(--pink);">I love you! 🤍</p>
        </div>
    </div>

    <script>
        // PASTE YOUR FULL LETTER BETWEEN THE BACKTICKS BELOW
        const fullLetter = `My love,

I’ve been thinking about you a lot lately, about how you walked into my life in the most unexpected way and somehow made everything feel lighter. There are days when the world feels loud and heavy, and then there’s you—your laugh, your presence, the calm you bring even when things get messy. 

(I've kept this short so you can paste your full beautiful text here!)

With all my love,
Always yours 🤍`;

        function unlock() {
            if(document.getElementById('pass').value.toLowerCase() === "mylove") {
                document.getElementById('lock').style.display = "none";
            } else { alert("Try again, beautiful! 🌸"); }
        }

        function moveNo() {
            const btn = document.getElementById('noBtn');
            const x = Math.random() * (window.innerWidth - btn.offsetWidth);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight);
            btn.style.left = x + 'px'; btn.style.top = y + 'px';
        }

        function reveal() {
            document.getElementById('question-area').style.display = "none";
            const content = document.getElementById('content');
            content.style.display = "block";
            setTimeout(() => content.style.opacity = "1", 50);
            setInterval(createHeart, 300);

            let i = 0;
            const target = document.getElementById('letterText');
            function type() {
                if (i < fullLetter.length) {
                    target.textContent += fullLetter.charAt(i);
                    i++;
                    setTimeout(type, 35);
                }
            }
            type();
        }

        function createHeart() {
            const h = document.createElement('div');
            h.classList.add('floating-heart');
            h.innerHTML = ['❤️', '💖', '🤍', '🌸', '✨'][Math.floor(Math.random() * 5)];
            h.style.left = Math.random() * 100 + "vw";
            h.style.fontSize = (Math.random() * 20 + 15) + "px";
            document.body.appendChild(h);
            setTimeout(() => h.remove(), 4000);
        }
    </script>
</body>
</html>
