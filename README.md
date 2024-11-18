<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pinkman - Kripto Para Borsası</title>
    <link rel="stylesheet" href="style.css">
    <!-- Chart.js kütüphanesini ekliyoruz -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body>
    <header>
        <div class="logo">
            <h1>Pinkman</h1>
        </div>
        <nav>
            <ul>
                <li><a href="#">Anasayfa</a></li>
                <li><a href="#">Piyasalar</a></li>
                <li><a href="#">Cüzdan</a></li>
                <li><a href="#">Al-Sat</a></li>
                <li><a href="#">Hesap</a></li>
                <li><a href="#">Bize Katıl</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- Banner -->
        <section class="banner">
            <h2>Kripto Para Dünyasına Hoş Geldiniz</h2>
            <p>Pinkman ile kolayca al-sat yapın, en iyi fiyatları takip edin!</p>
            <button onclick="location.href='#'">Hesap Oluştur</button>
        </section>

        <!-- Piyasa Durumu -->
        <section class="market-overview">
            <h2>Piyasa Durumu</h2>
            <div class="market-list">
                <div class="market-item">
                    <h3>Bitcoin (BTC)</h3>
                    <p id="btc-price">Fiyat: $45,000</p>
                    <p id="btc-change">24h Değişim: +3.5%</p>
                </div>
                <div class="market-item">
                    <h3>Ethereum (ETH)</h3>
                    <p id="eth-price">Fiyat: $3,000</p>
                    <p id="eth-change">24h Değişim: +2.1%</p>
                </div>
                <div class="market-item">
                    <h3>Binance Coin (BNB)</h3>
                    <p id="bnb-price">Fiyat: $350</p>
                    <p id="bnb-change">24h Değişim: -1.2%</p>
                </div>
            </div>
        </section>

        <!-- Kripto Para Grafik -->
        <section class="chart-section">
            <h2>Bitcoin (BTC) Fiyat Grafiği</h2>
            <canvas id="btcChart"></canvas>
        </section>
 

        <!-- Al/Sat İşlemleri -->
        <section class="trade-section">
            <h2>Al/Sat Yap</h2>
            <form id="trade-form">
                <label for="coin">Kripto Para Seçin:</label>
                <select id="coin" name="coin">
                    <option value="BTC">Bitcoin (BTC)</option>
                    <option value="ETH">Ethereum (ETH)</option>
                    <option value="BNB">Binance Coin (BNB)</option>
                </select>
                <label for="amount">Miktar:</label>
                <input type="number" id="amount" name="amount" min="0.01" step="0.01" required>
                <button type="submit">Al/Sat İşlemi Yap</button>
            </form>
            <p id="trade-result"></p>
        </section>

        <!-- Son Haberler -->
        <section class="news">
            <h2>Son Haberler</h2>
            <ul>
                <li><a href="#">Bitcoin 50.000 USD'yi geçti!</a></li>
                <li><a href="#">Ethereum 2.0 Güncellemesi Yayınlandı</a></li>
                <li><a href="#">Binance Coin Yükseliyor, Yeni Yatırımcılar Çekiyor</a></li>
            </ul>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="footer-links">
            <a href="#">Hakkımızda</a>
            <a href="#">İletişim</a>
            <a href="#">Gizlilik Politikası</a>
            <a href="#">Şartlar ve Koşullar</a>
        </div>
        <div class="social-media">
            <a href="#">Facebook</a>
            <a href="#">Twitter</a>
            <a href="#">Instagram</a>
        </div>
        <p>&copy; 2024 Binance. Tüm hakları saklıdır.</p>
    </footer>

    <script src="script.js"></script>
</body>
<head> 
<style>

/* Genel Ayarlar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    background-color: #f4f4f4;
}

/* Header */
header {
    background-color: #131b28;
    color: white;
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 1000;
}

header .logo h1 {
    font-size: 28px;
    font-weight: bold;
}

header nav ul {
    list-style: none;
    display: flex;
}

header nav ul li {
    margin: 0 15px;
}

header nav ul li a {
    color: white;
    text-decoration: none;
    font-size: 16px;
}

header nav ul li a:hover {
    color: #f0b90b;
}

/* Banner */
.banner {
    background-color: #1a2332;
    color: white;
    text-align: center;
    padding: 50px 20px;
    border-radius: 8px;
    margin-bottom: 40px;
}

.banner h2 {
    font-size: 36px;
    margin-bottom: 10px;
}

.banner p {
    font-size: 18px;
    margin-bottom: 20px;
}

.banner button {
    background-color: #f0b90b;
    color: black;
    font-size: 18px;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
}

.banner button:hover {
    background-color: #d49e06;
}

/* Piyasa Durumu */
.market-overview {
    margin-top: 40px;
}

.market-overview h2 {
    font-size: 28px;
    margin-bottom: 20px;
}

.market-list {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}

.market-item {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    width: 30%;
    text-align: center;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 20px;
}

