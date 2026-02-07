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
        
        #lock { position: fixed; inset: 0; background: white; z-index: 100; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; }
        input { padding: 12px; border: 2px solid var(--pink); border-radius: 25px; margin: 10px; outline: none; text-align: center; font-size: 16px; }
        
        .container { max-width: 600px; margin: 0 auto; padding: 40px 20px; text-align: center; }
        h1 { font-family: 'Dancing Script', cursive; font-size: 2.5rem; color: var(--pink); }
        
        .btn-group { margin-top: 30px; position: relative; height: 120px; }
        button { padding: 15px 35px; border-radius: 50px; border: none; font-weight: bold; cursor: pointer; transition: 0.3s; touch-action: manipulation; }
        #yesBtn { background: var(--pink); color: white; font-size: 1.2rem; position: relative; z-index: 10; }
        #noBtn { background: #eee; color: #888; position: absolute; left: 50%; transform: translateX(-50%); top: 60px; }

        #content { display: none; opacity: 0; transition: 1s; }
        
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
                <iframe style="border-radius:12px" src="https://open.spotify.com/track/4mc3rUoMwwiNTHA4al9nNd?si=FjiiHQGYRpyh8JVtXS2OoA" width="100%" height="152" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
            </div>

            <div class="letter-paper" id="letterText"></div>
            
            <p style="margin-top: 40px; font-family: 'Dancing Script'; font-size: 1.5rem; color: var(--pink);">I love you! 🤍</p>
        </div>
    </div>

    <script>
        const fullLetter = `My love,

I’ve been thinking about you a lot lately, about how you walked into my life in the most unexpected way and somehow made everything feel lighter. There are days when the world feels loud and heavy, and then there’s you—your laugh, your presence, the calm you bring even when things get messy. I don’t always say this out loud, but having you in my life is one of the things I’m most grateful for. You remind me that love doesn’t have to be perfect to be real. It just has to be honest.

Thank you for choosing me every day, even on the days when I’m not at my best. Thank you for being patient when I’m moody, tired, or quiet. Thank you for listening to my stories, even the random ones that don’t always make sense. Thank you for caring about the small details—how I’m feeling, what made me smile, what made my day hard. Those little things might seem simple, but they mean so much to me. They make me feel seen, heard, and understood.

I love how you make ordinary moments feel special. The simple talks, the jokes we share, the times we just sit and exist together—those moments are my favorite. They remind me that love isn’t only about big gestures. It’s about choosing to show up, choosing to care, choosing to stay kind even when things aren’t easy. With you, I’ve learned that comfort can be beautiful. I’ve learned that peace can feel like home.
You inspire me to be better—not in a pressured way, but in a gentle way.

You make me want to grow, to be more patient, to be more understanding, to be braver with my feelings. When I doubt myself, you remind me of my worth. When I’m scared to try, you encourage me to take the step anyway. You don’t just love me; you believe in me, and that’s something I hold close to my heart.

I know we’re both still learning. We’re learning how to communicate, how to handle misunderstandings, how to be there for each other when life gets tough. There will be days when we don’t agree, days when we’re tired, days when emotions run high. But I want you to know that I choose to work through those days with you. I choose patience over pride. I choose honesty over silence. I choose us, not because we’re perfect, but because we’re willing to grow together.

If I ever get quiet, please know it doesn’t mean I love you any less. Sometimes my heart just needs a moment to breathe. And if you ever feel unsure, I hope you remember this: you matter to me. Your feelings matter to me. Your dreams matter to me. I care about the things that make you excited, the things that worry you, and the things you’re still figuring out. I want to be someone who supports you, not someone who holds you back.

I admire your strength, even when you don’t see it in yourself. I admire how you try, how you keep going, how you show up for the people you care about. You don’t have to be perfect for me to love you. I love you for who you are, for the effort you give, for the heart you carry. And on the days you feel like you’re not enough, I hope you hear my voice in your mind telling you that you are more than enough.
Being with you makes me hopeful about the future—not in a pressured way, but in a gentle, steady way. I imagine more shared laughs, more late-night talks, more quiet moments where everything feels okay because we’re together. I don’t know exactly what tomorrow will bring, but I know I want to face it with you by my side, learning, growing, and choosing each other again and again.

Thank you for being my safe place. Thank you for being my comfort. Thank you for being my favorite person to talk to when my day has been long. Thank you for reminding me that love can be kind, patient, and real. I promise to keep trying to be someone who listens, who understands, and who shows love not just with words, but with actions.

No matter how busy life gets, no matter how loud the world becomes, I hope you always remember this: you are important to me. You are valued. You are cared for deeply. I’m proud of you for who you are and for who you’re becoming. And I’m grateful that out of all the people in this world, I get to walk this part of life with you.

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
                    setTimeout(type, 30);
                    if (i % 5 === 0) window.scrollTo(0, document.body.scrollHeight);
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
