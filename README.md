<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, viewport-fit=cover">
    <title>Purr-fect Date? ✨🐱💖</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(145deg, #ffe6f0 0%, #ffccdd 100%);
            font-family: 'Quicksand', 'Segoe UI', 'Comic Neue', 'Poppins', cursive, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 16px;
            position: relative;
            overflow-x: hidden;
        }

        /* floating hearts background */
        .heart-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .heart-bg i {
            position: absolute;
            display: block;
            color: #ff4d6d;
            opacity: 0.4;
            animation: floatHeart 8s linear infinite;
            font-size: 1.5rem;
        }

        @keyframes floatHeart {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0.6; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* main card */
        .date-card {
            background: rgba(255, 250, 245, 0.96);
            backdrop-filter: blur(2px);
            border-radius: 48px;
            box-shadow: 0 20px 40px rgba(255, 80, 120, 0.25), 0 0 0 6px #fff9, 0 0 0 10px #ffb7c5;
            padding: 24px 20px 32px;
            max-width: 550px;
            width: 100%;
            text-align: center;
            z-index: 10;
            position: relative;
        }

        h1 {
            font-size: clamp(1.6rem, 6vw, 2rem);
            color: #b13e5c;
            margin-bottom: 16px;
            display: flex;
            justify-content: center;
            gap: 8px;
            flex-wrap: wrap;
            align-items: center;
        }

        .question-text {
            background: #fff0f3;
            border-radius: 40px;
            padding: 16px 12px;
            margin: 12px 0 20px;
            font-size: clamp(1.1rem, 4.5vw, 1.6rem);
            font-weight: bold;
            color: #c44569;
            box-shadow: inset 0 1px 4px #ffbfd0, 0 6px 12px rgba(0,0,0,0.05);
            border: 1px solid #ffb8c9;
            word-break: break-word;
        }

        .question-text p {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            flex-wrap: wrap;
        }

        .cat-emoji {
            font-size: clamp(1.8rem, 7vw, 2.2rem);
            cursor: pointer;
            transition: transform 0.2s;
            display: inline-block;
        }

        .cat-emoji:active {
            transform: scale(0.92);
        }

        /* buttons area */
        .buttons-area {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin: 20px 0 16px;
            flex-wrap: wrap;
            position: relative;
            min-height: 100px;
        }

        .btn {
            font-size: clamp(1.4rem, 5.5vw, 2rem);
            font-weight: bold;
            padding: 12px 24px;
            border: none;
            border-radius: 60px;
            cursor: pointer;
            font-family: inherit;
            box-shadow: 0 6px 0 rgba(0,0,0,0.1);
            transform: translateY(-2px);
            transition: transform 0.08s linear, box-shadow 0.08s linear;
            touch-action: manipulation;
        }

        .btn:active {
            transform: translateY(4px);
            box-shadow: 0 2px 0 rgba(0,0,0,0.1);
        }

        .btn-yes {
            background-color: #ff8aa8;
            color: white;
            text-shadow: 0 1px 2px #b13e5c;
            box-shadow: 0 6px 0 #b13e5c;
        }

        .btn-no {
            background-color: #b0a0b0;
            color: #2d2f36;
            box-shadow: 0 6px 0 #6e5a6e;
            position: relative;
            transition: left 0.12s ease, top 0.12s ease;
        }

        /* secret section */
        .secret-section {
            margin-top: 20px;
            transition: 0.3s;
            display: none;
        }

        .confirm-box {
            background: #ffeef4;
            border-radius: 48px;
            padding: 20px 16px;
            border: 2px dashed #ff99bb;
        }

        .cute-input {
            width: 90%;
            max-width: 280px;
            padding: 14px 18px;
            font-size: clamp(1rem, 4vw, 1.2rem);
            border-radius: 60px;
            border: 2px solid #ffbfd0;
            background: white;
            font-family: monospace;
            text-align: center;
            font-weight: bold;
            color: #c93a5e;
            outline: none;
            margin: 8px auto;
            display: block;
        }

        .cute-input:focus {
            border-color: #ff6f91;
            box-shadow: 0 0 0 3px #ffb7c5;
        }

        .submit-btn {
            background: #ff90ae;
            border: none;
            margin-top: 12px;
            padding: 10px 24px;
            border-radius: 40px;
            font-size: clamp(1rem, 4vw, 1.2rem);
            font-weight: bold;
            color: white;
            cursor: pointer;
            transition: 0.2s;
            display: inline-block;
        }

        .submit-btn:active {
            transform: scale(0.96);
            background: #ff6f91;
        }

        /* fullscreen celebration */
        .fullscreen-love {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, #ffddee, #ffb3c6);
            z-index: 1000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            gap: 20px;
            animation: fadeGlow 0.5s ease;
            backdrop-filter: blur(5px);
            padding: 20px;
            overflow-y: auto;
        }

        .fullscreen-love h2 {
            font-size: clamp(1.8rem, 8vw, 3.5rem);
            color: #b13e5c;
            text-shadow: 3px 3px 0 #ffdfe8;
            background: rgba(255, 255, 255, 0.9);
            padding: 16px 24px;
            border-radius: 60px;
            box-shadow: 0 15px 25px rgba(0,0,0,0.15);
            margin: 0 12px;
        }

        .cat-gallery {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 15px;
        }

        .cat-gallery span {
            font-size: clamp(2.5rem, 10vw, 4rem);
            cursor: pointer;
            transition: 0.15s;
        }

        .cat-gallery span:active {
            transform: scale(1.15);
        }

        .heart-rain {
            position: absolute;
            pointer-events: none;
            font-size: 1.8rem;
            animation: fall 2s linear forwards;
        }

        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }

        @keyframes fadeGlow {
            from { opacity: 0; transform: scale(0.96);}
            to { opacity: 1; transform: scale(1);}
        }

        footer {
            font-size: 0.7rem;
            margin-top: 20px;
            color: #e27c9e;
        }

        @media (max-width: 550px) {
            .date-card { padding: 20px 16px 28px; border-radius: 40px; }
            .buttons-area { gap: 20px; min-height: 90px; }
            .btn { padding: 10px 20px; min-width: 100px; }
        }

        @media (max-width: 400px) {
            .buttons-area { gap: 15px; }
            .btn { padding: 8px 18px; min-width: 85px; font-size: 1.3rem; }
        }

        .shake {
            animation: shakeAnim 0.3s ease-in-out 0s 2;
        }
        @keyframes shakeAnim {
            0% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
            100% { transform: translateX(0); }
        }

        .cute-popup {
            position: fixed;
            top: 30%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(255, 240, 245, 0.98);
            backdrop-filter: blur(10px);
            color: #c93a5e;
            padding: 18px 28px;
            border-radius: 60px;
            font-size: clamp(1.1rem, 4.5vw, 1.4rem);
            font-weight: bold;
            box-shadow: 0 20px 35px rgba(0,0,0,0.2);
            border: 3px solid #ff99bb;
            z-index: 1100;
            text-align: center;
            max-width: 85vw;
            line-height: 1.4;
            pointer-events: none;
            animation: popFade 1.8s forwards;
        }
        @keyframes popFade {
            0% { opacity: 0; transform: translate(-50%, -40%); }
            15% { opacity: 1; transform: translate(-50%, -50%); }
            85% { opacity: 1; transform: translate(-50%, -50%); }
            100% { opacity: 0; transform: translate(-50%, -55%); visibility: hidden; }
        }
    </style>
