<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1/10 運試しチャレンジ</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @keyframes bounce-slow {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        .animate-bounce-slow {
            animation: bounce-slow 2s infinite;
        }
        .box-container {
            perspective: 1000px;
        }
        .box-card {
            transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            transform-style: preserve-3d;
            cursor: pointer;
        }
        .box-card.flipped {
            transform: rotateY(180deg);
        }
        .card-face {
            backface-visibility: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 1rem;
        }
        .card-back {
            transform: rotateY(180deg);
        }
    </style>
</head>
<body class="bg-gray-900 text-white min-h-screen flex flex-col items-center justify-center p-4">

    <div class="max-w-md w-full text-center">
        <h1 class="text-4xl font-black mb-2 text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 to-orange-500 animate-bounce-slow">
            LUCKY 1/10
        </h1>
        <p class="text-gray-400 mb-8">10個の箱の中から「当たり」を見つけ出せ！</p>

        <div id="stats" class="grid grid-cols-2 gap-4 mb-8">
            <div class="bg-gray-800 p-3 rounded-lg border border-gray-700">
                <p class="text-xs text-gray-500 uppercase">挑戦回数</p>
                <p id="attempts" class="text-2xl font-bold">0</p>
            </div>
            <div class="bg-gray-800 p-3 rounded-lg border border-gray-700">
                <p class="text-xs text-gray-500 uppercase">当たり回数</p>
                <p id="wins" class="text-2xl font-bold text-yellow-400">0</p>
            </div>
        </div>

        <!-- Game Grid -->
        <div id="gameGrid" class="grid grid-cols-5 gap-3 mb-8">
            <!-- Cards will be generated here -->
        </div>

        <div id="messageBox" class="h-12 flex items-center justify-center mb-4">
            <p id="statusMsg" class="text-lg font-medium text-gray-300">箱を選んでください</p>
        </div>

        <button id="resetBtn" class="bg-gradient-to-r from-blue-600 to-blue-500 hover:from-blue-500 hover:to-blue-400 text-white font-bold py-3 px-8 rounded-full shadow-lg transition-all active:scale-95">
            新しく挑戦する
        </button>
    </div>

    <!-- UI Overlay for Winner -->
    <div id="winOverlay" class="fixed inset-0 bg-black/80 flex flex-col items-center justify-center z-50 hidden transition-opacity duration-500 opacity-0">
        <div class="text-9xl mb-4">✨🏆✨</div>
        <h2 class="text-5xl font-black text-yellow-400 mb-4 text-center">おめでとう！<br>当たり！</h2>
        <p class="text-xl text-white mb-8">10分の1を引き当てました！</p>
        <button onclick="resetGame()" class="bg-yellow-500 hover:bg-yellow-400 text-black font-black py-4 px-12 rounded-full text-xl shadow-2xl transition-transform active:scale-95">
            もう一度遊ぶ
        </button>
    </div>

    <script>
        const gameGrid = document.getElementById('gameGrid');
        const statusMsg = document.getElementById('statusMsg');
        const attemptsEl = document.getElementById('attempts');
        const winsEl = document.getElementById('wins');
        const resetBtn = document.getElementById('resetBtn');
        const winOverlay = document.getElementById('winOverlay');

        let attempts = 0;
        let wins = 0;
        let winningIndex = -1;
        let isGameOver = false;

        function initGame() {
            gameGrid.innerHTML = '';
            winningIndex = Math.floor(Math.random() * 10);
            isGameOver = false;
            statusMsg.textContent = "箱を選んでください";
            statusMsg.className = "text-lg font-medium text-gray-300";
            
            for (let i = 0; i < 10; i++) {
                const container = document.createElement('div');
                container.className = 'box-container h-20 w-full';
                
                const card = document.createElement('div');
                card.className = 'box-card relative w-full h-full';
                card.dataset.index = i;

                // Front Face
                const front = document.createElement('div');
                front.className = 'card-face card-front bg-gray-700 border-2 border-gray-600 hover:border-yellow-500 transition-colors shadow-inner';
                front.innerHTML = '<span class="text-xl font-bold text-gray-400">?</span>';

                // Back Face
                const back = document.createElement('div');
                back.className = 'card-face card-back shadow-lg';
                
                card.appendChild(front);
                card.appendChild(back);
                container.appendChild(card);
                gameGrid.appendChild(container);

                card.addEventListener('click', () => handleChoice(i, card));
            }
        }

        function handleChoice(index, cardElement) {
            if (isGameOver || cardElement.classList.contains('flipped')) return;

            isGameOver = true;
            attempts++;
            attemptsEl.textContent = attempts;

            const isWin = (index === winningIndex);
            const backFace = cardElement.querySelector('.card-back');

            if (isWin) {
                wins++;
                winsEl.textContent = wins;
                backFace.classList.add('bg-yellow-500');
                backFace.innerHTML = '<span class="text-3xl">🌟</span>';
                statusMsg.textContent = "大当たり！";
                statusMsg.className = "text-xl font-bold text-yellow-400";
                
                setTimeout(() => {
                    showOverlay();
                }, 600);
            } else {
                backFace.classList.add('bg-red-500');
                backFace.innerHTML = '<span class="text-3xl">💀</span>';
                statusMsg.textContent = "ハズレ... 残念！";
                statusMsg.className = "text-lg font-medium text-red-400";
                
                // Show where the winner was
                setTimeout(() => {
                    revealWinner();
                }, 400);
            }

            cardElement.classList.add('flipped');
        }

        function revealWinner() {
            const cards = document.querySelectorAll('.box-card');
            const winnerCard = cards[winningIndex];
            if (!winnerCard.classList.contains('flipped')) {
                const backFace = winnerCard.querySelector('.card-back');
                backFace.classList.add('bg-green-600');
                backFace.innerHTML = '<span class="text-3xl">🌟</span>';
                winnerCard.classList.add('flipped');
            }
        }

        function showOverlay() {
            winOverlay.classList.remove('hidden');
            setTimeout(() => {
                winOverlay.style.opacity = '1';
            }, 10);
        }

        function resetGame() {
            winOverlay.style.opacity = '0';
            setTimeout(() => {
                winOverlay.classList.add('hidden');
                initGame();
            }, 500);
        }

        resetBtn.addEventListener('click', initGame);

        // Initial Load
        window.onload = initGame;
    </script>
</body>
</html>
