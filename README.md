<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hamyor Mini App</title>
    <!-- Telegram SDK -->
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--tg-theme-bg-color);
            color: var(--tg-theme-text-color);
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .header {
            text-align: center;
            margin-bottom: 20px;
        }
        .header h1 {
            color: #24A1DE; 
            font-size: 24px;
            margin-bottom: 5px;
        }
        .categories {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            width: 100%;
            max-width: 400px;
        }
        .category-card {
            background-color: var(--tg-theme-secondary-bg-color);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            cursor: pointer;
            transition: transform 0.2s;
            border: 1px solid rgba(0,0,0,0.1);
        }
        .category-card:active {
            transform: scale(0.95);
        }
        .category-card span {
            display: block;
            font-size: 30px;
            margin-bottom: 10px;
        }
        .category-card p {
            margin: 0;
            font-weight: 500;
        }
        .footer {
            margin-top: 30px;
            font-size: 12px;
            opacity: 0.7;
        }
    </style>
</head>
<body>

    <div class="header">
        <h1 style="margin: 0; color: #24A1DE;">Hamyor</h1>
        <p>O'zbekistondagi eng yaxshi ustalarni toping</p>
    </div>

    <div class="categories">
        <div class="category-card" onclick="selectCategory('Santexnik')">
            <span>🚰</span>
            <p>Santexnik</p>
        </div>
        <div class="category-card" onclick="selectCategory('Elektrik')">
            <span>⚡</span>
            <p>Elektrik</p>
        </div>
        <div class="category-card" onclick="selectCategory('Repetitor')">
            <span>📚</span>
            <p>Repetitor</p>
        </div>
        <div class="category-card" onclick="selectCategory('Huquqshunos')">
            <span>⚖️</span>
            <p>Huquqshunos</p>
        </div>
    </div>

    <div class="footer">© 2026 Hamyor Servis</div>

    <script>
        // Инициализация Telegram WebApp
        const tg = window.Telegram.WebApp;
        tg.expand(); 

        function selectCategory(category) {
            // 1. Отправляем данные обратно боту (это закроет приложение и отправит сообщение в чат)
            tg.sendData(`Search:${category}`);
            
            // 2. Показываем уведомление (опционально)
            tg.showAlert(`Siz ${category} yo'nalishini tanladingiz. Hozir biz sizga eng yaxshi ustalarni topamiz!`);
        }
    </script>
</body>
</html># hamyor
