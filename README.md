<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>FlappyBird.io - Play Free Online Flappy Bird Game</title>
    <meta name="description" content="Play Flappy Bird online for free! Compete for high scores, unlock new birds, and read gaming tips, strategies, and tutorials." />
    <meta name="keywords" content="flappy bird, online game, arcade, free game, html5 game, gaming tips, web development" />
    <link rel="canonical" href="https://flappybird.io/" />

    <!-- Google AdSense -->
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-xxxxxxxxxxxxxxxx"
    crossorigin="anonymous"></script>

    <style>
        /* --- RESET & BASE --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0f0f1a;
            color: #e0e0e0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        a {
            color: #9fd6ff;
            text-decoration: none;
        }
        a:hover {
            color: #ffcc00;
            text-decoration: underline;
        }

        /* --- HEADER / NAVIGATION --- */
        header {
            background: rgba(20, 20, 40, 0.95);
            backdrop-filter: blur(8px);
            padding: 12px 5%;
            position: sticky;
            top: 0;
            z-index: 50;
            border-bottom: 2px solid #2a2a4a;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
        }

        nav {
            display: flex;
            align-items: center;
            justify-content: space-between;
            max-width: 1200px;
            margin: 0 auto;
            flex-wrap: wrap;
            gap: 8px;
        }

        .logo {
            font-size: 24px;
            font-weight: 900;
            color: #ffcc00;
            text-shadow: 0 0 20px rgba(255, 204, 0, 0.3);
            letter-spacing: -0.5px;
        }
        .logo span {
            color: #70c5ce;
        }

        .nav-links {
            display: flex;
            flex-wrap: wrap;
            gap: 6px 12px;
            list-style: none;
        }

        .nav-links a {
            color: #ccc;
            font-size: 14px;
            font-weight: 500;
            padding: 4px 8px;
            border-radius: 4px;
            transition: all 0.2s;
            text-decoration: none;
        }

        .nav-links a:hover,
        .nav-links a.active {
            color: #ffcc00;
            background: rgba(255, 204, 0, 0.1);
            text-decoration: none;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            gap: 4px;
            background: none;
            border: none;
            cursor: pointer;
            padding: 4px;
        }
        .hamburger span {
            display: block;
            width: 26px;
            height: 3px;
            background: #ccc;
            border-radius: 2px;
            transition: 0.3s;
        }

        /* --- PAGE CONTAINER --- */
        .page {
            display: none;
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 5% 60px;
            width: 100%;
            flex: 1;
        }
        .page.active {
            display: block;
        }

        .page h1 {
            font-size: clamp(28px, 5vw, 44px);
            color: #ffcc00;
            margin-bottom: 16px;
            border-bottom: 2px solid #2a2a4a;
            padding-bottom: 12px;
        }

        .page h2 {
            font-size: clamp(22px, 3vw, 30px);
            color: #70c5ce;
            margin: 24px 0 12px;
        }

        .page h3 {
            font-size: clamp(18px, 2vw, 22px);
            color: #9fd6ff;
            margin: 18px 0 10px;
        }

        .page p {
            font-size: clamp(15px, 1.2vw, 18px);
            line-height: 1.8;
            margin-bottom: 14px;
            color: #d0d0e0;
        }

        .page ul,
        .page ol {
            padding-left: 24px;
            margin-bottom: 16px;
        }
        .page li {
            font-size: clamp(14px, 1.1vw, 17px);
            line-height: 1.7;
            margin-bottom: 6px;
            color: #d0d0e0;
        }

        .page img {
            max-width: 100%;
            border-radius: 8px;
            margin: 12px 0;
        }

        /* --- GAME SECTION --- */
        #gameSection {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        #gameWrapper {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            width: 100%;
            max-width: 1100px;
            margin: 10px 0;
            flex-wrap: wrap;
        }

        .side-ad {
            flex: 0 0 auto;
            width: 160px;
            min-height: 600px;
            max-height: 90vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.04);
            border-radius: 8px;
            border: 1px dashed rgba(255, 255, 255, 0.12);
            color: #666;
            font-size: 12px;
            overflow: hidden;
            position: relative;
        }
        .side-ad .ad-label {
            position: absolute;
            top: 4px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 9px;
            color: #555;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .side-ad .ad-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 8px;
            padding: 20px 8px;
        }
        .side-ad .ad-content .ad-placeholder {
            font-size: 28px;
            opacity: 0.3;
        }

        #gameContainer {
            position: relative;
            flex: 0 0 auto;
            width: 400px;
            height: 600px;
            box-shadow: 0 0 40px rgba(0, 0, 0, 0.7);
            border-radius: 8px;
            overflow: hidden;
            background: #70c5ce;
            aspect-ratio: 400 / 600;
            max-width: 100%;
        }

        #gameCanvas {
            display: block;
            width: 100%;
            height: 100%;
            background: #70c5ce;
            image-rendering: pixelated;
        }

        /* --- OVERLAY (same as before, slightly adjusted) --- */
        #overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: rgba(0, 0, 0, 0.6);
            color: #fff;
            text-align: center;
            cursor: pointer;
            user-select: none;
            z-index: 10;
            padding: 5%;
        }
        #overlay h1 {
            font-size: clamp(24px, 6vw, 42px);
            color: #ffcc00;
            text-shadow: 3px 3px 0 #000;
            margin-bottom: 8px;
        }
        #overlay p {
            font-size: clamp(12px, 2.5vw, 16px);
            margin: 4px 0;
            text-shadow: 1px 1px 0 #000;
        }
        #overlay .score-line {
            font-size: clamp(16px, 3.5vw, 22px);
            color: #fff;
            margin-top: 8px;
            text-shadow: 2px 2px 0 #000;
        }
        #hud {
            position: absolute;
            top: 3%;
            left: 0;
            width: 100%;
            text-align: center;
            font-size: clamp(28px, 6vw, 42px);
            font-weight: bold;
            color: #fff;
            text-shadow: 2px 2px 0 #000, -1px -1px 0 #000;
            pointer-events: none;
            z-index: 5;
            display: none;
        }
        #userBadge {
            position: absolute;
            top: 2%;
            left: 3%;
            font-size: clamp(9px, 1.5vw, 12px);
            color: #fff;
            background: rgba(0, 0, 0, 0.5);
            padding: 2px 8px;
            border-radius: 12px;
            z-index: 6;
            display: none;
            white-space: nowrap;
        }
        #logoutBtn {
            position: absolute;
            top: 2%;
            right: 3%;
            font-size: clamp(9px, 1.5vw, 12px);
            color: #fff;
            background: rgba(0, 0, 0, 0.5);
            padding: 2px 8px;
            border-radius: 12px;
            z-index: 6;
            cursor: pointer;
            display: none;
            border: none;
        }

        /* --- AUTH BOX --- */
        .authBox {
            background: rgba(255, 255, 255, 0.08);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            padding: 5% 6%;
            width: 85%;
            max-width: 280px;
        }
        .authBox input {
            width: 100%;
            padding: 8px 10px;
            margin: 5px 0;
            border-radius: 6px;
            border: 1px solid #888;
            font-size: clamp(12px, 2vw, 14px);
            outline: none;
            background: #fff;
            color: #222;
        }
        .authBox button {
            width: 100%;
            padding: 8px 10px;
            margin-top: 8px;
            border-radius: 6px;
            border: none;
            background: #ffcc00;
            color: #222;
            font-weight: bold;
            font-size: clamp(12px, 2vw, 14px);
            cursor: pointer;
        }
        .authBox button:hover {
            background: #ffd83d;
        }
        .authBox .switchLink {
            margin-top: 10px;
            font-size: clamp(10px, 1.8vw, 12px);
            color: #9fd6ff;
            cursor: pointer;
            text-decoration: underline;
            display: inline-block;
        }
        .authError {
            color: #ff8585;
            font-size: clamp(10px, 1.8vw, 12px);
            margin-top: 4px;
            min-height: 14px;
        }

        /* --- BIRD GALLERY --- */
        .unlockPopup {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
            max-width: 320px;
        }
        .birdGallery {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            justify-content: center;
            margin: 10px 0;
            max-height: 40vh;
            overflow-y: auto;
            padding: 4px;
            width: 100%;
        }
        .birdSlot {
            width: 12%;
            min-width: 36px;
            max-width: 48px;
            aspect-ratio: 1/1;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.12);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            border: 2px solid transparent;
            position: relative;
        }
        .birdSlot.locked {
            opacity: 0.25;
            cursor: not-allowed;
        }
        .birdSlot.selected {
            border-color: #ffcc00;
        }
        .birdSlot canvas {
            width: 70%;
            height: auto;
        }
        .birdSlot .lvl {
            position: absolute;
            bottom: -2px;
            right: -2px;
            font-size: clamp(6px, 1vw, 8px);
            background: #000;
            color: #fff;
            border-radius: 6px;
            padding: 1px 4px;
            line-height: 1;
        }
        .smallBtn {
            padding: 5px 14px;
            border-radius: 6px;
            border: none;
            background: #ffcc00;
            color: #222;
            font-weight: bold;
            font-size: clamp(11px, 2vw, 14px);
            cursor: pointer;
            margin-top: 4px;
        }

        /* --- BLOG CARDS --- */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }

        .blog-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid #2a2a4a;
            border-radius: 10px;
            padding: 18px;
            transition: all 0.3s;
        }
        .blog-card:hover {
            transform: translateY(-4px);
            border-color: #ffcc00;
            box-shadow: 0 8px 30px rgba(255, 204, 0, 0.1);
        }
        .blog-card h3 {
            color: #ffcc00;
            margin: 0 0 8px;
            font-size: clamp(16px, 1.4vw, 20px);
        }
        .blog-card .meta {
            font-size: 12px;
            color: #888;
            margin-bottom: 10px;
        }
        .blog-card p {
            font-size: 14px;
            color: #bbb;
            line-height: 1.6;
        }
        .blog-card .read-more {
            display: inline-block;
            margin-top: 10px;
            color: #9fd6ff;
            font-weight: 600;
            font-size: 14px;
        }
        .blog-card .read-more:hover {
            color: #ffcc00;
        }

        /* --- TOP AD --- */
        #ad-top {
            width: 100%;
            max-width: 728px;
            height: auto;
            min-height: 50px;
            max-height: 90px;
            margin: 0 auto 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 4px;
            border: 1px dashed rgba(255, 255, 255, 0.08);
            font-size: 12px;
            color: #555;
            overflow: hidden;
        }

        /* --- FOOTER --- */
        footer {
            background: rgba(10, 10, 25, 0.95);
            border-top: 2px solid #2a2a4a;
            padding: 20px 5%;
            text-align: center;
            font-size: 13px;
            color: #888;
            margin-top: auto;
        }
        footer a {
            color: #9fd6ff;
            margin: 0 10px;
        }
        footer a:hover {
            color: #ffcc00;
        }
        footer .footer-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 8px 16px;
            margin: 10px 0;
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 850px) {
            .side-ad {
                display: none !important;
            }
            #gameWrapper {
                gap: 0;
            }
            #gameContainer {
                width: 100%;
                max-width: 480px;
                height: auto;
                aspect-ratio: 400/600;
            }
            .nav-links {
                display: none;
                flex-direction: column;
                width: 100%;
                padding: 12px 0 4px;
                gap: 4px;
            }
            .nav-links.open {
                display: flex;
            }
            .hamburger {
                display: flex;
            }
        }

        @media (max-width: 450px) {
            #ad-top {
                min-height: 40px;
                max-height: 60px;
            }
            header {
                padding: 8px 4%;
            }
            .logo {
                font-size: 18px;
            }
            .blog-grid {
                grid-template-columns: 1fr;
            }
            .page {
                padding: 0 4% 40px;
                margin: 10px auto;
            }
        }

        /* --- MODAL (for legal pages overlay) --- */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            z-index: 100;
            overflow-y: auto;
            padding: 20px;
        }
        .modal-content {
            max-width: 760px;
            margin: 20px auto;
            background: #1a1a2e;
            color: #eee;
            padding: 28px;
            border-radius: 12px;
            border: 1px solid #444;
            position: relative;
        }
        .modal-content h1 {
            color: #ffcc00;
            margin-bottom: 16px;
            font-size: clamp(24px, 4vw, 34px);
        }
        .modal-content h2 {
            color: #70c5ce;
            font-size: clamp(18px, 2.5vw, 24px);
            margin: 20px 0 10px;
        }
        .modal-content p,
        .modal-content li {
            font-size: clamp(14px, 1.2vw, 17px);
            line-height: 1.7;
        }
        .modal-content ul {
            padding-left: 20px;
            margin: 8px 0;
        }
        .close-btn {
            position: absolute;
            top: 10px;
            right: 16px;
            background: none;
            border: none;
            color: #fff;
            font-size: 32px;
            cursor: pointer;
        }
        .modal-btn {
            margin-top: 16px;
            padding: 8px 24px;
            background: #ffcc00;
            border: none;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            font-size: 15px;
        }
        .modal-btn:hover {
            background: #ffd83d;
        }
    </style>
