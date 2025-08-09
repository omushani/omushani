<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile README</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            color: #333;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                rgba(255, 255, 255, 0.05) 10px,
                rgba(255, 255, 255, 0.05) 20px
            );
            animation: slide 20s linear infinite;
        }

        @keyframes slide {
            0% { transform: translateX(-50px) translateY(-50px); }
            100% { transform: translateX(0px) translateY(0px); }
        }

        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 48px;
            position: relative;
            z-index: 1;
        }

        .header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            position: relative;
            z-index: 1;
        }

        .header p {
            font-size: 1.2rem;
            opacity: 0.9;
            position: relative;
            z-index: 1;
        }

        .content {
            padding: 40px;
        }

        .section {
            margin-bottom: 40px;
        }

        .section h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: #667eea;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 30px;
        }

        .skill-card {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            transform: translateY(0);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);
        }

        .skill-icon {
            font-size: 2rem;
            margin-bottom: 10px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: white;
            border: 2px solid #e1e8ed;
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            border-color: #667eea;
            transform: translateY(-3px);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 5px;
        }

        .game-container {
            background: linear-gradient(135deg, #ff6b6b, #4ecdc4);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            color: white;
        }

        .game-board {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
            max-width: 400px;
            margin: 20px auto;
        }

        .game-tile {
            aspect-ratio: 1;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .game-tile:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: scale(1.05);
        }

        .game-tile.revealed {
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            border-color: #fff;
        }

        .game-tile.matched {
            background: rgba(76, 175, 80, 0.8);
            color: white;
        }

        .game-controls {
            margin-top: 20px;
        }

        .game-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid white;
            padding: 12px 24px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            margin: 0 10px;
            transition: all 0.3s ease;
        }

        .game-btn:hover {
            background: white;
            color: #ff6b6b;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 20px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            }
            
            .game-board {
                max-width: 300px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="profile-img">👨‍💻</div>
            <h1>Your Name</h1>
            <p>Full Stack Developer | Open Source Enthusiast | Problem Solver</p>
        </div>

        <div class="content">
            <div class="section">
                <h2>🚀 About Me</h2>
                <p style="font-size: 1.1rem; line-height: 1.6; color: #666;">
                    Passionate developer with expertise in modern web technologies. I love creating efficient, scalable solutions 
                    and contributing to open source projects. Always eager to learn new technologies and tackle challenging problems.
                </p>
            </div>

            <div class="section">
                <h2>💻 Tech Stack</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <div class="skill-icon">⚛️</div>
                        <div>React</div>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🟢</div>
                        <div>Node.js</div>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🐍</div>
                        <div>Python</div>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">💾</div>
                        <div>MongoDB</div>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🎨</div>
                        <div>CSS3</div>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">⚡</div>
                        <div>JavaScript</div>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">🔧</div>
                        <div>Git</div>
                    </div>
                    <div class="skill-card">
                        <div class="skill-icon">☁️</div>
                        <div>AWS</div>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2>📊 GitHub Stats</h2>
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-number">150+</div>
                        <div>Repositories</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">500+</div>
                        <div>Contributions</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">50+</div>
                        <div>Stars Earned</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">25+</div>
                        <div>Followers</div>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2>🎮 Memory Game Challenge</h2>
                <div class="game-container">
                    <h3>Test Your Memory!</h3>
                    <p>Match the pairs of emojis. Click on tiles to reveal them!</p>
                    
                    <div class="game-board" id="gameBoard"></div>
                    
                    <div style="margin: 20px 0;">
                        <span>Moves: <strong id="moveCount">0</strong></span> | 
                        <span>Matches: <strong id="matchCount">0</strong></span>
                    </div>
                    
                    <div class="game-controls">
                        <button class="game-btn" onclick="startNewGame()">New Game</button>
                        <button class="game-btn" onclick="resetGame()">Reset</button>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2>📫 Connect With Me</h2>
                <div class="contact-links">
                    <a href="#" class="contact-link">
                        <span>📧</span>
                        <span>Email</span>
                    </a>
                    <a href="#" class="contact-link">
                        <span>💼</span>
                        <span>LinkedIn</span>
                    </a>
                    <a href="#" class="contact-link">
                        <span>🐦</span>
                        <span>Twitter</span>
                    </a>
                    <a href="#" class="contact-link">
                        <span>🌐</span>
                        <span>Portfolio</span>
                    </a>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Memory Game Logic
        const emojis = ['🚀', '💻', '🎯', '⚡', '🔥', '💎', '🌟', '🎨'];
        let gameCards = [...emojis, ...emojis];
        let flippedCards = [];
        let matchedPairs = 0;
        let moves = 0;

        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
            return array;
        }

        function createGameBoard() {
            const gameBoard = document.getElementById('gameBoard');
            gameBoard.innerHTML = '';
            
            shuffleArray(gameCards);
            
            gameCards.forEach((emoji, index) => {
                const tile = document.createElement('div');
                tile.className = 'game-tile';
                tile.dataset.emoji = emoji;
                tile.dataset.index = index;
                tile.addEventListener('click', flipCard);
                gameBoard.appendChild(tile);
            });
        }

        function flipCard(event) {
            const tile = event.target;
            
            if (tile.classList.contains('revealed') || tile.classList.contains('matched') || flippedCards.length >= 2) {
                return;
            }

            tile.classList.add('revealed');
            tile.textContent = tile.dataset.emoji;
            flippedCards.push(tile);

            if (flippedCards.length === 2) {
                moves++;
                document.getElementById('moveCount').textContent = moves;
                
                setTimeout(checkMatch, 1000);
            }
        }

        function checkMatch() {
            const [card1, card2] = flippedCards;
            
            if (card1.dataset.emoji === card2.dataset.emoji) {
                card1.classList.add('matched');
                card2.classList.add('matched');
                matchedPairs++;
                document.getElementById('matchCount').textContent = matchedPairs;
                
                if (matchedPairs === emojis.length) {
                    setTimeout(() => {
                        alert(`🎉 Congratulations! You won in ${moves} moves!`);
                    }, 500);
                }
            } else {
                card1.classList.remove('revealed');
                card2.classList.remove('revealed');
                card1.textContent = '';
                card2.textContent = '';
            }
            
            flippedCards = [];
        }

        function startNewGame() {
            gameCards = [...emojis, ...emojis];
            resetGame();
        }

        function resetGame() {
            flippedCards = [];
            matchedPairs = 0;
            moves = 0;
            document.getElementById('moveCount').textContent = '0';
            document.getElementById('matchCount').textContent = '0';
            createGameBoard();
        }

        // Initialize game on page load
        document.addEventListener('DOMContentLoaded', function() {
            createGameBoard();
        });

        // Add hover effects to skill cards
        document.querySelectorAll('.skill-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-5px) rotate(2deg)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) rotate(0deg)';
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96c4cb1d21199a77',t:'MTc1NDcxNjcxMi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