.market-item h3 {
    font-size: 22px;
    margin-bottom: 10px;
}

.market-item p {
    font-size: 16px;
}

.market-item p span {
    font-weight: bold;
}

/* Grafik */
.chart-section {
    background-color: #fff;
    padding: 30px;
    margin-top: 40px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.chart-section h2 {
    font-size: 28px;
    margin-bottom: 20px;
}

#btcChart {
    width: 100%;
    height: 300px;
}

/* Al/Sat Form */
.trade-section {
    background-color: #fff;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    margin-top: 40px;
}

.trade-section h2 {
    font-size: 28px;
    margin-bottom: 20px;
}

.trade-section form {
    display: flex;
    flex-direction: column;
}

.trade-section label {
    font-size: 16px;
    margin-bottom: 5px;
}

.trade-section input, .trade-section select {
    padding: 10px;
    margin-bottom: 20px;
    font-size: 16px;
    border-radius: 5px;
    border: 1px solid #ccc;
}

.trade-section button {
    background-color: #f0b90b;
    color: black;
    font-size: 18px;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
}

.trade-section button:hover {
    background-color: #d49e06;
}

/* Haberler */
.news {
    margin-top: 40px;
}

.news h2 {
    font-size: 28px;
    margin-bottom: 20px;
}

.news ul {
    list-style: none;
}

.news ul li {
    margin-bottom: 10px;
}

.news ul li a {
    color: #333;
    text-decoration: none;
    font-size: 16px;
}

.news ul li a:hover {
    color: #f0b90b;
}

/* Footer */
footer {
    background-color: #131b28;
    color: white;
    text-align: center;
    padding: 20px;
    margin-top: 40px;
}

.footer-links, .social-media {
    margin-bottom: 20px;
}

.footer-links a, .social-media a {
    color: white;
    text-decoration: none;
    margin: 0 10px;
}

.footer-links a:hover, .social-media a:hover {
    color: #f0b90b;
}

/* Responsive Tasarım */
@media (max-width: 768px) {
    .market-list {
        flex-direction: column;
        align-items: center;
    }

    .market-item {
        width: 80%;
        margin-bottom: 20px;
    }

    .banner h2 {
        font-size: 28px;
    }

    .trade-section {
        width: 100%;
    }

    .chart-section {
        padding: 20px;
    }
}
</style> 
</head>
<script>
// Kripto para fiyatlarını güncelleyen fonksiyon
function updatePrices() {
    const btcPrice = (45000 + (Math.random() * 2000 - 1000)).toFixed(2);
    const ethPrice = (3000 + (Math.random() * 100 - 50)).toFixed(2);
    const bnbPrice = (350 + (Math.random() * 20 - 10)).toFixed(2);
    
    const btcChange = ((Math.random() * 6 - 3).toFixed(2)) + "%";
    const ethChange = ((Math.random() * 4 - 2).toFixed(2)) + "%";
    const bnbChange = ((Math.random() * 2 - 1).toFixed(2)) + "%";
    
    document.getElementById("btc-price").textContent = Fiyat: $${btcPrice};
    document.getElementById("btc-change").textContent = 24h Değişim: ${btcChange};

    document.getElementById("eth-price").textContent = Fiyat: $${ethPrice};
    document.getElementById("eth-change").textContent = 24h Değişim: ${ethChange};

    document.getElementById("bnb-price").textContent = Fiyat: $${bnbPrice};
    document.getElementById("bnb-change").textContent = 24h Değişim: ${bnbChange};
}

// Al/Sat işlemi simülasyonu
document.getElementById("trade-form").addEventListener("submit", function(e) {
    e.preventDefault();

    const coin = document.getElementById("coin").value;
    const amount = parseFloat(document.getElementById("amount").value);

    const prices = {
        BTC: 45000,
        ETH: 3000,
        BNB: 350
    };

    if (isNaN(amount) || amount <= 0) {
        alert("Lütfen geçerli bir miktar girin!");
        return;
    }

    const total = (prices[coin] * amount).toFixed(2);
    document.getElementById("trade-result").textContent = Seçilen Kripto Para: ${coin} | Miktar: ${amount} | Toplam: $${total};
});

// Bitcoin için basit bir fiyat grafiği oluşturuyoruz
var ctx = document.getElementById('btcChart').getContext('2d');
var btcChart = new Chart(ctx, {
    type: 'line',
    data: {
        labels: ['1 Gün', '2 Gün', '3 Gün', '4 Gün', '5 Gün', '6 Gün', '7 Gün'],
        datasets: [{
            label: 'Bitcoin (BTC) Fiyatı',
            data: [45000, 46000, 44500, 44000, 45000, 45500, 46000],
            borderColor: 'rgba(255, 99, 132, 1)',
            fill: false
        }]
    }
});

// Sayfa yüklendiğinde fiyatları güncelle
window.onload = updatePrices;

// Fiyatları her 10 saniyede bir güncelle
setInterval(updatePrices, 10000);
</script>
</html>
# kadir
