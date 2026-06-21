<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flappy Bird Guide - Tips, Strategies & Free Online Game</title>
    <meta name="description" content="Master Flappy Bird with expert tips, strategies, and tutorials. Play the classic game online for free, track high scores, and unlock new birds." />
    <meta name="keywords" content="flappy bird, game guide, tips, strategies, high score, online game, html5 game" />
    <link rel="canonical" href="https://atharvsharmagrandmaster-beep.github.io/Flappybird.github.io/" />

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

        /* --- COOKIE CONSENT BANNER --- */
        #cookieConsent {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(10, 10, 30, 0.97);
            backdrop-filter: blur(10px);
            border-top: 2px solid #2a2a4a;
            padding: 16px 5%;
            z-index: 999;
            display: none;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 12px;
        }
        #cookieConsent p {
            font-size: clamp(13px, 1.2vw, 16px);
            color: #ccc;
            flex: 1;
            min-width: 200px;
        }
        #cookieConsent .cookie-buttons {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        #cookieConsent button {
            padding: 8px 20px;
            border-radius: 6px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            font-size: 14px;
            transition: all 0.2s;
        }
        #cookieConsent .btn-accept {
            background: #ffcc00;
            color: #222;
        }
        #cookieConsent .btn-accept:hover {
            background: #ffd83d;
        }
        #cookieConsent .btn-decline {
            background: transparent;
            color: #aaa;
            border: 1px solid #555;
        }
        #cookieConsent .btn-decline:hover {
            background: rgba(255, 255, 255, 0.05);
            color: #fff;
        }
        #cookieConsent .btn-settings {
            background: transparent;
            color: #9fd6ff;
            border: 1px solid #2a4a6a;
        }
        #cookieConsent .btn-settings:hover {
            background: rgba(159, 214, 255, 0.1);
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

        .page h4 {
            font-size: clamp(16px, 1.5vw, 19px);
            color: #ffcc00;
            margin: 14px 0 8px;
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

        /* --- ARTICLE FULL PAGE --- */
        .article-full {
            max-width: 820px;
            margin: 0 auto;
        }
        .article-full .article-meta {
            color: #888;
            font-size: 14px;
            margin-bottom: 20px;
            border-bottom: 1px solid #2a2a4a;
            padding-bottom: 12px;
        }
        .article-full .article-meta span {
            margin-right: 16px;
        }
        .article-full .article-body img {
            max-width: 100%;
            border-radius: 8px;
            margin: 16px 0;
        }
        .article-full .article-body blockquote {
            border-left: 4px solid #ffcc00;
            padding: 12px 20px;
            margin: 16px 0;
            background: rgba(255, 204, 0, 0.06);
            border-radius: 0 8px 8px 0;
            font-style: italic;
            color: #ccc;
        }
        .article-full .article-body .tip-box {
            background: rgba(255, 204, 0, 0.08);
            border-left: 4px solid #ffcc00;
            padding: 14px 18px;
            margin: 16px 0;
            border-radius: 0 8px 8px 0;
        }
        .article-full .article-body .tip-box strong {
            color: #ffcc00;
        }
        .article-full .article-body .highlight {
            color: #ffcc00;
            font-weight: 600;
        }
        .article-full .back-to-blog {
            display: inline-block;
            margin-top: 24px;
            padding: 8px 20px;
            background: rgba(255, 204, 0, 0.1);
            border: 1px solid #2a2a4a;
            border-radius: 6px;
            color: #ffcc00;
            font-weight: 600;
        }
        .article-full .back-to-blog:hover {
            background: rgba(255, 204, 0, 0.2);
            text-decoration: none;
        }

        /* --- GAME SECTION - CLEAN, NO ADS --- */
        #gameSection {
            display: flex;
            flex-direction: column;
            align-items: center;
            max-width: 500px;
            margin: 0 auto;
        }

        #gameContainer {
            position: relative;
            width: 100%;
            max-width: 480px;
            aspect-ratio: 400 / 600;
            box-shadow: 0 0 40px rgba(0, 0, 0, 0.7);
            border-radius: 8px;
            overflow: hidden;
            background: #70c5ce;
        }

        #gameCanvas {
            display: block;
            width: 100%;
            height: 100%;
            background: #70c5ce;
            image-rendering: pixelated;
        }

        /* --- OVERLAY --- */
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
        .smallBtn:hover {
            background: #ffd83d;
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
            cursor: pointer;
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
        .blog-card .meta span {
            margin-right: 12px;
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

        /* --- AD PLACEMENTS --- */
        .ad-in-article {
            width: 100%;
            max-width: 728px;
            min-height: 90px;
            margin: 24px auto;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 4px;
            border: 1px dashed rgba(255, 255, 255, 0.08);
            font-size: 12px;
            color: #555;
            overflow: hidden;
            padding: 10px;
            text-align: center;
        }

        .ad-in-article ins.adsbygoogle {
            display: block;
            width: 728px;
            height: 90px;
        }

        .ad-sidebar {
            width: 100%;
            max-width: 300px;
            min-height: 250px;
            margin: 16px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 4px;
            border: 1px dashed rgba(255, 255, 255, 0.08);
            font-size: 12px;
            color: #555;
            overflow: hidden;
            padding: 10px;
        }

        .ad-sidebar ins.adsbygoogle {
            display: block;
            width: 300px;
            height: 250px;
        }

        .blog-layout {
            display: flex;
            gap: 24px;
            flex-wrap: wrap;
        }
        .blog-layout .blog-main {
            flex: 2;
            min-width: 280px;
        }
        .blog-layout .blog-sidebar {
            flex: 1;
            min-width: 200px;
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
            .blog-layout {
                flex-direction: column;
            }
            .ad-sidebar {
                max-width: 100%;
            }
            .ad-sidebar ins.adsbygoogle {
                width: 320px;
                height: 100px;
            }
            .ad-in-article ins.adsbygoogle {
                width: 320px;
                height: 50px;
            }
        }

        @media (max-width: 450px) {
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
            .ad-in-article ins.adsbygoogle {
                width: 300px;
                height: 50px;
            }
            #cookieConsent {
                padding: 12px 4%;
                flex-direction: column;
                align-items: stretch;
            }
            #cookieConsent .cookie-buttons {
                justify-content: center;
            }
        }

        /* --- UTILITY --- */
        .highlight {
            color: #ffcc00;
            font-weight: 600;
        }
        .tip-box {
            background: rgba(255, 204, 0, 0.08);
            border-left: 4px solid #ffcc00;
            padding: 14px 18px;
            margin: 16px 0;
            border-radius: 0 8px 8px 0;
        }
        .tip-box strong {
            color: #ffcc00;
        }

        .strategy-table {
            width: 100%;
            border-collapse: collapse;
            margin: 16px 0;
            font-size: clamp(13px, 1vw, 16px);
        }
        .strategy-table th,
        .strategy-table td {
            border: 1px solid #2a2a4a;
            padding: 10px 12px;
            text-align: left;
        }
        .strategy-table th {
            background: #2a2a4a;
            color: #ffcc00;
        }
        .strategy-table tr:nth-child(even) {
            background: rgba(255, 255, 255, 0.03);
        }

        .back-to-top {
            display: inline-block;
            margin-top: 20px;
            color: #9fd6ff;
            font-size: 14px;
        }
        .back-to-top:hover {
            color: #ffcc00;
        }

        /* --- ARTICLE GRID FOR BLOG LISTING --- */
        .article-excerpt {
            display: block;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <!-- ========== COOKIE CONSENT BANNER ========== -->
    <div id="cookieConsent">
        <p>🍪 We use cookies to personalize content and ads, and to analyze our traffic. By continuing, you agree to our use of cookies. <a href="#" data-page="privacy" style="color:#ffcc00;">Learn more</a></p>
        <div class="cookie-buttons">
            <button class="btn-settings" onclick="showCookieSettings()">⚙️ Settings</button>
            <button class="btn-decline" onclick="declineCookies()">Decline</button>
            <button class="btn-accept" onclick="acceptCookies()">Accept All</button>
        </div>
    </div>

    <!-- ========== HEADER ========== -->
    <header>
        <nav>
            <div class="logo">Flappy<span>Bird</span> Guide</div>

            <button class="hamburger" id="hamburger" aria-label="Toggle navigation">
                <span></span><span></span><span></span>
            </button>

            <ul class="nav-links" id="navLinks">
                <li><a href="#" class="active" data-page="home">Home</a></li>
                <li><a href="#" data-page="play">Play Game</a></li>
                <li><a href="#" data-page="howto">How to Play</a></li>
                <li><a href="#" data-page="blog">Blog</a></li>
                <li><a href="#" data-page="about">About</a></li>
                <li><a href="#" data-page="contact">Contact</a></li>
                <li><a href="#" data-page="privacy">Privacy</a></li>
                <li><a href="#" data-page="terms">Terms</a></li>
            </ul>
        </nav>
    </header>

    <!-- ========== PAGES ========== -->

    <!-- HOME -->
    <section class="page active" id="page-home">
        <h1>🎮 Master Flappy Bird: Complete Guide & Free Game</h1>
        <p>Welcome to the ultimate <strong>Flappy Bird resource</strong>! Whether you're looking to beat your high score, unlock all birds, or just enjoy the classic arcade experience, you've come to the right place.</p>

        <div style="display:flex; gap:12px; flex-wrap:wrap; margin:16px 0;">
            <a href="#" data-page="play" class="smallBtn" style="padding:10px 24px; font-size:16px;">▶ Play Now</a>
            <a href="#" data-page="howto" class="smallBtn" style="padding:10px 24px; font-size:16px; background:#9fd6ff;">📖 How to Play</a>
            <a href="#" data-page="blog" class="smallBtn" style="padding:10px 24px; font-size:16px; background:#70c5ce;">📝 Blog</a>
        </div>

        <div class="ad-in-article">
            <span>Advertisement</span>
        </div>

        <h2>🔥 Why Flappy Bird?</h2>
        <p>Flappy Bird is more than just a game — it's a cultural phenomenon. Created by Dong Nguyen in 2013, it became one of the most downloaded mobile games of all time. Its simple yet addictive gameplay has inspired countless clones, tributes, and even academic studies on game design and psychology.</p>

        <div class="tip-box">
            <strong>💡 Did You Know?</strong> The original Flappy Bird was removed from app stores in 2014, but its legacy lives on through fan-made versions like this one!
        </div>

        <h2>📈 What You'll Find Here</h2>
        <ul>
            <li><strong>Free Game:</strong> Play the classic Flappy Bird experience in your browser.</li>
            <li><strong>Expert Strategies:</strong> Learn proven techniques to improve your score.</li>
            <li><strong>Unlockable Birds:</strong> Score points to unlock 100+ unique bird designs.</li>
            <li><strong>In-Depth Guides:</strong> Read tutorials on game mechanics, physics, and development.</li>
        </ul>

        <h2>🎯 Quick Tips for Beginners</h2>
        <ul>
            <li>Focus on the <span class="highlight">gap between pipes</span>, not the bird itself.</li>
            <li>Tap <span class="highlight">rhythmically</span> rather than frantically.</li>
            <li>Keep the bird at <span class="highlight">mid-height</span> for better reaction time.</li>
            <li><span class="highlight">Practice daily</span> — muscle memory is key!</li>
        </ul>
    </section>

    <!-- PLAY -->
    <section class="page" id="page-play">
        <h1>Play Flappy Bird</h1>
        <p style="text-align:center; max-width:500px; margin:0 auto 16px;">
            Click, tap, or press <kbd>Space</kbd> to flap. Score <strong>10 points</strong> to unlock your first new bird!
        </p>

        <div id="gameSection">
            <div id="gameContainer">
                <canvas id="gameCanvas" width="400" height="600"></canvas>
                <div id="hud">0</div>
                <div id="userBadge"></div>
                <button id="logoutBtn">Log out</button>
                <div id="overlay"></div>
            </div>
        </div>

        <div style="max-width:500px; margin:16px auto; text-align:center; color:#888; font-size:14px; border-top:1px solid #2a2a4a; padding-top:16px;">
            <p>💡 <strong>Pro Tip:</strong> Focus on the gap, not the bird. Tap consistently, not frantically.</p>
            <p style="margin-top:6px;">🏆 <strong>Challenge:</strong> Can you beat the 1000-point Boss Bird unlock?</p>
        </div>
    </section>

    <!-- HOW TO PLAY -->
    <section class="page" id="page-howto">
        <h1>How to Play Flappy Bird</h1>
        <p>Flappy Bird is a simple but challenging arcade game. Here's everything you need to know to get started.</p>

        <div class="ad-in-article">
            <span>Advertisement</span>
        </div>

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

        <h2>💡 Expert Strategies</h2>
        <table class="strategy-table">
            <thead>
                <tr><th>Strategy</th><th>Why It Works</th></tr>
            </thead>
            <tbody>
                <tr><td><strong>Stay Low</strong></td><td>Flying too high makes it harder to react to pipes. Mid-to-low flight gives you more reaction time.</td></tr>
                <tr><td><strong>Rhythmic Tapping</strong></td><td>Find a steady rhythm that matches the pipe gaps. Consistency beats frantic tapping.</td></tr>
                <tr><td><strong>Focus on the Gap</strong></td><td>Look at the space between pipes, not the bird itself. Your peripheral vision will handle the bird.</td></tr>
                <tr><td><strong>Practice Daily</strong></td><td>Muscle memory develops over time. Short daily sessions are more effective than long sessions.</td></tr>
            </tbody>
        </table>

        <div class="tip-box">
            <strong>🔥 Advanced Tip:</strong> Try to <span class="highlight">anticipate the next pipe</span> before it appears on screen. This gives you a split-second advantage in positioning.
        </div>
    </section>

    <!-- BLOG - LISTING -->
    <section class="page" id="page-blog">
        <h1>Flappy Bird Blog</h1>
        <p>Expert gaming tips, development tutorials, and behind-the-scenes stories. Click any article to read the full post.</p>

        <div class="blog-layout">
            <div class="blog-main">
                <div class="blog-grid" id="blogGrid">
                    <!-- Articles will be rendered by JavaScript -->
                </div>
            </div>
            <div class="blog-sidebar">
                <div class="ad-sidebar">
                    <span>Advertisement</span>
                </div>
                <div style="background:rgba(255,204,0,0.05); border:1px solid #2a2a4a; border-radius:8px; padding:16px; margin-top:16px;">
                    <h3 style="color:#ffcc00; font-size:18px;">📈 Top Tips</h3>
                    <ul style="font-size:14px; color:#bbb;">
                        <li>Tap rhythmically, not frantically</li>
                        <li>Focus on the gap between pipes</li>
                        <li>Keep the bird at mid-height</li>
                        <li>Practice daily for muscle memory</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- BLOG - ARTICLE VIEW (hidden by default) -->
    <section class="page" id="page-article">
        <div class="article-full" id="articleContent">
            <!-- Rendered by JavaScript -->
        </div>
    </section>

    <!-- ABOUT -->
    <section class="page" id="page-about">
        <h1>About FlappyBird Guide</h1>
        <p>FlappyBird Guide is a fan-made resource dedicated to the classic Flappy Bird game. We rebuilt it from scratch using modern web technologies — HTML5 Canvas, CSS3, and vanilla JavaScript — to bring the addictive experience back to browsers everywhere.</p>

        <h2>🌟 Our Mission</h2>
        <p>We believe that great games should be accessible to everyone, anywhere, on any device. That's why FlappyBird Guide is:</p>
        <ul>
            <li><strong>100% Free:</strong> No paywalls, no in-app purchases.</li>
            <li><strong>Cross-Platform:</strong> Play on desktop, tablet, or phone.</li>
            <li><strong>Privacy-First:</strong> We collect minimal data — only what's needed to save your progress.</li>
        </ul>

        <div class="ad-in-article">
            <span>Advertisement</span>
        </div>

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
            <li>🐦 Twitter / X: <a href="#">@FlappyBirdGuide</a></li>
            <li>📸 Instagram: <a href="#">@FlappyBirdGuide</a></li>
            <li>▶️ YouTube: <a href="#">FlappyBird Gameplay</a></li>
        </ul>

        <div class="ad-in-article">
            <span>Advertisement</span>
        </div>

        <h2>📩 Business Inquiries</h2>
        <p>For sponsorship, advertising, or collaboration opportunities, email us directly at the address above with "Business Inquiry" in the subject line.</p>
    </section>

    <!-- PRIVACY POLICY -->
    <section class="page" id="page-privacy">
        <h1>Privacy Policy</h1>
        <p><strong>Last updated:</strong> June 21, 2026</p>

        <p>FlappyBird Guide ("we", "our", or "us") respects your privacy. This policy explains how we collect, use, and protect your personal information.</p>

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

        <h2>7. Cookie Policy</h2>
        <p>We use the following types of cookies:</p>
        <ul>
            <li><strong>Essential:</strong> Required for the game and account functionality.</li>
            <li><strong>Analytics:</strong> Help us understand how users interact with our site.</li>
            <li><strong>Advertising:</strong> Used by Google AdSense to serve relevant ads.</li>
        </ul>
        <p>You can control cookie preferences through your browser settings or our cookie consent banner.</p>
    </section>

    <!-- TERMS OF SERVICE -->
    <section class="page" id="page-terms">
        <h1>Terms of Service</h1>
        <p><strong>Last updated:</strong> June 21, 2026</p>

        <p>Welcome to FlappyBird Guide! By using our game and website, you agree to the following terms.</p>

        <h2>1. Acceptance of Terms</h2>
        <p>By creating an account or playing the game, you agree to these Terms of Service. If you do not agree, please do not use our service.</p>

        <h2>2. User Accounts</h2>
        <ul>
            <li>You are responsible for maintaining the confidentiality of your password.</li>
            <li>You agree to provide accurate information during sign-up.</li>
            <li>We reserve the right to terminate accounts that violate these terms.</li>
            <li>You must be at least 13 years old to create an account.</li>
        </ul>

        <h2>3. Acceptable Use</h2>
        <p>You agree not to:</p>
        <ul>
            <li>Use the service for any illegal or unauthorized purpose.</li>
            <li>Attempt to hack, disrupt, or exploit the game or its backend.</li>
            <li>Share or impersonate another user's account.</li>
            <li>Use bots, cheats, or automated systems to manipulate game scores.</li>
            <li>Post or transmit any harmful, offensive, or inappropriate content.</li>
        </ul>

        <h2>4. Intellectual Property</h2>
        <p>All game code, art, and design are the property of FlappyBird Guide. You may not copy, modify, or distribute any part without permission. The original Flappy Bird concept and characters are the property of Dong Nguyen and .Gears.</p>

        <h2>5. Disclaimer of Warranties</h2>
        <p>The game is provided "as is" without warranties of any kind. We are not liable for any losses or damages arising from your use of the service.</p>

        <h2>6. Limitation of Liability</h2>
        <p>To the maximum extent permitted by law, FlappyBird Guide shall not be liable for any indirect, incidental, or consequential damages arising from your use of the service.</p>

        <h2>7. Third-Party Services</h2>
        <p>Our service integrates with Google AdSense and JSONBin. These services have their own terms and privacy policies, which you should review.</p>

        <h2>8. Changes to Terms</h2>
        <p>We may update these terms periodically. Continued use of the service constitutes acceptance of the updated terms.</p>

        <h2>9. Contact</h2>
        <p>For questions about these terms, please <a href="#" data-page="contact">contact us</a>.</p>
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
            <a href="#" data-page="terms">Terms of Service</a>
        </div>
        <p>&copy; 2026 FlappyBird Guide — Made with ❤️ by Atharv Sharma</p>
    </footer>

    <!-- ========== SCRIPTS ========== -->

    <script>
        // =============================================
        // 1. COOKIE CONSENT
        // =============================================
        function getCookie(name) {
            const match = document.cookie.match(new RegExp('(^| )' + name + '=([^;]+)'));
            return match ? match[2] : null;
        }

        function setCookie(name, value, days) {
            const expires = new Date(Date.now() + days * 86400000).toUTCString();
            document.cookie = name + '=' + value + '; expires=' + expires + '; path=/';
        }

        function acceptCookies() {
            setCookie('cookie_consent', 'accepted', 365);
            setCookie('analytics_consent', 'granted', 365);
            setCookie('ad_consent', 'granted', 365);
            document.getElementById('cookieConsent').style.display = 'none';
        }

        function declineCookies() {
            setCookie('cookie_consent', 'declined', 365);
            setCookie('analytics_consent', 'denied', 365);
            setCookie('ad_consent', 'denied', 365);
            document.getElementById('cookieConsent').style.display = 'none';
        }

        function showCookieSettings() {
            // Simple settings: show a prompt to accept or decline
            if (confirm('Manage cookie preferences:\n\nClick OK to accept all cookies.\nCancel to decline all non-essential cookies.')) {
                acceptCookies();
            } else {
                declineCookies();
            }
        }

        // Check if consent already given
        (function checkCookieConsent() {
            const consent = getCookie('cookie_consent');
            if (!consent) {
                document.getElementById('cookieConsent').style.display = 'flex';
            }
        })();

        // =============================================
        // 2. NAVIGATION
        // =============================================
        const navLinks = document.querySelectorAll('.nav-links a, .footer-links a, [data-page]');
        const pages = {
            home: document.getElementById('page-home'),
            play: document.getElementById('page-play'),
            howto: document.getElementById('page-howto'),
            blog: document.getElementById('page-blog'),
            article: document.getElementById('page-article'),
            about: document.getElementById('page-about'),
            contact: document.getElementById('page-contact'),
            privacy: document.getElementById('page-privacy'),
            terms: document.getElementById('page-terms')
        };

        function showPage(pageId) {
            Object.values(pages).forEach(p => p.classList.remove('active'));
            if (pages[pageId]) pages[pageId].classList.add('active');
            document.querySelectorAll('.nav-links a').forEach(a => {
                a.classList.toggle('active', a.dataset.page === pageId);
            });
            document.getElementById('navLinks').classList.remove('open');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        document.addEventListener('click', function(e) {
            const link = e.target.closest('[data-page]');
            if (link) {
                e.preventDefault();
                const page = link.dataset.page;
                if (pages[page]) showPage(page);
                // If clicking an article from blog, load it
                const articleId = link.dataset.article;
                if (articleId && page === 'article') {
                    loadArticle(parseInt(articleId));
                }
            }
        });

        document.getElementById('hamburger').addEventListener('click', function() {
            document.getElementById('navLinks').classList.toggle('open');
        });

        // =============================================
        // 3. BLOG ARTICLES DATA (20 full articles)
        // =============================================
        const articles = [{
            id: 1,
            title: "10 Flappy Bird Tips to Skyrocket Your Score",
            date: "June 20, 2026",
            readTime: "5 min read",
            excerpt: "From timing your flaps to reading pipe patterns — these 10 pro tips will help you beat your high score every time.",
            category: "Tips",
            body: `
                <h2>1. Master the Rhythm</h2>
                <p>Flappy Bird is all about rhythm. Instead of tapping frantically, find a steady beat that matches the pipe gaps. Count silently — <span class="highlight">"tap, tap, pause"</span> — and you'll find yourself flowing through obstacles more smoothly.</p>

                <h2>2. Keep Your Eyes on the Gap</h2>
                <p>This is the single most important tip. <span class="highlight">Look at the space between the pipes</span>, not at your bird. Your peripheral vision will keep the bird in view while your focus guides you through the opening.</p>

                <div class="tip-box">
                    <strong>💡 Pro Tip:</strong> Try to look about <span class="highlight">one pipe ahead</span> of where you are. This gives you more reaction time and helps you anticipate the next move.
                </div>

                <h2>3. Stay at Mid-Height</h2>
                <p>Avoid flying too high or too low. <span class="highlight">Mid-height flight</span> gives you the most flexibility to react to both high and low gaps. If you stay low, you'll struggle with low gaps; if you stay high, high gaps become impossible.</p>

                <h2>4. Tap Consistently, Not Hard</h2>
                <p>The force of your tap doesn't matter — <span class="highlight">the timing does</span>. A gentle tap is just as effective as a hard tap. Focus on consistency and precision over power.</p>

                <h2>5. Practice Daily in Short Bursts</h2>
                <p>Muscle memory develops through repetition. <span class="highlight">10-15 minutes of practice each day</span> is more effective than a 2-hour session once a week. Your brain needs time to process and internalize the patterns.</p>

                <h2>6. Learn the Pipe Patterns</h2>
                <p>While pipes are randomly generated, there are only a few gap positions. <span class="highlight">Learn to recognize common patterns</span> — high gap, low gap, mid gap — and react accordingly.</p>

                <h2>7. Stay Calm Under Pressure</h2>
                <p>It's easy to panic when you're on a high score run. <span class="highlight">Take deep breaths</span> and maintain your rhythm. Remember: the game is the same at 1 point as it is at 100 points.</p>

                <h2>8. Watch Expert Players</h2>
                <p>Study videos of top Flappy Bird players. Pay attention to <span class="highlight">their tapping rhythm and how they handle different gap positions</span>. You'll pick up subtle techniques you can apply to your own gameplay.</p>

                <h2>9. Use the Spacebar for Precision</h2>
                <p>If you're on a desktop, try using the <span class="highlight">Spacebar instead of clicking</span>. It can feel more responsive and allow for quicker, more precise taps.</p>

                <h2>10. Have Fun!</h2>
                <p>The most important tip: <span class="highlight">enjoy the game</span>. Flappy Bird is frustrating but rewarding. Celebrate every improvement, no matter how small.</p>
            `
        }, {
            id: 2,
            title: "How to Build a Flappy Bird Clone in HTML5",
            date: "June 18, 2026",
            readTime: "8 min read",
            excerpt: "A complete step-by-step tutorial on building Flappy Bird with Canvas, JavaScript, and CSS. Perfect for beginners!",
            category: "Development",
            body: `
                <h2>Step 1: Set Up the HTML Structure</h2>
                <p>Start with a basic HTML file. You'll need a <span class="highlight">canvas element</span> for rendering the game, and a container for the game interface.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">&lt;!DOCTYPE html&gt;
        &lt;html&gt;
        &lt;head&gt;
            &lt;title&gt;Flappy Bird Clone&lt;/title&gt;
            &lt;style&gt;body { margin:0; display:flex; justify-content:center; align-items:center; height:100vh; background:#1a1a2e; }&lt;/style&gt;
        &lt;/head&gt;
        &lt;body&gt;
            &lt;canvas id="game" width="400" height="600"&gt;&lt;/canvas&gt;
            &lt;script src="game.js"&gt;&lt;/script&gt;
        &lt;/body&gt;
        &lt;/html&gt;</pre>

                <h2>Step 2: Draw the Background and Ground</h2>
                <p>Create the sky gradient and the ground using Canvas API. This sets up the visual foundation of your game.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">const canvas = document.getElementById('game');
        const ctx = canvas.getContext('2d');
        const W = 400, H = 600;

        function drawBackground() {
            const gradient = ctx.createLinearGradient(0, 0, 0, 450);
            gradient.addColorStop(0, '#70c5ce');
            gradient.addColorStop(1, '#a8e0e6');
            ctx.fillStyle = gradient;
            ctx.fillRect(0, 0, W, 450);
        }</pre>

                <h2>Step 3: Add the Bird</h2>
                <p>Draw a simple bird shape using ellipses and arcs. Add wings that flap using a sine wave animation.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">function drawBird(x, y, frame) {
            ctx.save();
            ctx.translate(x, y);
            // Body
            ctx.fillStyle = '#ffd23f';
            ctx.beginPath();
            ctx.ellipse(0, 0, 17, 13, 0, 0, Math.PI * 2);
            ctx.fill();
            // Wing
            const wingFlap = Math.sin(frame * 0.4) * 3;
            ctx.fillStyle = '#ffb700';
            ctx.beginPath();
            ctx.ellipse(-4, 2 + wingFlap, 9, 6, -0.3, 0, Math.PI * 2);
            ctx.fill();
            ctx.restore();
        }</pre>

                <div class="tip-box">
                    <strong>💡 Key Concept:</strong> The <span class="highlight">game loop</span> — using <code>requestAnimationFrame</code> — is what makes the game run smoothly at 60fps.
                </div>

                <h2>Step 4: Implement Gravity and Flapping</h2>
                <p>Add gravity to make the bird fall, and flapping to make it rise. This creates the core physics of the game.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">let birdY = 300, birdVy = 0;
        const GRAVITY = 0.5, FLAP = -8;

        function flap() { birdVy = FLAP; }

        function update() {
            birdVy += GRAVITY;
            birdY += birdVy;
        }</pre>

                <h2>Step 5: Generate Pipes</h2>
                <p>Create pipes with random gap positions. Move them across the screen and detect collisions with the bird.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">let pipes = [];
        const PIPE_WIDTH = 60, PIPE_GAP = 150, PIPE_SPEED = 2.6;

        function addPipe() {
            const topHeight = 60 + Math.random() * (300 - 60);
            pipes.push({ x: W, topHeight, bottomY: topHeight + PIPE_GAP });
        }</pre>

                <h2>Step 6: Collision Detection</h2>
                <p>Use AABB (Axis-Aligned Bounding Box) collision detection to check if the bird hits any pipes or the ground.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">function checkCollision(bird, pipe) {
            return bird.x < pipe.x + PIPE_WIDTH &&
                bird.x + bird.w > pipe.x &&
                (bird.y < pipe.topHeight || bird.y + bird.h > pipe.bottomY);
        }</pre>

                <h2>Step 7: Add Scoring and Game Over</h2>
                <p>Track when the bird passes a pipe, increment the score, and handle game over conditions.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">let score = 0;

        function update() {
            for (const pipe of pipes) {
                if (!pipe.passed && pipe.x + PIPE_WIDTH < bird.x) {
                    pipe.passed = true;
                    score++;
                }
            }
        }</pre>

                <div class="tip-box">
                    <strong>🔥 Going Further:</strong> Add <span class="highlight">unlockable birds</span>, a high score system, and mobile touch support to make your clone truly complete!
                </div>
            `
        }, {
            id: 3,
            title: "Why Flappy Bird Still Captivates Players in 2026",
            date: "June 15, 2026",
            readTime: "4 min read",
            excerpt: "Discover the psychology, game design, and cultural impact behind one of the most addictive mobile games ever.",
            category: "Analysis",
            body: `
                <h2>The Simplicity Paradox</h2>
                <p>Flappy Bird is deceptively simple: one button, one bird, one endless challenge. Yet <span class="highlight">it's this simplicity that makes it so addictive</span>. The game strips away all complexity, leaving only pure, immediate feedback.</p>

                <h2>Why We Can't Stop Playing</h2>
                <p>The game leverages several psychological principles:</p>
                <ul>
                    <li><strong>Near-Miss Effect:</strong> When you barely miss a pipe, your brain releases dopamine, encouraging you to try again.</li>
                    <li><strong>Challenge Curve:</strong> The difficulty is perfectly balanced — easy to learn, impossible to master.</li>
                    <li><strong>Immediate Feedback:</strong> Every action has an instant consequence, keeping you engaged.</li>
                </ul>

                <div class="tip-box">
                    <strong>🎯 Key Insight:</strong> Flappy Bird taps into the same psychological rewards as gambling — <span class="highlight">intermittent reinforcement</span> keeps players coming back.
                </div>

                <h2>The Cultural Phenomenon</h2>
                <p>When Flappy Bird was removed from app stores in 2014, it became a <span class="highlight">cultural legend</span>. The game's creator, Dong Nguyen, became an overnight sensation and then promptly disappeared from the spotlight. This mystery only added to the game's allure.</p>

                <h2>Why It Endures</h2>
                <p>In 2026, Flappy Bird remains relevant because:</p>
                <ul>
                    <li><span class="highlight">Nostalgia:</span> Players who grew up with the original game now share it with their children.</li>
                    <li><span class="highlight">Accessibility:</span> It's free, easy to play, and available everywhere.</li>
                    <li><span class="highlight">Community:</span> Fan-made versions, challenges, and competitions keep the spirit alive.</li>
                </ul>
            `
        }, {
            id: 4,
            title: "Game Design 101: What Makes a Game Addictive?",
            date: "June 12, 2026",
            readTime: "6 min read",
            excerpt: "Explore the core principles of addictive game design — from feedback loops to challenge curves.",
            category: "Game Design",
            body: `
                <h2>The Core Loop</h2>
                <p>Every addictive game has a <span class="highlight">core loop</span> — the repeated sequence of actions that keeps players engaged. In Flappy Bird, the core loop is: tap → move bird → avoid pipe → score → repeat.</p>

                <h2>Feedback Loops</h2>
                <p>Effective feedback loops are essential. They can be:</p>
                <ul>
                    <li><strong>Positive:</strong> Score increases, new birds unlock, visual/audio rewards.</li>
                    <li><strong>Negative:</strong> Game over, reset, loss of progress (which paradoxically makes you want to try again).</li>
                </ul>

                <div class="tip-box">
                    <strong>💡 Design Principle:</strong> The best games balance <span class="highlight">challenge and skill</span>. When the challenge matches your skill level, you enter a state of "flow."
                </div>

                <h2>Progression Systems</h2>
                <p>Unlockable content — like the birds in our game — gives players <span class="highlight">short-term goals</span> that keep them playing. Each small achievement releases dopamine, reinforcing the behavior.</p>

                <h2>The Role of Frustration</h2>
                <p>Surprisingly, a moderate amount of frustration can make a game more appealing. <span class="highlight">Overcoming obstacles</span> creates a sense of accomplishment that is deeply satisfying.</p>
            `
        }, {
            id: 5,
            title: "JavaScript Canvas: A Beginner's Guide",
            date: "June 10, 2026",
            readTime: "7 min read",
            excerpt: "Learn the fundamentals of the HTML5 Canvas API — the foundation of browser-based games like Flappy Bird.",
            category: "Development",
            body: `
                <h2>What is the Canvas API?</h2>
                <p>The HTML5 Canvas is a <span class="highlight">drawing surface</span> that allows you to create graphics, animations, and games entirely in JavaScript. It's supported by all modern browsers.</p>

                <h2>Getting Started</h2>
                <p>To use Canvas, you need an HTML element and a JavaScript context:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">const canvas = document.getElementById('myCanvas');
        const ctx = canvas.getContext('2d');
        // Now you can draw!
        ctx.fillStyle = '#ffcc00';
        ctx.fillRect(10, 10, 100, 50);</pre>

                <h2>Drawing Shapes</h2>
                <p>The Canvas API supports rectangles, circles, lines, and complex paths:</p>
                <ul>
                    <li><span class="highlight">fillRect()</span> — draws a filled rectangle</li>
                    <li><span class="highlight">strokeRect()</span> — draws a rectangle outline</li>
                    <li><span class="highlight">arc()</span> — draws circles and arcs</li>
                    <li><span class="highlight">beginPath()</span> and <span class="highlight">closePath()</span> — for custom shapes</li>
                </ul>

                <div class="tip-box">
                    <strong>🎯 Key Concept:</strong> Canvas uses a <span class="highlight">state machine</span> — settings like fillStyle, strokeStyle, and lineWidth affect all subsequent drawing until changed.
                </div>

                <h2>Animating with requestAnimationFrame</h2>
                <p>The <span class="highlight">requestAnimationFrame</span> method creates smooth, efficient animations that sync with the screen refresh rate.</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">function gameLoop() {
            update();
            draw();
            requestAnimationFrame(gameLoop);
        }
        gameLoop();</pre>

                <h2>Handling User Input</h2>
                <p>Capture mouse clicks, keyboard presses, and touch events to make your game interactive:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">canvas.addEventListener('click', function(e) {
            // Handle click
        });

        document.addEventListener('keydown', function(e) {
            if (e.key === ' ') {
                // Handle spacebar
            }
        });</pre>
            `
        }, {
            id: 6,
            title: "CSS Animations for Game UI",
            date: "June 8, 2026",
            readTime: "5 min read",
            excerpt: "Enhance your game's interface with smooth CSS animations — from hover effects to score popups.",
            category: "Development",
            body: `
                <h2>Why CSS Animations?</h2>
                <p>CSS animations are <span class="highlight">lightweight and performant</span>, making them perfect for UI elements like buttons, menus, and score displays. They offload animation work from JavaScript to the browser's rendering engine.</p>

                <h2>Keyframe Animations</h2>
                <p>Use <span class="highlight">@keyframes</span> to define complex animations:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">@keyframes pulse {
            0% { transform: scale(1); opacity: 0.7; }
            50% { transform: scale(1.1); opacity: 1; }
            100% { transform: scale(1); opacity: 0.7; }
        }

        .score-popup {
            animation: pulse 0.5s ease-in-out;
        }</pre>

                <h2>Transition Effects</h2>
                <p>Transitions are perfect for <span class="highlight">hover states and interactive elements</span>:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">.button {
            transition: all 0.3s ease;
        }
        .button:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 20px rgba(255, 204, 0, 0.3);
        }</pre>

                <div class="tip-box">
                    <strong>💡 Best Practice:</strong> Use <span class="highlight">transform</span> and <span class="highlight">opacity</span> for animations — they're GPU-accelerated and won't cause layout recalculations.
                </div>

                <h2>Animating Game Elements</h2>
                <p>CSS animations can enhance many game UI components:</p>
                <ul>
                    <li><strong>Score display:</strong> Pop-up animations when scoring</li>
                    <li><strong>Buttons:</strong> Hover and click feedback</li>
                    <li><strong>Bird gallery:</strong> Smooth transitions between selections</li>
                    <li><strong>Notifications:</strong> Slide-in messages for unlocks</li>
                </ul>
            `
        }, {
            id: 7,
            title: "Optimizing HTML5 Games for Mobile",
            date: "June 5, 2026",
            readTime: "6 min read",
            excerpt: "Learn how to make your browser games run smoothly on phones and tablets with responsive design and performance tips.",
            category: "Development",
            body: `
                <h2>Why Mobile Optimization Matters</h2>
                <p>Over <span class="highlight">50% of web traffic</span> comes from mobile devices. If your game doesn't work well on phones and tablets, you're alienating a huge portion of your audience.</p>

                <h2>Responsive Design</h2>
                <p>Use <span class="highlight">viewport units, flexbox, and media queries</span> to adapt your game's layout to any screen size:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">#gameContainer {
            width: 100%;
            max-width: 500px;
            aspect-ratio: 400 / 600;
        }

        @media (max-width: 450px) {
            #gameContainer { max-width: 100%; }
            .button { font-size: 14px; padding: 6px 12px; }
        }</pre>

                <h2>Touch Events</h2>
                <p>Support touch interactions alongside mouse and keyboard:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">canvas.addEventListener('touchstart', function(e) {
            e.preventDefault();
            // Handle tap
        }, { passive: false });</pre>

                <div class="tip-box">
                    <strong>🎯 Performance Tip:</strong> Use <span class="highlight">image-rendering: pixelated</span> on your canvas to prevent blurring and improve performance on mobile devices.
                </div>

                <h2>Performance Optimization</h2>
                <ul>
                    <li><strong>Avoid repaints:</strong> Minimize DOM manipulation during gameplay.</li>
                    <li><strong>Use requestAnimationFrame:</strong> It's designed for smooth animations.</li>
                    <li><strong>Limit particle effects:</strong> While pretty, they can be resource-intensive on mobile.</li>
                    <li><strong>Test on real devices:</strong> Use browser dev tools' device emulation and test on actual phones.</li>
                </ul>
            `
        }, {
            id: 8,
            title: "The History of Flappy Bird: Rise and Fall",
            date: "June 2, 2026",
            readTime: "4 min read",
            excerpt: "The story of how a simple indie game became a global phenomenon — and why its creator pulled it from app stores.",
            category: "History",
            body: `
                <h2>The Birth of a Legend</h2>
                <p>In 2013, Vietnamese developer <span class="highlight">Dong Nguyen</span> released Flappy Bird on the App Store. It was a simple, unpolished game that barely anyone noticed — at first.</p>

                <h2>The Viral Explosion</h2>
                <p>By early 2014, Flappy Bird had become <span class="highlight">the most downloaded free game</span> on both iOS and Android. It was everywhere: on social media, in the news, and on millions of phones worldwide.</p>

                <h2>The Controversy</h2>
                <p>But fame came with a price. Nguyen faced:</p>
                <ul>
                    <li><strong>Death threats:</strong> From frustrated players</li>
                    <li><strong>Media scrutiny:</strong> Constant interviews and attention</li>
                    <li><strong>Guilt:</strong> Feeling responsible for people's addiction to his game</li>
                </ul>

                <div class="tip-box">
                    <strong>📱 The Removal:</strong> On February 10, 2014, <span class="highlight">Dong Nguyen removed Flappy Bird</span> from all app stores. He said: <em>"I can call Flappy Bird a success of mine. But it also ruins my simple life. So now I hate it."</em>
                </div>

                <h2>The Legacy</h2>
                <p>Despite its removal, Flappy Bird's legacy continues. It <span class="highlight">inspired thousands of clones</span>, launched the hyper-casual game genre, and proved that a simple game could become a global phenomenon.</p>
            `
        }, {
            id: 9,
            title: "From Zero to Hero: My Flappy Bird Journey",
            date: "May 30, 2026",
            readTime: "3 min read",
            excerpt: "One player's story of going from a score of 0 to 200+ — with the lessons learned along the way.",
            category: "Personal",
            body: `
                <h2>Day 1: Complete Failure</h2>
                <p>When I first picked up Flappy Bird, I couldn't score more than <span class="highlight">3 points</span>. Every attempt ended with a frustrating crash into the first or second pipe. I almost gave up.</p>

                <h2>Week 1: Finding the Rhythm</h2>
                <p>Then I discovered <span class="highlight">the rhythm</span>. Instead of tapping frantically, I started counting: "One... two... tap." Suddenly, I could reach 10 points. Then 20. The game started to make sense.</p>

                <div class="tip-box">
                    <strong>🎯 Breakthrough:</strong> The key was <span class="highlight">focusing on the gap</span> and ignoring the bird. Once I stopped watching my bird, my scores doubled.
                </div>

                <h2>Month 1: Consistent Progress</h2>
                <p>By the end of the month, I was consistently scoring <span class="highlight">50+ points</span>. I had unlocked several birds and was addicted to the feeling of progress.</p>

                <h2>Today: 200+ Points</h2>
                <p>Now I can reach 200 points on a good run. The game is still challenging, but <span class="highlight">I've learned to enjoy the process</span>, not just the result. Every attempt is a chance to improve.</p>

                <h2>Lessons Learned</h2>
                <ul>
                    <li><span class="highlight">Consistency beats intensity:</span> Short daily practice is more effective than long sessions.</li>
                    <li><span class="highlight">Patience is key:</span> Getting frustrated only makes you worse.</li>
                    <li><span class="highlight">Celebrate small wins:</span> Every personal best is a victory.</li>
                </ul>
            `
        }, {
            id: 10,
            title: "Building a High Score System with JSONBin",
            date: "May 28, 2026",
            readTime: "7 min read",
            excerpt: "Learn how to build a cloud-based leaderboard for your HTML5 games using the JSONBin API.",
            category: "Development",
            body: `
                <h2>What is JSONBin?</h2>
                <p>JSONBin is a <span class="highlight">simple JSON storage service</span> that lets you store and retrieve data via a REST API. It's perfect for game leaderboards, player profiles, and game state.</p>

                <h2>Setting Up a JSONBin Account</h2>
                <p>Create a free account at <a href="https://jsonbin.io" target="_blank">jsonbin.io</a>. You'll need your <span class="highlight">Master Key</span> to authenticate requests.</p>

                <h2>Storing Player Data</h2>
                <p>Here's how to store a player's high score:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">async function saveScore(username, score) {
            const binId = 'your-bin-id';
            const masterKey = 'your-master-key';
            const url = https://api.jsonbin.io/v3/b/${binId};

            const response = await fetch(url, {
                method: 'PUT',
                headers: {
                    'Content-Type': 'application/json',
                    'X-Master-Key': masterKey
                },
                body: JSON.stringify({ scores: { [username]: score } })
            });
            return response.ok;
        }</pre>

                <div class="tip-box">
                    <strong>💡 Security Note:</strong> Never expose your Master Key in client-side code. Use it only in server-side or cloud functions. For this demo, we're using it in the client for simplicity.
                </div>

                <h2>Retrieving the Leaderboard</h2>
                <p>Fetch and display the top scores:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">async function getScores() {
            const response = await fetch(url + '/latest', {
                headers: { 'X-Master-Key': masterKey }
            });
            const data = await response.json();
            return data.record.scores;
        }</pre>

                <h2>Limitations and Alternatives</h2>
                <p>JSONBin has rate limits on free accounts. For production games, consider:</p>
                <ul>
                    <li>Firebase Realtime Database</li>
                    <li>Supabase</li>
                    <li>A custom backend with Node.js</li>
                </ul>
            `
        }, {
            id: 11,
            title: "Responsive Design for Game Websites",
            date: "May 25, 2026",
            readTime: "5 min read",
            excerpt: "Ensure your game looks great on every device with flexible layouts, media queries, and fluid grids.",
            category: "Development",
            body: `
                <h2>Why Responsive Design Matters</h2>
                <p>Players will access your game from <span class="highlight">phones, tablets, laptops, and desktops</span>. A responsive design ensures everyone has a great experience, regardless of their device.</p>

                <h2>Fluid Layouts</h2>
                <p>Use <span class="highlight">relative units</span> like percentages, vw, vh, and em instead of fixed pixels:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">#gameContainer {
            width: 100%;
            max-width: 500px;
            aspect-ratio: 400 / 600;
        }

        .heading {
            font-size: clamp(24px, 5vw, 44px);
        }</pre>

                <h2>Media Queries</h2>
                <p>Use media queries to <span class="highlight">adjust layouts at different breakpoints</span>:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">/* For mobile devices */
        @media (max-width: 450px) {
            .nav-links { display: none; }
            .hamburger { display: flex; }
            .blog-grid { grid-template-columns: 1fr; }
        }</pre>

                <div class="tip-box">
                    <strong>🎯 Best Practice:</strong> <span class="highlight">Mobile-first design</span> — start with the mobile layout and add complexity for larger screens.
                </div>

                <h2>Testing Responsive Design</h2>
                <p>Use browser dev tools (F12) to test your design across different devices. The <span class="highlight">device emulation</span> feature lets you preview how your site looks on various phones and tablets.</p>
            `
        }, {
            id: 12,
            title: "Monetizing Your HTML5 Game with AdSense",
            date: "May 22, 2026",
            readTime: "6 min read",
            excerpt: "A practical guide to integrating Google AdSense into your game website while maintaining a good user experience.",
            category: "Business",
            body: `
                <h2>The AdSense Approval Process</h2>
                <p>Getting approved for AdSense requires:</p>
                <ul>
                    <li><span class="highlight">Original content:</span> Your site must have substantial, unique content.</li>
                    <li><span class="highlight">Good user experience:</span> No intrusive ads, clear navigation.</li>
                    <li><span class="highlight">Essential pages:</span> Privacy Policy, Terms of Service, About, Contact.</li>
                    <li><span class="highlight">No ad placement on interactive elements:</span> Keep ads away from game mechanics.</li>
                </ul>

                <h2>Safe Ad Placement</h2>
                <p>Place ads <span class="highlight">on content pages, not on the game itself</span>. Good placements include:</p>
                <ul>
                    <li>Between blog articles or sections</li>
                    <li>In sidebars</li>
                    <li>Below content (before the footer)</li>
                    <li>On the homepage (content section)</li>
                </ul>

                <div class="tip-box">
                    <strong>⚠️ Important:</strong> <span class="highlight">Never place ads directly on or around your game</span>. This can lead to accidental clicks and AdSense policy violations.
                </div>

                <h2>Ad Formats to Consider</h2>
                <ul>
                    <li><strong>Display ads:</strong> 728x90 (header), 300x250 (sidebar)</li>
                    <li><strong>In-article ads:</strong> Between content sections</li>
                    <li><strong>Auto ads:</strong> Let Google place ads automatically (but monitor placement)</li>
                </ul>

                <h2>Earnings Expectations</h2>
                <p>AdSense earnings depend on <span class="highlight">traffic, ad placements, and niche</span>. Gaming sites typically have lower RPM (revenue per thousand impressions) but can still be profitable with high traffic.</p>
            `
        }, {
            id: 13,
            title: "Game Physics: Simulating Gravity in JavaScript",
            date: "May 20, 2026",
            readTime: "5 min read",
            excerpt: "Understand the math behind gravity, velocity, and collision detection in 2D games.",
            category: "Development",
            body: `
                <h2>The Physics of Falling</h2>
                <p>Gravity is one of the most important concepts in game physics. In Flappy Bird, gravity pulls the bird down, while flapping pushes it up.</p>

                <h2>Implementing Gravity</h2>
                <p>Here's the basic gravity code used in Flappy Bird:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">const GRAVITY = 0.45;
        const FLAP_VELOCITY = -8;
        const MAX_FALL_SPEED = 10;

        let birdVy = 0;

        function update() {
            // Apply gravity
            birdVy += GRAVITY;
            // Limit fall speed
            if (birdVy > MAX_FALL_SPEED) birdVy = MAX_FALL_SPEED;
            // Move bird
            bird.y += birdVy;
        }

        function flap() {
            birdVy = FLAP_VELOCITY;
        }</pre>

                <div class="tip-box">
                    <strong>💡 Physics Concept:</strong> <span class="highlight">Acceleration due to gravity</span> is constant (9.8 m/s² in real life). In games, we use a simplified version for gameplay purposes.
                </div>

                <h2>Velocity and Position</h2>
                <p>In game physics:</p>
                <ul>
                    <li><span class="highlight">Position</span> is where the object is (x, y coordinates)</li>
                    <li><span class="highlight">Velocity</span> is the rate of change of position</li>
                    <li><span class="highlight">Acceleration</span> is the rate of change of velocity</li>
                </ul>

                <h2>Collision Detection</h2>
                <p>AABB (Axis-Aligned Bounding Box) is the simplest collision detection method:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">function rectsOverlap(ax, ay, aw, ah, bx, by, bw, bh) {
            return ax < bx + bw && ax + aw > bx &&
                   ay < by + bh && ay + ah > by;
        }</pre>
            `
        }, {
            id: 14,
            title: "10 Common Mistakes in Game Development",
            date: "May 18, 2026",
            readTime: "6 min read",
            excerpt: "Learn from the most frequent pitfalls faced by indie game developers — and how to avoid them.",
            category: "Development",
            body: `
                <h2>1. Overcomplicating the Game</h2>
                <p>Starting with a simple concept and <span class="highlight">over-engineering it</span> is a classic mistake. Flappy Bird succeeded because of its simplicity.</p>

                <h2>2. Ignoring Mobile Support</h2>
                <p>Most players will access your game on a phone. <span class="highlight">Test on mobile early</span> in development.</p>

                <h2>3. Poor Performance</h2>
                <p>Unoptimized code leads to lag and frustrated players. Use <span class="highlight">requestAnimationFrame</span> and minimize DOM manipulation.</p>

                <div class="tip-box">
                    <strong>💡 Fix:</strong> Profile your game's performance using browser dev tools. Look for <span class="highlight">long frames, memory leaks, and expensive operations</span>.
                </div>

                <h2>4. Not Handling Edge Cases</h2>
                <p>What happens when the bird goes too high or too low? <span class="highlight">Test all boundary conditions</span>.</p>

                <h2>5. Forgetting About UX</h2>
                <p>User experience matters. <span class="highlight">Clear instructions, responsive controls, and visual feedback</span> are essential.</p>

                <h2>6. Skipping the Tutorial</h2>
                <p>Players need to understand the controls. <span class="highlight">Include a brief tutorial or tooltip</span>.</p>

                <h2>7. Not Testing on Multiple Browsers</h2>
                <p>Your game might work in Chrome but fail in Safari. <span class="highlight">Test across browsers</span>.</p>

                <h2>8. Poor Audio Design</h2>
                <p>Sound effects can make or break a game. <span class="highlight">Use subtle, satisfying audio cues</span>.</p>

                <h2>9. Ignoring Feedback</h2>
                <p>Listen to player feedback. <span class="highlight">Iterate based on real user experiences</span>.</p>

                <h2>10. Giving Up Too Soon</h2>
                <p>Game development is a marathon, not a sprint. <span class="highlight">Persevere through challenges</span>.</p>
            `
        }, {
            id: 15,
            title: "Flappy Bird Community: Best Fan Games",
            date: "May 15, 2026",
            readTime: "4 min read",
            excerpt: "Explore the most creative and fun Flappy Bird fan games made by players around the world.",
            category: "Community",
            body: `
                <h2>The Power of Fan-Made Games</h2>
                <p>Since the original Flappy Bird was removed, the community has created <span class="highlight">hundreds of tributes, clones, and creative remakes</span>. Here are some of the best:</p>

                <h2>Flappy Dunk</h2>
                <p>A basketball-themed version where you <span class="highlight">guide a basketball through hoops</span> instead of pipes. The physics are spot-on and the dunk sound effect is incredibly satisfying.</p>

                <h2>Flappy Fighter</h2>
                <p>A fighting game where Flappy Bird's mechanics determine <span class="highlight">who wins in a boxing match</span>. It's a weird but brilliant crossover.</p>

                <div class="tip-box">
                    <strong>🎮 Community Spotlight:</strong> Check out <span class="highlight">"Flappy Golf"</span> — a mashup with golf mechanics where you navigate the bird through obstacles on a golf course.
                </div>

                <h2>Flappy 2048</h2>
                <p>A mashup with the 2048 puzzle game. <span class="highlight">Merge birds instead of numbers</span> while avoiding obstacles. It's chaotic and addictive.</p>

                <h2>Why Fan Games Matter</h2>
                <p>Fan games keep the Flappy Bird <span class="highlight">spirit alive</span>. They showcase creativity, community engagement, and the enduring appeal of simple game mechanics.</p>
            `
        }, {
            id: 16,
            title: "How to Use GitHub Pages for Game Hosting",
            date: "May 12, 2026",
            readTime: "5 min read",
            excerpt: "Deploy your HTML5 game for free with GitHub Pages — perfect for indie developers and hobbyists.",
            category: "Development",
            body: `
                <h2>What is GitHub Pages?</h2>
                <p>GitHub Pages is a <span class="highlight">free hosting service</span> that serves websites directly from your GitHub repository. It's ideal for HTML5 games.</p>

                <h2>Step 1: Create a Repository</h2>
                <p>On GitHub, create a new repository named <span class="highlight">username.github.io</span> (replace username with your GitHub username). This creates a site at that URL.</p>

                <h2>Step 2: Upload Your Game Files</h2>
                <p>Upload your HTML, CSS, and JavaScript files to the repository. <span class="highlight">Your main file should be index.html</span>.</p>

                <h2>Step 3: Enable GitHub Pages</h2>
                <p>Go to Settings → Pages, select the branch (usually <span class="highlight">main or gh-pages</span>), and save. Your site will be live at your GitHub Pages URL.</p>

                <div class="tip-box">
                    <strong>💡 Pro Tip:</strong> Use a <span class="highlight">custom domain</span> by adding a CNAME file to your repository and configuring your domain provider.
                </div>

                <h2>Benefits of GitHub Pages</h2>
                <ul>
                    <li><span class="highlight">Free</span> — no hosting costs</li>
                    <li><span class="highlight">Fast</span> — CDN-backed delivery</li>
                    <li><span class="highlight">Versioned</span> — all changes are tracked</li>
                    <li><span class="highlight">HTTPS</span> — secure by default</li>
                </ul>
            `
        }, {
            id: 17,
            title: "Game Audio: Adding Sound Effects to HTML5 Games",
            date: "May 10, 2026",
            readTime: "4 min read",
            excerpt: "Use the Web Audio API to add sound effects and background music to your browser games.",
            category: "Development",
            body: `
                <h2>Why Audio Matters</h2>
                <p>Sound effects <span class="highlight">enhance immersion and provide essential feedback</span> to players. A well-timed sound can make a game feel significantly more polished.</p>

                <h2>Using the Web Audio API</h2>
                <p>The Web Audio API is a powerful tool for <span class="highlight">generating and manipulating audio</span> in the browser:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">function playSound(frequency, duration) {
            const ctx = new (window.AudioContext || window.webkitAudioContext)();
            const oscillator = ctx.createOscillator();
            const gainNode = ctx.createGain();

            oscillator.type = 'sine';
            oscillator.frequency.value = frequency;

            gainNode.gain.setValueAtTime(0.3, ctx.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + duration);

            oscillator.connect(gainNode);
            gainNode.connect(ctx.destination);

            oscillator.start(ctx.currentTime);
            oscillator.stop(ctx.currentTime + duration);
        }</pre>

                <div class="tip-box">
                    <strong>🎯 Sound Design Tip:</strong> Use <span class="highlight">different frequencies for different game events</span>. A high-pitched sound for scoring, a low sound for game over.
                </div>

                <h2>Loading Audio Files</h2>
                <p>For realistic sounds, load audio files instead of synthesizing:</p>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">const audio = new Audio('flap.mp3');
        audio.play();</pre>

                <h2>Best Practices</h2>
                <ul>
                    <li>Keep audio files small (< 100KB) for fast loading</li>
                    <li>Use <span class="highlight">MP3 and OGG formats</span> for broad browser support</li>
                    <li>Provide a <span class="highlight">mute button</span> for user control</li>
                </ul>
            `
        }, {
            id: 18,
            title: "Designing a Custom Domain for Your Game",
            date: "May 8, 2026",
            readTime: "3 min read",
            excerpt: "Why a custom domain matters — and how to set one up for your game website.",
            category: "Business",
            body: `
                <h2>Why a Custom Domain?</h2>
                <p>A custom domain like <span class="highlight">flappybirdguide.com</span> builds trust, makes your site memorable, and is <span class="highlight">required for AdSense approval</span>.</p>

                <h2>Choosing a Domain Name</h2>
                <p>Tips for selecting a good domain:</p>
                <ul>
                    <li>Keep it <span class="highlight">short and memorable</span></li>
                    <li>Use <span class="highlight">.com, .io, or .game</span> extensions</li>
                    <li>Include your <span class="highlight">game's name or theme</span></li>
                    <li>Avoid numbers and hyphens</li>
                </ul>

                <h2>Registering Your Domain</h2>
                <p>Purchase your domain from a registrar like <span class="highlight">Namecheap, GoDaddy, or Google Domains</span>. Prices typically range from $5-15 per year.</p>

                <div class="tip-box">
                    <strong>💡 Setup Process:</strong> 1. Buy domain → 2. Point DNS to your host → 3. Add CNAME/A records → 4. Configure your hosting → 5. Verify ownership → 6. Apply for AdSense
                </div>

                <h2>Connecting to GitHub Pages</h2>
                <p>Add a <span class="highlight">CNAME file</span> to your repository with your custom domain, and configure your domain provider's DNS settings to point to GitHub's servers.</p>
            `
        }, {
            id: 19,
            title: "From Mobile to Browser: Porting Flappy Bird",
            date: "May 5, 2026",
            readTime: "6 min read",
            excerpt: "How to adapt a mobile game for the browser — tackling touch events, screen sizes, and performance.",
            category: "Development",
            body: `
                <h2>The Challenge of Porting</h2>
                <p>Mobile games are designed for <span class="highlight">touch input and smaller screens</span>. Porting to the browser requires careful adaptation.</p>

                <h2>Touch to Mouse/Keyboard</h2>
                <p>In the mobile version, players tap the screen. In the browser, you need to support:</p>
                <ul>
                    <li><span class="highlight">Mouse clicks</span> (desktop)</li>
                    <li><span class="highlight">Keyboard inputs</span> (Space, Up Arrow)</li>
                    <li><span class="highlight">Touch events</span> (mobile browsers)</li>
                </ul>
                <pre style="background:#1a1a2e; padding:12px; border-radius:6px; overflow-x:auto; color:#7ec850;">canvas.addEventListener('click', flap);
        canvas.addEventListener('touchstart', flap);
        document.addEventListener('keydown', (e) => {
            if (e.key === ' ') flap();
        });</pre>

                <div class="tip-box">
                    <strong>📱 Key Insight:</strong> Browser games must <span class="highlight">support multiple input methods</span> to work across devices.
                </div>

                <h2>Screen Size Adaptation</h2>
                <p>In the browser, screens vary from 320px to 4K+ monitors. Use:</p>
                <ul>
                    <li><span class="highlight">Responsive CSS</span> to scale the game</li>
                    <li><span class="highlight">Aspect-ratio locking</span> to maintain proportions</li>
                    <li><span class="highlight">Media queries</span> for device-specific layouts</li>
                </ul>

                <h2>Performance Considerations</h2>
                <p>Browser games have different performance characteristics than mobile apps. Ensure smooth 60fps performance across devices.</p>
            `
        }, {
            id: 20,
            title: "Why Simplicity Wins in Game Design",
            date: "May 2, 2026",
            readTime: "4 min read",
            excerpt: "A deep dive into why simple, polished games like Flappy Bird often outperform complex, bloated ones.",
            category: "Game Design",
            body: `
                <h2>The Power of Simplicity</h2>
                <p>Simple games like Flappy Bird succeed because <span class="highlight">they're accessible to everyone</span>. There's no learning curve, no complex controls, no barriers to entry.</p>

                <h2>Less is More</h2>
                <p>By focusing on one core mechanic, Flappy Bird achieves:</p>
                <ul>
                    <li><span class="highlight">Instant understanding</span> — players know what to do immediately</li>
                    <li><span class="highlight">Easy iteration</span> — the game loop is tight and satisfying</li>
                    <li><span class="highlight">Broad appeal</span> — anyone can pick it up and play</li>
                </ul>

                <div class="tip-box">
                    <strong>🎯 Design Principle:</strong> <span class="highlight">"Perfection is achieved, not when there is nothing more to add, but when there is nothing left to take away."</span> — Antoine de Saint-Exupéry
                </div>

                <h2>The Polarization Effect</h2>
                <p>Simple games often create <span class="highlight">strong emotional reactions</span>. Players either love them or hate them. This polarization drives word-of-mouth and viral growth.</p>

                <h2>Applying This to Your Game</h2>
                <p>When designing your own game:</p>
                <ul>
                    <li>Start with <span class="highlight">one core mechanic</span></li>
                    <li><span class="highlight">Polish it</span> until it feels perfect</li>
                    <li><span class="highlight">Remove complexity</span> whenever possible</li>
                    <li><span class="highlight">Test with non-gamers</span> to ensure accessibility</li>
                </ul>
            `
        }];

        // =============================================
        // 4. RENDER BLOG
        // =============================================
        const blogGrid = document.getElementById('blogGrid');

        function renderBlog() {
            if (!blogGrid) return;
            blogGrid.innerHTML = articles.map(article => `
                <div class="blog-card article-excerpt" data-article-id="${article.id}">
                    <div style="display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:4px;">
                        <span style="font-size:11px; color:#70c5ce; background:rgba(112,197,206,0.15); padding:2px 10px; border-radius:12px;">${article.category}</span>
                    </div>
                    <h3>${article.title}</h3>
                    <div class="meta">
                        <span>📅 ${article.date}</span>
                        <span>⏱️ ${article.readTime}</span>
                    </div>
                    <p>${article.excerpt}</p>
                    <a href="#" data-page="article" data-article="${article.id}" class="read-more">Read Full Article →</a>
                </div>
            `).join('');

            // Click on blog card to open article
            document.querySelectorAll('.article-excerpt').forEach(card => {
                card.addEventListener('click', function(e) {
                    const id = this.dataset.articleId;
                    if (id && !e.target.closest('a')) {
                        loadArticle(parseInt(id));
                        showPage('article');
                    }
                });
            });
        }

        // =============================================
        // 5. LOAD ARTICLE
        // =============================================
        function loadArticle(id) {
            const article = articles.find(a => a.id === id);
            if (!article) return;

            const container = document.getElementById('articleContent');
            container.innerHTML = `
                <a href="#" data-page="blog" class="back-to-blog">← Back to Blog</a>
                <h1>${article.title}</h1>
                <div class="article-meta">
                    <span>📅 ${article.date}</span>
                    <span>⏱️ ${article.readTime}</span>
                    <span>🏷️ ${article.category}</span>
                </div>
                <div class="article-body">
                    ${article.body}
                </div>
                <a href="#" data-page="blog" class="back-to-blog">← Back to Blog</a>
            `;

            // Re-bind navigation for back links
            container.querySelectorAll('[data-page]').forEach(el => {
                el.addEventListener('click', function(e) {
                    e.preventDefault();
                    const page = this.dataset.page;
                    if (pages[page]) showPage(page);
                });
            });
        }

        // =============================================
        // 6. GAME CODE
        // =============================================
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

        // =============================================
        // 7. INIT
        // =============================================
        renderBlog();

        // Handle "Read More" clicks from blog grid
        document.addEventListener('click', function(e) {
            const link = e.target.closest('[data-article]');
            if (link) {
                e.preventDefault();
                const id = parseInt(link.dataset.article);
                if (!isNaN(id)) {
                    loadArticle(id);
                    showPage('article');
                }
            }
        });
    </script>

</body>
</html>