</head>
<body>

<div class="heart-bg" id="heartBg"></div>

<div class="date-card" id="mainCard">
    <h1>
        <span>🐱💗</span> Meow? <span>💗🐱</span>
    </h1>
    <div class="question-text">
        <p>
            <span>📅🍿</span> will you go on a date with me tomorrow to the cineworld hounslow @ 3pm <span>🍿🐱</span>
        </p>
    </div>
    
    <!-- Cute interactive cats (click them to meow!) -->
    <div style="display: flex; justify-content: center; gap: 18px; margin-bottom: 12px; flex-wrap: wrap;">
        <span class="cat-emoji" data-cat="meow1">🐈‍⬛💖</span>
        <span class="cat-emoji" data-cat="meow2">🐱🌸</span>
        <span class="cat-emoji" data-cat="meow3">😻🎀</span>
    </div>

    <div class="buttons-area" id="buttonArea">
        <button class="btn btn-yes" id="yesButton">💖 YES 💖</button>
        <button class="btn btn-no" id="noButton">😾 NO 😾</button>
    </div>
    
    <div class="secret-section" id="secretSection">
        <div class="confirm-box">
            <p style="font-size:clamp(1rem,4vw,1.2rem); margin-bottom:12px;">🎀 type the magic words 🎀</p>
            <input type="text" id="loveInput" class="cute-input" placeholder="I love you" autocomplete="off" enterkeyhint="done">
            <br>
            <button id="submitLoveBtn" class="submit-btn">💌 submit & confirm 💌</button>
        </div>
    </div>
    <footer>✨ tap on cats for meows! ✨</footer>