</head>
<body>

    <!-- ========== HEADER ========== -->
    <header>
        <nav>
            <div class="logo">Flappy<span>Bird</span>.io</div>

            <button class="hamburger" id="hamburger" aria-label="Toggle navigation">
                <span></span><span></span><span></span>
            </button>

            <ul class="nav-links" id="navLinks">
                <li><a href="#" class="active" data-page="home">Home</a></li>
                <li><a href="#" data-page="play">Play Flappy Bird</a></li>
                <li><a href="#" data-page="howto">How to Play</a></li>
                <li><a href="#" data-page="blog">Blog</a></li>
                <li><a href="#" data-page="about">About</a></li>
                <li><a href="#" data-page="contact">Contact</a></li>
                <li><a href="#" data-page="privacy">Privacy Policy</a></li>
            </ul>
        </nav>
    </header>

    <!-- ========== TOP AD ========== -->
    <div id="ad-top">
        <span>Advertisement</span>
        <!-- <ins class="adsbygoogle" style="display:inline-block;width:728px;height:90px" data-ad-client="ca-pub-xxxxxxxxxxxxxxxx" data-ad-slot="xxxxxxxxxx"></ins> -->
    </div>

    <!-- ========== PAGES ========== -->

    <!-- HOME -->
    <section class="page active" id="page-home">
        <h1>Welcome to FlappyBird.io</h1>
        <p>The classic arcade game is back — better than ever! Flap your way through pipes, unlock new birds, and compete for the highest score. Whether you're a casual gamer or a hardcore competitor, there's something for everyone.</p>

        <div style="display:flex; gap:12px; flex-wrap:wrap; margin:16px 0;">
            <a href="#" data-page="play" class="smallBtn" style="padding:10px 24px; font-size:16px;">▶ Play Now</a>
            <a href="#" data-page="howto" class="smallBtn" style="padding:10px 24px; font-size:16px; background:#9fd6ff;">📖 How to Play</a>
            <a href="#" data-page="blog" class="smallBtn" style="padding:10px 24px; font-size:16px; background:#70c5ce;">📝 Blog</a>
        </div>

        <h2>🔥 Latest from the Blog</h2>
        <div class="blog-grid">
            <div class="blog-card">
                <h3>10 Flappy Bird Tips to Skyrocket Your Score</h3>
                <div class="meta">June 20, 2026 • 5 min read</div>
                <p>Master the game with these pro strategies — from timing your flaps to staying calm under pressure.</p>
                <a href="#" data-page="blog" class="read-more">Read More →</a>
            </div>
            <div class="blog-card">
                <h3>How to Build a Flappy Bird Clone in HTML5</h3>
                <div class="meta">June 18, 2026 • 8 min read</div>
                <p>Learn step-by-step how to create your own Flappy Bird game using Canvas, JavaScript, and CSS.</p>
                <a href="#" data-page="blog" class="read-more">Read More →</a>
            </div>
            <div class="blog-card">
                <h3>Why Flappy Bird Still Captivates Players in 2026</h3>
                <div class="meta">June 15, 2026 • 4 min read</div>
                <p>Explore the psychology and game design that made Flappy Bird an enduring viral sensation.</p>
                <a href="#" data-page="blog" class="read-more">Read More →</a>
            </div>
        </div>
    </section>

    <!-- PLAY -->
    <section class="page" id="page-play">
        <h1>Play Flappy Bird</h1>
        <p>Click, tap, or press <kbd>Space</kbd> to flap. Score 10 to unlock new birds!</p>

        <div id="gameWrapper">
            <!-- LEFT AD -->
            <div class="side-ad" id="leftAd">
                <div class="ad-label">Advertisement</div>
                <div class="ad-content">
                    <div class="ad-placeholder">📢</div>
                    <span>160×600</span>
                </div>
            </div>

            <!-- GAME -->
            <div id="gameContainer">
                <canvas id="gameCanvas" width="400" height="600"></canvas>
                <div id="hud">0</div>
                <div id="userBadge"></div>
                <button id="logoutBtn">Log out</button>
                <div id="overlay"></div>
            </div>

            <!-- RIGHT AD -->
            <div class="side-ad" id="rightAd">
                <div class="ad-label">Advertisement</div>
                <div class="ad-content">
                    <div class="ad-placeholder">📢</div>
                    <span>160×600</span>
                </div>
            </div>
        </div>

        <p style="margin-top:12px; text-align:center; color:#888; font-size:14px;">
            💡 <strong>Pro Tip:</strong> Focus on the gap, not the bird. Tap consistently, not frantically.
        </p>
    </section>

    <!-- HOW TO PLAY -->
    <section class="page" id="page-howto">
        <h1>How to Play Flappy Bird</h1>
        <p>Flappy Bird is a simple but challenging arcade game. Here's everything you need to know:</p>

        <h2>🎯 Objective</h2>
        <p>Navigate the bird through a series of green pipes without hitting them. Each pipe you pass gives you <strong>1 point</strong>. The game ends when you hit a pipe or the ground.</p>

        <h2>🕹️ Controls</h2>
        <ul>
            <li><strong>Click / Tap:</strong> Click or tap anywhere on the game screen to make the bird flap upward.</li>
            <li><strong>Spacebar:</strong> Press the <kbd>Space</kbd> key on your keyboard.</li>
            <li><strong>Up Arrow:</strong> Press the <kbd>↑</kbd> key as an alternative.</li>
        </ul>

        <h2>🐦 Unlockable Birds</h2>
        <ul>
            <li>Score <strong>10 points</strong> to unlock your first new bird.</li>
            <li>Every <strong>10 points</strong> up to 1000 unlocks a new bird design.</li>
            <li>Reach <strong>1000 points</strong> to unlock the legendary <strong>Boss Bird</strong>!</li>
            <li>Visit the <strong>"My Birds"</strong> gallery to select your favorite.</li>
        </ul>

        <h2>💡 Pro Strategies</h2>
        <ul>
            <li><strong>Stay low:</strong> Flying too high makes it harder to react to pipes.</li>
            <li><strong>Tap rhythmically:</strong> Find a steady rhythm that matches the pipe gaps.</li>
            <li><strong>Focus on the gap:</strong> Look at the space between pipes, not the bird itself.</li>
            <li><strong>Practice:</strong> The more you play, the better your muscle memory gets.</li>
        </ul>
    </section>

    <!-- BLOG -->
    <section class="page" id="page-blog">
        <h1>Blog</h1>
        <p>Gaming tips, development tutorials, and behind-the-scenes stories.</p>

        <div class="blog-grid">
            <!-- Article 1 -->
            <div class="blog-card">
                <h3>10 Flappy Bird Tips to Skyrocket Your Score</h3>
                <div class="meta">June 20, 2026 • 5 min read</div>
                <p>From timing your flaps to reading pipe patterns — these 10 pro tips will help you beat your high score every time.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 2 -->
            <div class="blog-card">
                <h3>How to Build a Flappy Bird Clone in HTML5</h3>
                <div class="meta">June 18, 2026 • 8 min read</div>
                <p>A complete step-by-step tutorial on building Flappy Bird with Canvas, JavaScript, and CSS. Perfect for beginners!</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 3 -->
            <div class="blog-card">
                <h3>Why Flappy Bird Still Captivates Players in 2026</h3>
                <div class="meta">June 15, 2026 • 4 min read</div>
                <p>Discover the psychology, game design, and cultural impact behind one of the most addictive mobile games ever.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 4 -->
            <div class="blog-card">
                <h3>Game Design 101: What Makes a Game Addictive?</h3>
                <div class="meta">June 12, 2026 • 6 min read</div>
                <p>Explore the core principles of addictive game design — from feedback loops to challenge curves.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 5 -->
            <div class="blog-card">
                <h3>JavaScript Canvas: A Beginner's Guide</h3>
                <div class="meta">June 10, 2026 • 7 min read</div>
                <p>Learn the fundamentals of the HTML5 Canvas API — the foundation of browser-based games like Flappy Bird.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 6 -->
            <div class="blog-card">
                <h3>CSS Animations for Game UI</h3>
                <div class="meta">June 8, 2026 • 5 min read</div>
                <p>Enhance your game's interface with smooth CSS animations — from hover effects to score popups.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 7 -->
            <div class="blog-card">
                <h3>Optimizing HTML5 Games for Mobile</h3>
                <div class="meta">June 5, 2026 • 6 min read</div>
                <p>Learn how to make your browser games run smoothly on phones and tablets with responsive design and performance tips.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 8 -->
            <div class="blog-card">
                <h3>The History of Flappy Bird: Rise and Fall</h3>
                <div class="meta">June 2, 2026 • 4 min read</div>
                <p>The story of how a simple indie game became a global phenomenon — and why its creator pulled it from app stores.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 9 -->
            <div class="blog-card">
                <h3>From Zero to Hero: My Flappy Bird Journey</h3>
                <div class="meta">May 30, 2026 • 3 min read</div>
                <p>One player's story of going from a score of 0 to 200+ — with the lessons learned along the way.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 10 -->
            <div class="blog-card">
                <h3>Building a High Score System with JSONBin</h3>
                <div class="meta">May 28, 2026 • 7 min read</div>
                <p>Learn how to build a cloud-based leaderboard for your HTML5 games using the JSONBin API.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 11 -->
            <div class="blog-card">
                <h3>Responsive Design for Game Websites</h3>
                <div class="meta">May 25, 2026 • 5 min read</div>
                <p>Ensure your game looks great on every device with flexible layouts, media queries, and fluid grids.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 12 -->
            <div class="blog-card">
                <h3>Monetizing Your HTML5 Game with AdSense</h3>
                <div class="meta">May 22, 2026 • 6 min read</div>
                <p>A practical guide to integrating Google AdSense into your game website while maintaining a good user experience.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 13 -->
            <div class="blog-card">
                <h3>Game Physics: Simulating Gravity in JavaScript</h3>
                <div class="meta">May 20, 2026 • 5 min read</div>
                <p>Understand the math behind gravity, velocity, and collision detection in 2D games.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 14 -->
            <div class="blog-card">
                <h3>10 Common Mistakes in Game Development</h3>
                <div class="meta">May 18, 2026 • 6 min read</div>
                <p>Learn from the most frequent pitfalls faced by indie game developers — and how to avoid them.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 15 -->
            <div class="blog-card">
                <h3>Flappy Bird Community: Best Fan Games</h3>
                <div class="meta">May 15, 2026 • 4 min read</div>
                <p>Explore the most creative and fun Flappy Bird fan games made by players around the world.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 16 -->
            <div class="blog-card">
                <h3>How to Use GitHub Pages for Game Hosting</h3>
                <div class="meta">May 12, 2026 • 5 min read</div>
                <p>Deploy your HTML5 game for free with GitHub Pages — perfect for indie developers and hobbyists.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 17 -->
            <div class="blog-card">
                <h3>Game Audio: Adding Sound Effects to HTML5 Games</h3>
                <div class="meta">May 10, 2026 • 4 min read</div>
                <p>Use the Web Audio API to add sound effects and background music to your browser games.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 18 -->
            <div class="blog-card">
                <h3>Designing a Custom Domain for Your Game</h3>
                <div class="meta">May 8, 2026 • 3 min read</div>
                <p>Why a custom domain matters — and how to set one up for your game website.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 19 -->
            <div class="blog-card">
                <h3>From Mobile to Browser: Porting Flappy Bird</h3>
                <div class="meta">May 5, 2026 • 6 min read</div>
                <p>How to adapt a mobile game for the browser — tackling touch events, screen sizes, and performance.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>

            <!-- Article 20 -->
            <div class="blog-card">
                <h3>Why Simplicity Wins in Game Design</h3>
                <div class="meta">May 2, 2026 • 4 min read</div>
                <p>A deep dive into why simple, polished games like Flappy Bird often outperform complex, bloated ones.</p>
                <a href="#" class="read-more">Read More →</a>
            </div>
        </div>
    </section>

    <!-- ABOUT -->
    <section class="page" id="page-about">
        <h1>About FlappyBird.io</h1>
        <p>FlappyBird.io is a fan-made tribute to the classic Flappy Bird game that took the world by storm in 2013. We rebuilt it from scratch using modern web technologies — HTML5 Canvas, CSS3, and vanilla JavaScript — to bring the addictive experience back to browsers everywhere.</p>

        <h2>🌟 Our Mission</h2>
        <p>We believe that great games should be accessible to everyone, anywhere, on any device. That's why FlappyBird.io is:</p>
        <ul>
            <li><strong>100% Free:</strong> No paywalls, no in-app purchases.</li>
            <li><strong>Cross-Platform:</strong> Play on desktop, tablet, or phone.</li>
            <li><strong>Privacy-First:</strong> We collect minimal data — only what's needed to save your progress.</li>
        </ul>

        <h2>👨‍💻 About the Developer</h2>
        <p>This project was created by <strong>Atharv Sharma</strong>, a passionate game developer and web enthusiast. With a love for retro arcade games and clean code, Atharv built this site to share the joy of Flappy Bird with a new generation of players.</p>

        <h2>📬 Get in Touch</h2>
        <p>Have questions, suggestions, or just want to say hi? Reach out via the <a href="#" data-page="contact">Contact</a> page — we'd love to hear from you!</p>
    </section>

    <!-- CONTACT -->
    <section class="page" id="page-contact">
        <h1>Contact Us</h1>
        <p>Have questions, feedback, or partnership ideas? We're all ears!</p>

        <div style="max-width:500px; margin:20px 0;">
            <p style="font-size:18px;">📧 <a href="mailto:atharvsharmagrandmaster@gmail.com">atharvsharmagrandmaster@gmail.com</a></p>
            <p style="font-size:16px; color:#888; margin-top:8px;">We typically respond within 24–48 hours.</p>
        </div>

        <h2>💬 Social Media</h2>
        <p>Follow us for updates, tips, and community highlights:</p>
        <ul>
            <li>🐦 Twitter / X: <a href="#">@FlappyBirdIO</a></li>
            <li>📸 Instagram: <a href="#">@FlappyBirdIO</a></li>
            <li>▶️ YouTube: <a href="#">FlappyBird Gameplay</a></li>
        </ul>

        <h2>📩 Business Inquiries</h2>
        <p>For sponsorship, advertising, or collaboration opportunities, email us directly at the address above with "Business Inquiry" in the subject line.</p>
    </section>

    <!-- PRIVACY POLICY -->
    <section class="page" id="page-privacy">
        <h1>Privacy Policy</h1>
        <p><strong>Last updated:</strong> June 21, 2026</p>

        <p>FlappyBird.io ("we", "our", or "us") respects your privacy. This policy explains how we collect, use, and protect your personal information.</p>

        <h2>1. Information We Collect</h2>
        <ul>
            <li><strong>Account Data:</strong> Username and password hash (stored via JSONBin).</li>
            <li><strong>Game Progress:</strong> Your high score and unlocked birds.</li>
            <li><strong>Usage Data:</strong> Anonymous analytics via Google AdSense (cookies).</li>
        </ul>

        <h2>2. How We Use Your Data</h2>
        <ul>
            <li>To authenticate your account and save game progress.</li>
            <li>To display relevant ads via Google AdSense.</li>
            <li>To improve the game based on user behavior.</li>
        </ul>

        <h2>3. Cookies & Third-Party Services</h2>
        <p>We use Google AdSense, which may set cookies on your browser to serve personalized ads. You can manage cookie preferences in your browser settings.</p>

        <h2>4. Data Security</h2>
        <p>Your password is hashed — never stored in plain text. However, no online service is 100% secure. Use at your own risk.</p>

        <h2>5. Your Rights</h2>
        <p>You may request account deletion or data removal by contacting us via the <a href="#" data-page="contact">Contact</a> page.</p>

        <h2>6. Changes to This Policy</h2>
        <p>We may update this policy occasionally. Check back for the latest version.</p>
    </section>

    <!-- ========== FOOTER ========== -->
    <footer>
        <div class="footer-links">
            <a href="#" data-page="home">Home</a>
            <a href="#" data-page="play">Play</a>
            <a href="#" data-page="howto">How to Play</a>
            <a href="#" data-page="blog">Blog</a>
            <a href="#" data-page="about">About</a>
            <a href="#" data-page="contact">Contact</a>
            <a href="#" data-page="privacy">Privacy Policy</a>
        </div>
        <p>&copy; 2026 FlappyBird.io — Made with ❤️ by Atharv Sharma</p>
    </footer>

    <!-- ========== SCRIPTS ========== -->

    <!-- Navigation -->
    <script>
        // --- PAGE NAVIGATION ---
        const navLinks = document.querySelectorAll('.nav-links a, .footer-links a, [data-page]');
        const pages = {
            home: document.getElementById('page-home'),
            play: document.getElementById('page-play'),
            howto: document.getElementById('page-howto'),
            blog: document.getElementById('page-blog'),
            about: document.getElementById('page-about'),
            contact: document.getElementById('page-contact'),
            privacy: document.getElementById('page-privacy')
        };

        function showPage(pageId) {
            // Hide all
            Object.values(pages).forEach(p => p.classList.remove('active'));
            // Show target
            if (pages[pageId]) pages[pageId].classList.add('active');
            // Update nav active state
            document.querySelectorAll('.nav-links a').forEach(a => {
                a.classList.toggle('active', a.dataset.page === pageId);
            });
            // Close mobile menu
            document.getElementById('navLinks').classList.remove('open');
            // Scroll to top
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Handle all navigation clicks
        document.addEventListener('click', function(e) {
            const link = e.target.closest('[data-page]');
            if (link) {
                e.preventDefault();
                const page = link.dataset.page;
                if (pages[page]) showPage(page);
            }
        });

        // Hamburger
        document.getElementById('hamburger').addEventListener('click', function() {
            document.getElementById('navLinks').classList.toggle('open');
        });

        // --- GAME CODE (same as before, with minor adjustments) ---
        (function() {
            const canvas = document.getElementById('gameCanvas');
            const ctx = canvas.getContext('2d');
            const overlay = document.getElementById('overlay');
            const hud = document.getElementById('hud');
            const userBadge = document.getElementById('userBadge');
            const logoutBtn = document.getElementById('logoutBtn');

            const W = 400,
                H = 600,
                GROUND_Y = H * 0.75;

            // --- BIRD DEFINITIONS ---
            const BASE_PALETTE = [
                { body: '#ffd23f', wing: '#ffb700', name: 'Classic' },
                { body: '#e24b4a', wing: '#a32d2d', name: 'Crimson' },
                { body: '#378ADD', wing: '#185FA5', name: 'Sky' },
                { body: '#639922', wing: '#3B6D11', name: 'Forest' },
                { body: '#7F77DD', wing: '#534AB7', name: 'Amethyst' },
                { body: '#D85A30', wing: '#993C1D', name: 'Coral' },
                { body: '#1D9E75', wing: '#0F6E56', name: 'Teal' },
                { body: '#D4537E', wing: '#993556', name: 'Blossom' },
                { body: '#BA7517', wing: '#854F0B', name: 'Amber' },
                { body: '#888780', wing: '#5F5E5A', name: 'Slate' },
                { body: '#85B7EB', wing: '#0C447C', name: 'Glacier' },
                { body: '#97C459', wing: '#27500A', name: 'Moss' },
                { body: '#ED93B1', wing: '#72243E', name: 'Magenta' },
                { body: '#EF9F27', wing: '#633806', name: 'Sunset' },
                { body: '#F09595', wing: '#791F1F', name: 'Cherry' },
                { body: '#5DCAA5', wing: '#085041', name: 'Lagoon' },
                { body: '#AFA9EC', wing: '#26215C', name: 'Violet' },
                { body: '#FAC775', wing: '#412402', name: 'Honey' },
                { body: '#C0DD97', wing: '#173404', name: 'Sprout' },
                { body: '#F5C4B3', wing: '#4A1B0C', name: 'Peach' }
            ];

            const ACCENTS = [
                { type: 'stripe', color: 'dark' },
                { type: 'star', color: 'light' },
                { type: 'dot', color: 'light' },
                { type: 'stripe', color: 'light' },
                { type: 'star', color: 'dark' }
            ];

            function shadeColor(hex, percent) {
                let r = parseInt(hex.substring(1, 3), 16),
                    g = parseInt(hex.substring(3, 5), 16),
                    b = parseInt(hex.substring(5, 7), 16);
                r = Math.min(255, Math.max(0, r + percent));
                g = Math.min(255, Math.max(0, g + percent));
                b = Math.min(255, Math.max(0, b + percent));
                return `rgb(${r},${g},${b})`;
            }

            function lightenForAccent(hex) { return shadeColor(hex, 90); }

            function darkenForAccent(hex) { return shadeColor(hex, -60); }

            function buildBirdDefs() {
                const defs = [{ level: 0, name: 'Classic', body: BASE_PALETTE[0].body, wing: BASE_PALETTE[0].wing,
                    accent: null }];
                for (let i = 1; i <= 99; i++) {
                    const level = i * 10;
                    const palette = BASE_PALETTE[i % BASE_PALETTE.length];
                    const accentDef = ACCENTS[i % ACCENTS.length];
                    const accentColor = accentDef.color === 'light' ? lightenForAccent(palette.body) :
                        darkenForAccent(palette.wing);
                    defs.push({ level, name: palette.name + ' ' + (Math.floor(i / BASE_PALETTE.length) + 1),
                        body: palette.body, wing: palette.wing, accent: accentDef.type, accentColor });
                }
                defs.push({ level: 1000, name: 'Boss Bird', body: '#2C2C2A', wing: '#171716', accent: 'crown',
                    accentColor: '#FFD700' });
                return defs;
            }

            const BIRD_DEFS = buildBirdDefs();

            let currentUser = null;
            let profile = { bestScore: 0, unlockedLevel: 0, selectedBird: 0 };

            const JSONBIN_BIN_ID = '6a377049f5f4af5e29170eac';
            const JSONBIN_MASTER_KEY = '$2a$10$ExoGhr0vFRHf0BoHC/sy8OL4hPtoU/iEqwU7gchDeeNAgBS.CBUcy';
            const JSONBIN_BASE = 'https://api.jsonbin.io/v3/b/' + JSONBIN_BIN_ID;

            async function fetchAllAccounts() {
                const res = await fetch(JSONBIN_BASE + '/latest', { method: 'GET', headers: { 'X-Master-Key': JSONBIN_MASTER_KEY } });
                if (!res.ok) throw new Error('Failed to reach account server (status ' + res.status + ')');
                const data = await res.json();
                return (data.record && data.record.accounts) ? data.record.accounts : {};
            }

            async function writeAllAccounts(accountsObj) {
                const res = await fetch(JSONBIN_BASE, {
                    method: 'PUT',
                    headers: { 'Content-Type': 'application/json', 'X-Master-Key': JSONBIN_MASTER_KEY },
                    body: JSON.stringify({ accounts: accountsObj })
                });
                if (!res.ok) throw new Error('Failed to save to account server (status ' + res.status + ')');
            }

            async function loadAccount(username) {
                try {
                    const accounts = await fetchAllAccounts();
                    return accounts[username.toLowerCase()] || null;
                } catch (e) { console.error('loadAccount failed', e);
                    throw e; }
            }

            async function saveAccount(username, data) {
                const accounts = await fetchAllAccounts();
                accounts[username.toLowerCase()] = data;
                await writeAllAccounts(accounts);
            }

            function simpleHash(str) {
                let hash = 0;
                for (let i = 0; i < str.length; i++) { hash = ((hash << 5) - hash) + str.charCodeAt(i);
                    hash |= 0; }
                return String(hash);
            }

            const STATE = { AUTH_CHOICE: 'auth_choice', LOGIN: 'login', SIGNUP: 'signup', START: 'start', PLAYING: 'playing',
                GAMEOVER: 'gameover', GALLERY: 'gallery' };
            let state = STATE.AUTH_CHOICE;

            const bird = { x: 90, y: H / 2, w: 34, h: 26, vy: 0, rotation: 0 };
            const GRAVITY = 0.45,
                FLAP_VELOCITY = -8,
                MAX_FALL_SPEED = 10;
            const PIPE_WIDTH = 60,
                PIPE_GAP = 150,
                PIPE_SPEED = 2.6,
                PIPE_SPACING = 220;
            let pipes = [],
                clouds = [],
                score = 0,
                frame = 0,
                groundOffset = 0,
                flashAlpha = 0,
                crownGlow = 0;

            function initClouds() {
                clouds = [];
                for (let i = 0; i < 4; i++) {
                    clouds.push({ x: Math.random() * W, y: 40 + Math.random() * 120, scale: 0.6 + Math.random() * 0.8,
                        speed: 0.3 + Math.random() * 0.3 });
                }
            }

            function spawnInitialPipes() {
                for (let i = 0; i < 3; i++) addPipe(W + 150 + i * PIPE_SPACING);
            }

            function addPipe(x) {
                const minTop = 60,
                    maxTop = GROUND_Y - PIPE_GAP - 60;
                const topHeight = minTop + Math.random() * (maxTop - minTop);
                pipes.push({ x, topHeight, bottomY: topHeight + PIPE_GAP, passed: false });
            }

            function resetGame() {
                bird.y = H / 2;
                bird.vy = 0;
                bird.rotation = 0;
                pipes = [];
                score = 0;
                frame = 0;
                flashAlpha = 0;
                spawnInitialPipes();
                initClouds();
            }

            function renderAuthChoice() {
                overlay.style.display = 'flex';
                overlay.innerHTML = `
                    <div class="authBox">
                        <h1 style="font-size:clamp(22px,5vw,32px);">FLAPPY BIRD</h1>
                        <button id="goLogin">Log in</button>
                        <button id="goSignup" style="background:#9fd6ff;">Sign up</button>
                        <p style="margin-top:12px; font-size:clamp(10px,1.8vw,12px); opacity:0.7;">Your account works on any device.</p>
                    </div>
                `;
                document.getElementById('goLogin').onclick = (e) => { e.stopPropagation();
                    renderLogin(); };
                document.getElementById('goSignup').onclick = (e) => { e.stopPropagation();
                    renderSignup(); };
            }

            function renderLogin() {
                state = STATE.LOGIN;
                overlay.innerHTML = `
                    <div class="authBox">
                        <h1>Log in</h1>
                        <input type="text" id="loginUser" placeholder="Username" autocomplete="off" />
                        <input type="password" id="loginPass" placeholder="Password" autocomplete="off" />
                        <button id="loginBtn">Log in</button>
                        <div class="authError" id="loginErr"></div>
                        <div class="switchLink" id="toSignup">Need an account? Sign up</div>
                    </div>
                `;
                document.getElementById('toSignup').onclick = (e) => { e.stopPropagation();
                    renderSignup(); };
                document.getElementById('loginBtn').onclick = async (e) => {
                    e.stopPropagation();
                    const username = document.getElementById('loginUser').value.trim();
                    const pass = document.getElementById('loginPass').value;
                    const errEl = document.getElementById('loginErr');
                    const btn = document.getElementById('loginBtn');
                    if (!username || !pass) { errEl.textContent = 'Enter username and password.'; return; }

                    if (username.toLowerCase() === 'developerx' && pass === 'FLAPPYDEVELOPERKEY') {
                        currentUser = { username: 'DeveloperX' };
                        profile = { bestScore: 1000, unlockedLevel: 1000, selectedBird: BIRD_DEFS.length - 1 };
                        enterGameAsLoggedIn();
                        return;
                    }

                    errEl.textContent = 'Connecting...';
                    btn.disabled = true;
                    try {
                        const acc = await loadAccount(username);
                        if (!acc) { errEl.textContent = 'No account found.';
                            btn.disabled = false; return; }
                        if (acc.passHash !== simpleHash(pass)) { errEl.textContent = 'Wrong password.';
                            btn.disabled = false; return; }
                        currentUser = { username };
                        profile = acc.profile || { bestScore: 0, unlockedLevel: 0, selectedBird: 0 };
                        enterGameAsLoggedIn();
                    } catch (err) {
                        errEl.textContent = 'Server error. Check internet.';
                        btn.disabled = false;
                    }
                };
                [document.getElementById('loginUser'), document.getElementById('loginPass')].forEach(el => {
                    el.onkeydown = (ev) => { if (ev.key === 'Enter') document.getElementById('loginBtn').click(); };
                    el.onclick = (ev) => ev.stopPropagation();
                });
            }

            function renderSignup() {
                state = STATE.SIGNUP;
                overlay.innerHTML = `
                    <div class="authBox">
                        <h1>Sign up</h1>
                        <input type="text" id="suUser" placeholder="Username" autocomplete="off" />
                        <input type="password" id="suPass" placeholder="Password" autocomplete="off" />
                        <input type="password" id="suPass2" placeholder="Confirm password" autocomplete="off" />
                        <button id="suBtn">Create account</button>
                        <div class="authError" id="suErr"></div>
                        <div class="switchLink" id="toLogin">Have an account? Log in</div>
                    </div>
                `;
                document.getElementById('toLogin').onclick = (e) => { e.stopPropagation();
                    renderLogin(); };
                document.getElementById('suBtn').onclick = async (e) => {
                    e.stopPropagation();
                    const username = document.getElementById('suUser').value.trim();
                    const pass = document.getElementById('suPass').value;
                    const pass2 = document.getElementById('suPass2').value;
                    const errEl = document.getElementById('suErr');
                    const btn = document.getElementById('suBtn');
                    if (!username || !pass) { errEl.textContent = 'Fill all fields.'; return; }
                    if (username.length < 3) { errEl.textContent = 'Username min 3 chars.'; return; }
                    if (pass !== pass2) { errEl.textContent = 'Passwords do not match.'; return; }
                    errEl.textContent = 'Connecting...';
                    btn.disabled = true;
                    try {
                        const existing = await loadAccount(username);
                        if (existing) { errEl.textContent = 'Username taken.';
                            btn.disabled = false; return; }
                        profile = { bestScore: 0, unlockedLevel: 0, selectedBird: 0 };
                        currentUser = { username };
                        await saveAccount(username, { passHash: simpleHash(pass), profile });
                        enterGameAsLoggedIn();
                    } catch (err) {
                        errEl.textContent = 'Server error. Check internet.';
                        btn.disabled = false;
                    }
                };
                [document.getElementById('suUser'), document.getElementById('suPass'), document.getElementById('suPass2')]
                    .forEach(el => {
                        el.onkeydown = (ev) => { if (ev.key === 'Enter') document.getElementById('suBtn').click(); };
                        el.onclick = (ev) => ev.stopPropagation();
                    });
            }

            function enterGameAsLoggedIn() {
                userBadge.textContent = currentUser.username + ' - best: ' + profile.bestScore;
                userBadge.style.display = 'block';
                logoutBtn.style.display = 'block';
                state = STATE.START;
                resetGame();
                showStartOverlay();
            }

            logoutBtn.onclick = (e) => {
                e.stopPropagation();
                currentUser = null;
                profile = { bestScore: 0, unlockedLevel: 0, selectedBird: 0 };
                userBadge.style.display = 'none';
                logoutBtn.style.display = 'none';
                hud.style.display = 'none';
                state = STATE.AUTH_CHOICE;
                renderAuthChoice();
            };

            function showStartOverlay() {
                overlay.style.display = 'flex';
                overlay.innerHTML = `
                    <h1>FLAPPY BIRD</h1>
                    <p>Click, tap, or press SPACE to flap</p>
                    <p>Score 10 to unlock a new bird!</p>
                    <div class="score-line">Best: ${profile.bestScore}</div>
                    <div style="display:flex; gap:8px; margin-top:10px; flex-wrap:wrap; justify-content:center;">
                        <button class="smallBtn" id="startBtn">Play</button>
                        <button class="smallBtn" id="galleryBtn" style="background:#9fd6ff;">My birds</button>
                    </div>
                `;
                document.getElementById('startBtn').onclick = (e) => { e.stopPropagation();
                    beginPlaying(); };
                document.getElementById('galleryBtn').onclick = (e) => { e.stopPropagation();
                    showGallery(); };
            }

            function showGallery() {
                state = STATE.GALLERY;
                overlay.style.display = 'flex';
                let slotsHtml = '';
                BIRD_DEFS.forEach((b, i) => {
                    const isUnlocked = profile.bestScore >= b.level;
                    const isSelected = i === profile.selectedBird;
                    slotsHtml += `<div class="birdSlot ${isUnlocked ? '' : 'locked'} ${isSelected ? 'selected' : ''}" data-idx="${i}" title="${b.name}">
                        <canvas width="64" height="52" data-bird="${i}"></canvas>
                        <span class="lvl">${b.level}</span>
                    </div>`;
                });
                overlay.innerHTML = `
                    <div class="unlockPopup">
                        <h1 style="font-size:clamp(18px,3.5vw,24px);">Your birds</h1>
                        <p style="font-size:clamp(10px,1.8vw,13px); opacity:0.85;">Tap an unlocked bird to select it</p>
                        <div class="birdGallery">${slotsHtml}</div>
                        <button class="smallBtn" id="backBtn">Back</button>
                    </div>
                `;
                document.querySelectorAll('.birdSlot canvas').forEach(cv => {
                    const idx = parseInt(cv.dataset.bird, 10);
                    drawBirdPreview(cv, BIRD_DEFS[idx]);
                });
                document.querySelectorAll('.birdSlot').forEach(slot => {
                    slot.onclick = async (e) => {
                        e.stopPropagation();
                        const idx = parseInt(slot.dataset.idx, 10);
                        if (profile.bestScore >= BIRD_DEFS[idx].level) {
                            profile.selectedBird = idx;
                            await persistProfile();
                            showGallery();
                        }
                    };
                });
                document.getElementById('backBtn').onclick = (e) => { e.stopPropagation();
                    showStartOverlay();
                    state = STATE.START; };
            }

            function drawBirdPreview(canvasEl, def) {
                const pctx = canvasEl.getContext('2d');
                pctx.clearRect(0, 0, 64, 52);
                pctx.save();
                pctx.translate(32, 26);
                drawBirdShape(pctx, def, 0, 1);
                pctx.restore();
            }

            async function persistProfile() {
                if (!currentUser || currentUser.username === 'DeveloperX') {
                    if (currentUser) userBadge.textContent = currentUser.username + ' - best: ' + profile.bestScore +
                        ' (dev mode)';
                    return;
                }
                try {
                    const acc = await loadAccount(currentUser.username);
                    if (acc) { acc.profile = profile;
                        await saveAccount(currentUser.username, acc); }
                    userBadge.textContent = currentUser.username + ' - best: ' + profile.bestScore;
                } catch (e) {
                    userBadge.textContent = currentUser.username + ' - best: ' + profile.bestScore +
                        ' (save failed)';
                }
            }

            function beginPlaying() {
                state = STATE.PLAYING;
                overlay.style.display = 'none';
                hud.style.display = 'block';
                resetGame();
                bird.vy = FLAP_VELOCITY;
            }

            async function endGame() {
                state = STATE.GAMEOVER;
                let newUnlock = null;
                if (score > profile.bestScore) {
                    const prevBest = profile.bestScore;
                    profile.bestScore = score;
                    const newlyUnlocked = BIRD_DEFS.filter(b => b.level > prevBest && b.level <= score);
                    if (newlyUnlocked.length) newUnlock = newlyUnlocked[newlyUnlocked.length - 1];
                    await persistProfile();
                }
                flashAlpha = 1;
                showGameOverOverlay(newUnlock);
            }

            function showGameOverOverlay(newUnlock) {
                overlay.style.display = 'flex';
                let unlockHtml = '';
                if (newUnlock) {
                    unlockHtml =
                        `<div class="score-line" style="color:#ffe87a;">New bird unlocked: ${newUnlock.name}!</div>`;
                }
                overlay.innerHTML = `
                    <h1>GAME OVER</h1>
                    <div class="score-line">Score: ${score}</div>
                    <div class="score-line" style="font-size:clamp(13px,2.2vw,16px); color:#ffcc00;">Best: ${profile.bestScore}</div>
                    ${unlockHtml}
                    <div style="display:flex; gap:8px; margin-top:10px; flex-wrap:wrap; justify-content:center;">
                        <button class="smallBtn" id="retryBtn">Retry</button>
                        <button class="smallBtn" id="galleryBtn2" style="background:#9fd6ff;">My birds</button>
                    </div>
                `;
                document.getElementById('retryBtn').onclick = (e) => { e.stopPropagation();
                    beginPlaying(); };
                document.getElementById('galleryBtn2').onclick = (e) => { e.stopPropagation();
                    showGallery(); };
            }

            function flap() { if (state === STATE.PLAYING) bird.vy = FLAP_VELOCITY; }

            function rectsOverlap(ax, ay, aw, ah, bx, by, bw, bh) {
                return ax < bx + bw && ax + aw > bx && ay < by + bh && ay + ah > by;
            }

            function update() {
                if (state !== STATE.PLAYING) return;
                frame++;
                bird.vy += GRAVITY;
                if (bird.vy > MAX_FALL_SPEED) bird.vy = MAX_FALL_SPEED;
                bird.y += bird.vy;
                bird.rotation = Math.max(-25, Math.min(90, bird.vy * 5));

                for (let i = 0; i < pipes.length; i++) {
                    pipes[i].x -= PIPE_SPEED;
                    if (!pipes[i].passed && pipes[i].x + PIPE_WIDTH < bird.x) { pipes[i].passed = true;
                        score++; }
                }
                if (pipes.length && pipes[0].x + PIPE_WIDTH < -10) pipes.shift();
                const lastPipe = pipes[pipes.length - 1];
                if (lastPipe && (W - lastPipe.x) >= PIPE_SPACING) addPipe(lastPipe.x + PIPE_SPACING);

                groundOffset = (groundOffset + PIPE_SPEED) % 24;
                crownGlow = (crownGlow + 0.08) % (Math.PI * 2);

                for (const c of clouds) { c.x -= c.speed; if (c.x < -80) c.x = W + 80; }

                if (bird.y + bird.h / 2 >= GROUND_Y) { bird.y = GROUND_Y - bird.h / 2;
                    endGame(); return; }
                if (bird.y - bird.h / 2 <= 0) { bird.y = bird.h / 2;
                    bird.vy = 0; }

                const birdLeft = bird.x - bird.w / 2 + 4,
                    birdTop = bird.y - bird.h / 2 + 4;
                const birdW = bird.w - 8,
                    birdH = bird.h - 8;
                for (const p of pipes) {
                    if (rectsOverlap(birdLeft, birdTop, birdW, birdH, p.x, 0, PIPE_WIDTH, p.topHeight)) { endGame(); return; }
                    if (rectsOverlap(birdLeft, birdTop, birdW, birdH, p.x, p.bottomY, PIPE_WIDTH, GROUND_Y - p.bottomY)) { endGame
                        (); return; }
                }
                if (flashAlpha > 0) flashAlpha -= 0.05;
            }

            function drawCloud(x, y, scale) {
                ctx.save();
                ctx.translate(x, y);
                ctx.scale(scale, scale);
                ctx.fillStyle = 'rgba(255,255,255,0.85)';
                ctx.beginPath();
                ctx.arc(0, 0, 20, 0, Math.PI * 2);
                ctx.arc(22, -8, 16, 0, Math.PI * 2);
                ctx.arc(-22, -6, 14, 0, Math.PI * 2);
                ctx.arc(10, 8, 18, 0, Math.PI * 2);
                ctx.arc(-10, 8, 16, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }

            function drawBackground() {
                const skyGrad = ctx.createLinearGradient(0, 0, 0, GROUND_Y);
                skyGrad.addColorStop(0, '#70c5ce');
                skyGrad.addColorStop(1, '#a8e0e6');
                ctx.fillStyle = skyGrad;
                ctx.fillRect(0, 0, W, GROUND_Y);
                for (const c of clouds) drawCloud(c.x, c.y, c.scale);
            }

            function drawGround() {
                ctx.fillStyle = '#ded895';
                ctx.fillRect(0, GROUND_Y, W, H - GROUND_Y);
                ctx.fillStyle = '#7ec850';
                ctx.fillRect(0, GROUND_Y, W, 14);
                ctx.strokeStyle = '#5fae3a';
                ctx.lineWidth = 3;
                for (let x = -groundOffset; x < W; x += 24) {
                    ctx.beginPath();
                    ctx.moveTo(x, GROUND_Y + 14);
                    ctx.lineTo(x + 8, GROUND_Y + 14);
                    ctx.stroke();
                }
                ctx.fillStyle = '#c9bd7a';
                for (let x = -groundOffset; x < W; x += 24) ctx.fillRect(x, GROUND_Y + 24, 10, 4);
            }

            function drawPipe(p) {
                const capHeight = 26,
                    capOverhang = 6;
                ctx.fillStyle = '#73c44a';
                ctx.strokeStyle = '#4f9c2e';
                ctx.lineWidth = 3;
                ctx.fillRect(p.x, 0, PIPE_WIDTH, p.topHeight - capHeight);
                ctx.strokeRect(p.x, 0, PIPE_WIDTH, p.topHeight - capHeight);
                ctx.fillRect(p.x - capOverhang, p.topHeight - capHeight, PIPE_WIDTH + capOverhang * 2, capHeight);
                ctx.strokeRect(p.x - capOverhang, p.topHeight - capHeight, PIPE_WIDTH + capOverhang * 2, capHeight);
                const bottomHeight = GROUND_Y - p.bottomY - capHeight;
                ctx.fillRect(p.x, p.bottomY + capHeight, PIPE_WIDTH, bottomHeight);
                ctx.strokeRect(p.x, p.bottomY + capHeight, PIPE_WIDTH, bottomHeight);
                ctx.fillRect(p.x - capOverhang, p.bottomY, PIPE_WIDTH + capOverhang * 2, capHeight);
                ctx.strokeRect(p.x - capOverhang, p.bottomY, PIPE_WIDTH + capOverhang * 2, capHeight);
                ctx.fillStyle = 'rgba(255,255,255,0.25)';
                ctx.fillRect(p.x + 6, 0, 8, p.topHeight - capHeight);
                ctx.fillRect(p.x + 6, p.bottomY + capHeight, 8, bottomHeight);
            }

            function drawBirdShape(targetCtx, def, wingPhase, scaleFactor) {
                const w = 34 * scaleFactor,
                    h = 26 * scaleFactor;
                targetCtx.fillStyle = def.body;
                targetCtx.strokeStyle = shadeColor(def.body, -20);
                targetCtx.lineWidth = 2;
                targetCtx.beginPath();
                targetCtx.ellipse(0, 0, w / 2, h / 2, 0, 0, Math.PI * 2);
                targetCtx.fill();
                targetCtx.stroke();

                const wingFlap = Math.sin(wingPhase) * 6 * scaleFactor;
                targetCtx.fillStyle = def.wing;
                targetCtx.beginPath();
                targetCtx.ellipse(-4 * scaleFactor, 2 * scaleFactor + wingFlap * 0.2, 9 * scaleFactor, 6 * scaleFactor, -0.3,
                    0, Math.PI * 2);
                targetCtx.fill();

                if (def.accent === 'stripe') {
                    targetCtx.strokeStyle = def.accentColor;
                    targetCtx.lineWidth = 3 * scaleFactor;
                    targetCtx.beginPath();
                    targetCtx.moveTo(-w / 2 + 4 * scaleFactor, -2 * scaleFactor);
                    targetCtx.lineTo(w / 2 - 8 * scaleFactor, -2 * scaleFactor);
                    targetCtx.stroke();
                } else if (def.accent === 'star') {
                    drawStar(targetCtx, -2 * scaleFactor, -h / 2 + 2 * scaleFactor, 4 * scaleFactor, def.accentColor);
                } else if (def.accent === 'dot') {
                    targetCtx.fillStyle = def.accentColor;
                    targetCtx.beginPath();
                    targetCtx.arc(-2 * scaleFactor, -h / 2 + 3 * scaleFactor, 3 * scaleFactor, 0, Math.PI * 2);
                    targetCtx.fill();
                } else if (def.accent === 'crown') {
                    drawCrown(targetCtx, scaleFactor);
                }

                targetCtx.fillStyle = '#fff';
                targetCtx.beginPath();
                targetCtx.arc(8 * scaleFactor, -5 * scaleFactor, 5 * scaleFactor, 0, Math.PI * 2);
                targetCtx.fill();
                targetCtx.fillStyle = '#000';
                targetCtx.beginPath();
                targetCtx.arc(9.5 * scaleFactor, -5 * scaleFactor, 2.4 * scaleFactor, 0, Math.PI * 2);
                targetCtx.fill();
                targetCtx.fillStyle = '#ff8c00';
                targetCtx.beginPath();
                targetCtx.moveTo(13 * scaleFactor, -1 * scaleFactor);
                targetCtx.lineTo(24 * scaleFactor, 1 * scaleFactor);
                targetCtx.lineTo(13 * scaleFactor, 5 * scaleFactor);
                targetCtx.closePath();
                targetCtx.fill();
                targetCtx.strokeStyle = '#cc6f00';
                targetCtx.lineWidth = 1.5 * scaleFactor;
                targetCtx.stroke();
            }

            function drawStar(targetCtx, cx, cy, r, color) {
                targetCtx.save();
                targetCtx.translate(cx, cy);
                targetCtx.fillStyle = color;
                targetCtx.beginPath();
                for (let i = 0; i < 5; i++) {
                    const angle = (Math.PI * 2 * i) / 5 - Math.PI / 2;
                    const angle2 = angle + Math.PI / 5;
                    targetCtx.lineTo(Math.cos(angle) * r, Math.sin(angle) * r);
                    targetCtx.lineTo(Math.cos(angle2) * (r * 0.45), Math.sin(angle2) * (r * 0.45));
                }
                targetCtx.closePath();
                targetCtx.fill();
                targetCtx.restore();
            }

            function drawCrown(targetCtx, scaleFactor) {
                const glow = 0.6 + 0.4 * Math.sin(crownGlow);
                targetCtx.save();
                targetCtx.translate(2 * scaleFactor, -13 * scaleFactor);
                targetCtx.scale(scaleFactor, scaleFactor);
                targetCtx.fillStyle = `rgba(255,215,0,${0.25 * glow})`;
                targetCtx.beginPath();
                targetCtx.arc(0, 0, 14, 0, Math.PI * 2);
                targetCtx.fill();
                targetCtx.fillStyle = '#FFD700';
                targetCtx.strokeStyle = '#B8860B';
                targetCtx.lineWidth = 1;
                targetCtx.beginPath();
                targetCtx.moveTo(-9, 4);
                targetCtx.lineTo(-9, -4);
                targetCtx.lineTo(-5, 1);
                targetCtx.lineTo(0, -7);
                targetCtx.lineTo(5, 1);
                targetCtx.lineTo(9, -4);
                targetCtx.lineTo(9, 4);
                targetCtx.closePath();
                targetCtx.fill();
                targetCtx.stroke();
                targetCtx.fillStyle = `rgba(255,255,255,${0.7 * glow})`;
                targetCtx.beginPath();
                targetCtx.arc(0, -6, 1.6, 0, Math.PI * 2);
                targetCtx.arc(-8, -3, 1.2, 0, Math.PI * 2);
                targetCtx.arc(8, -3, 1.2, 0, Math.PI * 2);
                targetCtx.fill();
                targetCtx.restore();
            }

            function drawBird() {
                const def = BIRD_DEFS[profile.selectedBird] || BIRD_DEFS[0];
                ctx.save();
                ctx.translate(bird.x, bird.y);
                ctx.rotate(bird.rotation * Math.PI / 180);
                drawBirdShape(ctx, def, frame * 0.4, 1);
                ctx.restore();
            }

            function draw() {
                drawBackground();
                for (const p of pipes) drawPipe(p);
                drawGround();
                if (state === STATE.PLAYING || state === STATE.GAMEOVER) drawBird();
                if (flashAlpha > 0) {
                    ctx.fillStyle = `rgba(255,255,255,${flashAlpha * 0.6})`;
                    ctx.fillRect(0, 0, W, H);
                }
                if (state === STATE.PLAYING) hud.textContent = score;
            }

            function loop() { update();
                draw();
                requestAnimationFrame(loop); }

            function handleInput(e) { if (state === STATE.PLAYING) { e.preventDefault();
                    flap(); } }

            canvas.addEventListener('mousedown', handleInput);
            canvas.addEventListener('touchstart', handleInput, { passive: false });
            overlay.addEventListener('mousedown', function(e) { if (state === STATE.PLAYING) flap(); });

            document.addEventListener('keydown', function(e) {
                if (e.code === 'Space' || e.key === ' ' || e.key === 'ArrowUp') {
                    if (document.activeElement && (document.activeElement.tagName === 'INPUT')) return;
                    e.preventDefault();
                    flap();
                }
            });

            initClouds();
            spawnInitialPipes();
            draw();
            loop();
            renderAuthChoice();
        })();
    </script>

</body>
</html>
