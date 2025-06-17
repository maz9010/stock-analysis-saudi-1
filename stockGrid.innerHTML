<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام التحليل الفني الشامل - الأسهم السعودية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #1a237e;
            --secondary: #4a148c;
            --accent: #00bcd4;
            --success: #4caf50;
            --warning: #ff9800;
            --danger: #f44336;
            --dark: #121212;
            --light: #f5f5f5;
            --text: #333;
            --text-light: #777;
        }
        
        body {
            background: linear-gradient(135deg, #0c1e3e, #1a237e);
            color: var(--light);
            min-height: 100vh;
            line-height: 1.6;
            padding: 20px;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo i {
            font-size: 2.5rem;
            color: var(--accent);
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo span {
            color: var(--accent);
        }
        
        .nav-links {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 8px 15px;
            border-radius: 30px;
            font-size: 0.9rem;
        }
        
        .nav-links a:hover, .nav-links a.active {
            background: rgba(0, 188, 212, 0.2);
            color: var(--accent);
        }
        
        .dashboard {
            display: grid;
            grid-template-columns: 1fr;
            gap: 25px;
            margin-bottom: 30px;
        }
        
        .card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            flex-wrap: wrap;
            gap: 15px;
        }
        
        .card-title {
            font-size: 1.4rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card-title i {
            color: var(--accent);
        }
        
        .stock-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
            gap: 15px;
        }
        
        .stock-card {
            background: rgba(0, 30, 60, 0.7);
            border-radius: 12px;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .stock-card:hover {
            background: rgba(0, 80, 120, 0.7);
            border-color: var(--accent);
        }
        
        .stock-card.selected {
            background: rgba(0, 150, 200, 0.7);
            border-color: var(--accent);
        }
        
        .stock-symbol {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .stock-name {
            font-size: 0.85rem;
            opacity: 0.8;
            margin-bottom: 10px;
        }
        
        .stock-price {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 5px;
            color: var(--accent);
        }
        
        .stock-change {
            font-size: 0.85rem;
            border-radius: 20px;
            padding: 3px 10px;
            display: inline-block;
        }
        
        .positive {
            background: rgba(76, 175, 80, 0.2);
            color: #76ff03;
        }
        
        .negative {
            background: rgba(244, 67, 54, 0.2);
            color: #ff5252;
        }
        
        .chart-container {
            height: 300px;
            position: relative;
            margin: 20px 0;
        }
        
        .indicator-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }
        
        .indicator {
            background: rgba(0, 60, 100, 0.5);
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .indicator-name {
            font-size: 0.85rem;
            opacity: 0.8;
            margin-bottom: 8px;
        }
        
        .indicator-value {
            font-size: 1.1rem;
            font-weight: bold;
        }
        
        .recommendation {
            text-align: center;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            font-size: 1.1rem;
            font-weight: bold;
            background: rgba(0, 100, 100, 0.3);
        }
        
        .buy {
            background: rgba(46, 125, 50, 0.3);
            color: #76ff03;
            border: 2px solid #76ff03;
        }
        
        .sell {
            background: rgba(198, 40, 40, 0.3);
            color: #ff5252;
            border: 2px solid #ff5252;
        }
        
        .hold {
            background: rgba(33, 150, 243, 0.3);
            color: #82b1ff;
            border: 2px solid #82b1ff;
        }
        
        .news-container {
            max-height: 300px;
            overflow-y: auto;
            padding-right: 10px;
        }
        
        .news-item {
            background: rgba(0, 40, 80, 0.5);
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .news-title {
            font-weight: bold;
            margin-bottom: 5px;
            color: var(--accent);
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1.05rem;
        }
        
        .news-time {
            font-size: 0.8rem;
            opacity: 0.7;
            margin-bottom: 10px;
            display: block;
        }
        
        .news-content {
            font-size: 0.9rem;
            line-height: 1.5;
        }
        
        .btn {
            background: linear-gradient(45deg, var(--secondary), var(--primary));
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 30px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
        }
        
        .btn:active {
            transform: translateY(0);
        }
        
        .btn i {
            font-size: 1.1rem;
        }
        
        .footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.85rem;
            opacity: 0.7;
        }
        
        /* Responsive design */
        @media (min-width: 768px) {
            .dashboard {
                grid-template-columns: 1fr 1fr;
            }
            
            .card:nth-child(1) {
                grid-column: 1 / 3;
            }
            
            .card:nth-child(4) {
                grid-column: 1 / 3;
            }
        }
        
        @media (min-width: 992px) {
            .dashboard {
                grid-template-columns: 1fr 1fr 1fr;
            }
            
            .card:nth-child(1) {
                grid-column: 1 / 4;
            }
            
            .card:nth-child(4) {
                grid-column: 1 / 4;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-chart-line"></i>
                <h1>نظام <span>التحليل الفني</span> الشامل</h1>
            </div>
            <div class="nav-links">
                <a href="#" class="active"><i class="fas fa-home"></i> الرئيسية</a>
                <a href="#"><i class="fas fa-chart-bar"></i> التحليل الفني</a>
                <a href="#"><i class="fas fa-newspaper"></i> الأخبار والإشاعات</a>
                <a href="#"><i class="fas fa-cog"></i> الإعدادات</a>
            </div>
        </header>
        
        <div class="dashboard">
            <div class="card">
                <div class="card-header">
                    <h2 class="card-title"><i class="fas fa-coins"></i> الأسهم السعودية</h2>
                    <div class="controls">
                        <button class="btn" id="refreshBtn"><i class="fas fa-sync"></i> تحديث</button>
                    </div>
                </div>
                <div class="stock-grid" id="stockGrid">
                    <!-- Stocks will be populated by JavaScript -->
                </div>
            </div>
            
            <div class="card">
                <div class="card-header">
                    <h2 class="card-title"><i class="fas fa-chart-area"></i> التحليل الفني</h2>
                    <div class="controls">
                        <select id="timeFrame" class="btn">
                            <option value="1d">يوم واحد</option>
                            <option value="1w">أسبوع</option>
                            <option value="1m">شهر</option>
                            <option value="3m">3 أشهر</option>
                            <option value="1y" selected>سنة</option>
                        </select>
                    </div>
                </div>
                <div class="chart-container">
                    <canvas id="stockChart"></canvas>
                </div>
                <div class="indicator-grid" id="indicators">
                    <!-- Indicators will be populated by JavaScript -->
                </div>
                <div class="recommendation hold" id="recommendation">
                    <i class="fas fa-info-circle"></i> اختر سهمًا لرؤية التوصية
                </div>
            </div>
            
            <div class="card">
                <div class="card-header">
                    <h2 class="card-title"><i class="fas fa-bullhorn"></i> أخبار وإشاعات السوق</h2>
                    <div class="controls">
                        <button class="btn" id="refreshNews"><i class="fas fa-sync"></i> تحديث</button>
                    </div>
                </div>
                <div class="news-container" id="newsContainer">
                    <!-- News items will be populated by JavaScript -->
                </div>
            </div>
            
            <div class="card">
                <div class="card-header">
                    <h2 class="card-title"><i class="fas fa-robot"></i> تحليل الذكاء الاصطناعي</h2>
                </div>
                <div class="chart-container">
                    <canvas id="forecastChart"></canvas>
                </div>
                <div style="text-align: center; margin-top: 20px;">
                    <button class="btn" id="analyzeBtn"><i class="fas fa-brain"></i> بدء التحليل المتقدم</button>
                </div>
            </div>
        </div>
        
        <div class="footer">
            نظام السعودي للتحليل الفني - الإصدار 2.5 © 2023 | تم التطوير باستخدام أحدث تقنيات الذكاء الاصطناعي
        </div>
    </div>

    <script>
        // Sample stock data for Saudi market
        const saudiStocks = [
            { symbol: "2222", name: "أرامكو السعودية", price: 32.75, change: 0.85, sector: "طاقة" },
            { symbol: "1211", name: "معادن", price: 43.20, change: -1.25, sector: "تعدين" },
            { symbol: "7010", name: "الاتصالات السعودية", price: 41.10, change: 0.42, sector: "اتصالات" },
            { symbol: "1120", name: "الراجحي", price: 73.50, change: 0.65, sector: "بنوك" },
            { symbol: "4002", name: "سدايا", price: 118.00, change: -0.85, sector: "تأمين" },
            { symbol: "4030", name: "الباحة", price: 28.90, change: 1.32, sector: "تطوير عقاري" },
            { symbol: "4200", name: "الدريس", price: 87.25, change: 0.25, sector: "خدمات" },
            { symbol: "4260", name: "بديكو", price: 34.80, change: -0.50, sector: "صناعة" }
        ];
        
        // Technical indicators
        const indicators = [
            { name: "RSI (14)", value: 56.8, optimal: "30-70", trend: "متوسط" },
            { name: "MACD", value: 1.25, optimal: "Signal crossover", trend: "إيجابي" },
            { name: "EMA (50)", value: 32.10, optimal: "السعر > المتوسط", trend: "إيجابي" },
            { name: "SMA (200)", value: 30.85, optimal: "السعر > المتوسط", trend: "إيجابي" },
            { name: "بولينجر باند", value: "32.20-34.80", optimal: "السعر في النطاق", trend: "محايد" },
            { name: "حجم التداول", value: "4.2M", optimal: "أعلى من المتوسط", trend: "إيجابي" },
            { name: "دعم قوي", value: 31.50, optimal: "مستوى دعم", trend: "إيجابي" },
            { name: "مقاومة", value: 33.80, optimal: "مستوى مقاومة", trend: "سلبي" }
        ];
        
        // Market news and rumors
        const marketNews = [
            {
                title: "توقعات بارتفاع أرباح أرامكو بنهاية الربع",
                time: "قبل 2 ساعة",
                content: "توقع محللون ارتفاع أرباح أرامكو السعودية بنسبة 8% مع نهاية الربع الحالي بسبب ارتفاع أسعار النفط العالمية. وقد أدت هذه التوقعات إلى زيادة الطلب على السهم في السوق المحلية."
            },
            {
                title: "إشاعات عن استحواذ جديد في قطاع الاتصالات",
                time: "قبل 4 ساعات",
                content: "تداولت وسائل التواصل الاجتماعي إشاعات عن استحواذ محتمل في قطاع الاتصالات السعودي مما أدى إلى ارتفاع أسهم القطاع بنسبة 2.3%. المصادر الرسمية لم تؤكد أو تنفي هذه الإشاعات حتى الآن."
            },
            {
                title: "بنوك سعودية تعلن عن خطط توسع جديدة",
                time: "قبل 6 ساعات",
                content: "أعلنت عدة بنوك سعودية كبرى عن خطط توسع في خدماتها الرقمية وفتح فروع جديدة في جميع أنحاء المملكة. من المتوقع أن تؤدي هذه الخطط إلى زيادة حصصها السوقية بنسبة 15% خلال العام القادم."
            },
            {
                title: "تقرير: نمو قطاع التجزئة السعودي بنسبة 12%",
                time: "أمس",
                content: "أظهر تقرير اقتصادي نمو قطاع التجزئة السعودي بنسبة 12% خلال الربع الماضي، مما أدى إلى ارتفاع أسهم شركات التجزئة في السوق المحلية. التقرير يرجع هذا النمو إلى زيادة الإنفاق الاستهلاكي خلال موسم الصيف."
            },
            {
                title: "توقعات بانتعاش قطاع السياحة السعودي",
                time: "قبل يومين",
                content: "توقع خبراء السياحة نموًا قويًا في قطاع السياحة السعودي خلال العام القادم بنسبة تصل إلى 25%، مما قد ينعكس إيجابًا على أسهم شركات السياحة والفنادق في السوق المحلية."
            }
        ];
        
        // Initialize the app
        function initApp() {
            renderStocks();
            renderIndicators();
            renderNews();
            setupChart();
            setupForecastChart();
            setupEventListeners();
            
            // Select the first stock by default
            if (saudiStocks.length > 0) {
                selectStock(saudiStocks[0]);
            }
        }
        
        // Render stock cards
        function renderStocks() {
            const stockGrid = document.getElementById('stockGrid');
            stockGrid.innerHTML = '';
            
            saudiStocks.forEach(stock => {
                const changeClass = stock.change >= 0 ? 'positive' : 'negative';
                const changeSign = stock.change >= 0 ? '+' : '';
                
                const stockCard = document.createElement('div');
                stockCard.className = 'stock-card';
                stockCard.innerHTML = `
                    <div class="stock-symbol">${stock.symbol}</div>
                    <div class="stock-name">${stock.name}</div>
                    <div class="stock-price">${stock.price.toFixed(2)} ر.س</div>
                    <div class="stock-change ${changeClass}">${changeSign}${stock.change.toFixed(2)}%</div>
                    <div class="stock-sector" style="margin-top: 8px; font-size: 0.8rem; opacity: 0.7;">${stock.sector}</div>
                `;
                
                stockCard.addEventListener('click', () => selectStock(stock));
                stockGrid.appendChild(stockCard);
            });
        }
        
        // Render technical indicators
        function renderIndicators() {
            const indicatorsContainer = document.getElementById('indicators');
            indicatorsContainer.innerHTML = '';
            
            indicators.forEach(indicator => {
                const indicatorElement = document.createElement('div');
                indicatorElement.className = 'indicator';
                indicatorElement.innerHTML = `
                    <div class="indicator-name">${indicator.name}</div>
                    <div class="indicator-value">${indicator.value}</div>
                    <div class="indicator-optimal">${indicator.optimal}</div>
                `;
                indicatorsContainer.appendChild(indicatorElement);
            });
        }
        
        // Render market news
        function renderNews() {
            const newsContainer = document.getElementById('newsContainer');
            newsContainer.innerHTML = '';
            
            marketNews.forEach(news => {
                const newsElement = document.createElement('div');
                newsElement.className = 'news-item';
                newsElement.innerHTML = `
                    <div class="news-title"><i class="fas fa-bullhorn"></i> ${news.title}</div>
                    <span class="news-time">${news.time}</span>
                    <div class="news-content">${news.content}</div>
                `;
                newsContainer.appendChild(newsElement);
            });
        }
        
        // Setup stock chart
        function setupChart() {
            const ctx = document.getElementById('stockChart').getContext('2d');
            
            // Sample chart data
            const labels = ['يناير', 'فبراير', 'مارس', 'أبريل', 'مايو', 'يونيو', 
                           'يوليو', 'أغسط