</div>

<script>
    // ---------- AUDIO (mobile-friendly Web Audio) ----------
    let audioCtx = null;
    
    function initAudio() {
        if (audioCtx) return audioCtx;
        try {
            const AudioContextClass = window.AudioContext || window.webkitAudioContext;
            audioCtx = new AudioContextClass();
            return audioCtx;
        } catch(e) {
            console.log("Web Audio not supported");
            return null;
        }
    }
    
    function playMeowSound(angry = false) {
        let ctx = initAudio();
        if (!ctx) return;
        
        if (ctx.state === 'suspended') {
            ctx.resume();
        }
        
        const now = ctx.currentTime;
        const oscillator = ctx.createOscillator();
        const gainNode = ctx.createGain();
        oscillator.connect(gainNode);
        gainNode.connect(ctx.destination);
        
        if (angry) {
            // Angry cat: growl + hiss
            oscillator.type = 'sawtooth';
            oscillator.frequency.setValueAtTime(180, now);
            oscillator.frequency.exponentialRampToValueAtTime(85, now + 0.4);
            gainNode.gain.setValueAtTime(0.28, now);
            gainNode.gain.exponentialRampToValueAtTime(0.001, now + 0.75);
            oscillator.start();
            oscillator.stop(now + 0.75);
            
            // Hiss noise
            const bufferSize = 2048;
            const noiseNode = ctx.createScriptProcessor(bufferSize, 1, 1);
            noiseNode.onaudioprocess = function(e) {
                const output = e.outputBuffer.getChannelData(0);
                for (let i = 0; i < bufferSize; i++) {
                    output[i] = (Math.random() * 2 - 1) * 0.12;
                }
            };
            const noiseGain = ctx.createGain();
            noiseGain.gain.setValueAtTime(0.18, now);
            noiseGain.gain.exponentialRampToValueAtTime(0.001, now + 0.35);
            noiseNode.connect(noiseGain);
            noiseGain.connect(ctx.destination);
            setTimeout(() => {
                try { noiseNode.disconnect(); noiseNode.onaudioprocess = null; } catch(e) {}
            }, 400);
        } else {
            // Cute meow
            oscillator.type = 'sine';
            oscillator.frequency.setValueAtTime(820, now);
            oscillator.frequency.exponentialRampToValueAtTime(420, now + 0.18);
            gainNode.gain.setValueAtTime(0.22, now);
            gainNode.gain.exponentialRampToValueAtTime(0.001, now + 0.48);
            oscillator.start();
            oscillator.stop(now + 0.48);
        }
    }
    
    function playHappyMeow() { playMeowSound(false); }
    function playAngryMeow() { playMeowSound(true); }
    
    // Helper: mini heart near element
    function createMiniHeart(element) {
        const heart = document.createElement('div');
        heart.innerHTML = '💖';
        heart.style.position = 'fixed';
        heart.style.fontSize = '1.6rem';
        heart.style.pointerEvents = 'none';
        heart.style.zIndex = '999';
        const rect = element.getBoundingClientRect();
        heart.style.left = rect.left + rect.width/2 - 12 + 'px';
        heart.style.top = rect.top - 15 + 'px';
        heart.style.transition = 'all 0.7s ease-out';
        heart.style.opacity = '1';
        document.body.appendChild(heart);
        setTimeout(() => {
            heart.style.transform = 'translateY(-45px)';
            heart.style.opacity = '0';
            setTimeout(() => heart.remove(), 800);
        }, 10);
    }
    
    // Cat click handlers
    const catSpans = document.querySelectorAll('.cat-emoji');
    catSpans.forEach(cat => {
        const handler = (e) => {
            e.stopPropagation();
            playHappyMeow();
            createMiniHeart(cat);
        };
        cat.addEventListener('click', handler);
        cat.addEventListener('touchstart', handler);
    });
    
    // Moving NO button logic
    const noBtn = document.getElementById('noButton');
    const yesBtn = document.getElementById('yesButton');
    const buttonArea = document.getElementById('buttonArea');
    const secretSection = document.getElementById('secretSection');
    const loveInput = document.getElementById('loveInput');
    const submitBtn = document.getElementById('submitLoveBtn');
    
    let moveTimeout = false;
    
    function moveNoButton() {
        if (moveTimeout) return;
        moveTimeout = true;
        
        const areaRect = buttonArea.getBoundingClientRect();
        const btnRect = noBtn.getBoundingClientRect();
        const maxX = Math.max(10, areaRect.width - btnRect.width - 15);
        const maxY = Math.max(10, areaRect.height - btnRect.height - 15);
        let randomX = Math.random() * maxX;
        let randomY = Math.random() * maxY;
        randomX = Math.min(Math.max(5, randomX), maxX);
        randomY = Math.min(Math.max(5, randomY), maxY);
        
        noBtn.style.position = 'absolute';
        noBtn.style.left = randomX + 'px';
        noBtn.style.top = randomY + 'px';
        noBtn.style.transform = 'rotate(' + (Math.random() * 6 - 3) + 'deg)';
        
        playAngryMeow();
        
        const angryEffect = document.createElement('div');
        angryEffect.innerText = '😾💢';
        angryEffect.style.position = 'fixed';
        angryEffect.style.left = (btnRect.left + btnRect.width/2 - 18) + 'px';
        angryEffect.style.top = (btnRect.top - 25) + 'px';
        angryEffect.style.fontSize = '1.8rem';
        angryEffect.style.pointerEvents = 'none';
        angryEffect.style.zIndex = '999';
        angryEffect.style.transition = 'opacity 0.5s';
        document.body.appendChild(angryEffect);
        setTimeout(() => {
            angryEffect.style.opacity = '0';
            setTimeout(() => angryEffect.remove(), 400);
        }, 450);
        
        setTimeout(() => { moveTimeout = false; }, 150);
    }
    
    // Event listeners for NO button
    const noHandler = (e) => {
        e.preventDefault();
        e.stopPropagation();
        if (!moveTimeout) moveNoButton();
    };
    noBtn.addEventListener('click', noHandler);
    noBtn.addEventListener('touchstart', noHandler);
    noBtn.addEventListener('mouseenter', () => { if (!moveTimeout) moveNoButton(); });
    
    // Custom cute popup
    function showCutePopup(msg) {
        const popup = document.createElement('div');
        popup.className = 'cute-popup';
        popup.innerText = msg;
        document.body.appendChild(popup);
        setTimeout(() => { if(popup) popup.remove(); }, 2000);
    }
    
    let yesClickedFlag = false;
    
    // YES button action
    function onYesClick() {
        if (yesClickedFlag) return;
        yesClickedFlag = true;
        playHappyMeow();
        showCutePopup("I knew you'd click yes <33, type I love you in the box to confirm the date 🥺💖");
        secretSection.style.display = 'block';
        createHeartExplosion();
        setTimeout(() => {
            secretSection.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }, 200);
    }
    
    yesBtn.addEventListener('click', onYesClick);
    yesBtn.addEventListener('touchstart', onYesClick);
    
    function createHeartExplosion() {
        for(let i=0; i<18; i++) {
            const heart = document.createElement('div');
            heart.innerHTML = ['💖','🌸','🐱','💗','✨','🎀','❤️'][Math.floor(Math.random()*7)];
            heart.style.position = 'fixed';
            heart.style.left = (window.innerWidth/2 - 20 + (Math.random() * 90 - 45)) + 'px';
            heart.style.top = (window.innerHeight/2 - 30) + 'px';
            heart.style.fontSize = '1.7rem';
            heart.style.pointerEvents = 'none';
            heart.style.zIndex = '999';
            heart.style.transition = 'all 0.9s ease-out';
            document.body.appendChild(heart);
            setTimeout(() => {
                heart.style.transform = `translate(${Math.random() * 220 - 110}px, ${Math.random() * -170 - 60}px) rotate(${Math.random()*360}deg)`;
                heart.style.opacity = '0';
                setTimeout(() => heart.remove(), 1000);
            }, 10);
        }
    }
    
    // SUBMIT LOGIC
    function onSubmit() {
        const userText = loveInput.value.trim().toLowerCase();
        if (userText === "i love you") {
            showFullscreenLove();
        } else {
            const errorDiv = document.createElement('div');
            errorDiv.innerText = "😿 type exactly 'I love you' to confirm 😿";
            errorDiv.style.position = 'fixed';
            errorDiv.style.bottom = '80px';
            errorDiv.style.left = '50%';
            errorDiv.style.transform = 'translateX(-50%)';
            errorDiv.style.backgroundColor = '#ffc0d0';
            errorDiv.style.padding = '10px 20px';
            errorDiv.style.borderRadius = '50px';
            errorDiv.style.color = '#a12a4a';
            errorDiv.style.fontWeight = 'bold';
            errorDiv.style.zIndex = '1001';
            errorDiv.style.fontSize = '0.9rem';
            errorDiv.style.textAlign = 'center';
            errorDiv.style.maxWidth = '90vw';
            errorDiv.style.whiteSpace = 'normal';
            document.body.appendChild(errorDiv);
            setTimeout(() => errorDiv.remove(), 1700);
            loveInput.classList.add('shake');
            setTimeout(() => loveInput.classList.remove('shake'), 500);
            loveInput.focus();
        }
    }
    
    submitBtn.addEventListener('click', onSubmit);
    submitBtn.addEventListener('touchstart', onSubmit);
    
    // Allow Enter key on input
    loveInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') {
            e.preventDefault();
            onSubmit();
        }
    });
    
    function showFullscreenLove() {
        const existing = document.querySelector('.fullscreen-love');
        if(existing) existing.remove();
        
        const fullDiv = document.createElement('div');
        fullDiv.className = 'fullscreen-love';
        fullDiv.innerHTML = `
            <h2>💗 I love you more baby 💗</h2>
            <div class="cat-gallery">
                <span class="celeb-cat">🐱💕</span>
                <span class="celeb-cat">😻💖</span>
                <span class="celeb-cat">🐈‍⬛🌸</span>
                <span class="celeb-cat">😽🎀</span>
                <span class="celeb-cat">🐱✨</span>
            </div>
            <div style="font-size:clamp(1.3rem,6vw,2rem); letter-spacing:8px;">❤️ 🧡 💛 💚 💙 💜</div>
        `;
        document.body.appendChild(fullDiv);
        
        // Celebration cats with meow
        const celebCats = fullDiv.querySelectorAll('.celeb-cat');
        const catHandler = (e) => {
            e.stopPropagation();
            playHappyMeow();
            const floatHeart = document.createElement('div');
            floatHeart.innerText = '💖';
            floatHeart.style.position = 'fixed';
            floatHeart.style.left = e.clientX + 'px';
            floatHeart.style.top = e.clientY + 'px';
            floatHeart.style.fontSize = '2rem';
            floatHeart.style.pointerEvents = 'none';
            floatHeart.style.transition = 'transform 0.5s ease-out, opacity 0.7s';
            document.body.appendChild(floatHeart);
            setTimeout(() => {
                floatHeart.style.transform = 'translateY(-70px)';
                floatHeart.style.opacity = '0';
                setTimeout(() => floatHeart.remove(), 700);
            }, 20);
        };
        celebCats.forEach(cat => {
            cat.style.cursor = 'pointer';
            cat.addEventListener('click', catHandler);
            cat.addEventListener('touchstart', catHandler);
        });
        
        // Heart rain
        for(let i=0;i<55;i++) {
            const heartRain = document.createElement('div');
            heartRain.innerHTML = ['❤️','💖','🌸','🐱','💗','🎀'][Math.floor(Math.random()*6)];
            heartRain.classList.add('heart-rain');
            heartRain.style.left = Math.random() * 100 + '%';
            heartRain.style.fontSize = (Math.random() * 1.5 + 1) + 'rem';
            heartRain.style.animationDuration = Math.random() * 2 + 1.3 + 's';
            heartRain.style.position = 'absolute';
            heartRain.style.top = '-20px';
            fullDiv.appendChild(heartRain);
            setTimeout(() => heartRain.remove(), 2700);
        }
        
        const closeHint = document.createElement('div');
        closeHint.innerText = '✨ tap anywhere to close ✨';
        closeHint.style.position = 'absolute';
        closeHint.style.bottom = '25px';
        closeHint.style.fontSize = '0.85rem';
        closeHint.style.background = '#fff0f0cc';
        closeHint.style.padding = '6px 16px';
        closeHint.style.borderRadius = '40px';
        closeHint.style.color = '#b13e5c';
        fullDiv.appendChild(closeHint);
        fullDiv.addEventListener('click', () => fullDiv.remove());
        
        playHappyMeow();
    }
    
    // Generate floating hearts background
    function generateFloatingHearts() {
        const bgContainer = document.getElementById('heartBg');
        for(let i=0; i<40; i++) {
            const heart = document.createElement('i');
            heart.innerHTML = ['❤️','💖','🌸','🐱','💗'][Math.floor(Math.random()*5)];
            heart.style.left = Math.random() * 100 + '%';
            heart.style.fontSize = (Math.random() * 1.2 + 0.8) + 'rem';
            heart.style.animationDuration = (Math.random() * 7 + 4) + 's';
            heart.style.animationDelay = Math.random() * 9 + 's';
            heart.style.opacity = Math.random() * 0.5 + 0.2;
            bgContainer.appendChild(heart);
        }
    }
    generateFloatingHearts();
    
    // Set up button area positioning
    buttonArea.style.position = 'relative';
    noBtn.style.position = 'relative';
    
    // Resume audio on first user interaction (mobile autoplay policy)
    function resumeAudioOnFirstTouch() {
        if (audioCtx && audioCtx.state === 'suspended') {
            audioCtx.resume();
        }
        document.body.removeEventListener('touchstart', resumeAudioOnFirstTouch);
        document.body.removeEventListener('click', resumeAudioOnFirstTouch);
    }
    document.body.addEventListener('touchstart', resumeAudioOnFirstTouch);
    document.body.addEventListener('click', resumeAudioOnFirstTouch);
</script>
</body>
</html>
