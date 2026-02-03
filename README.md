<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mochi Bites Premium</title>
    <style>
        /* CSS - Desain Minimalis & Pastel */
        :root {
            --primary: #ffb7c5;
            --secondary: #fce4ec;
            --text: #4a4a4a;
            --white: #ffffff;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            background-color: var(--secondary);
            color: var(--text);
            line-height: 1.6;
        }

        header {
            background-color: var(--white);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo { font-weight: bold; font-size: 1.5rem; color: #d81b60; }

        .lang-switcher button {
            background: #eee;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 5px;
            margin-left: 5px;
            transition: 0.3s;
        }

        .lang-switcher button.active {
            background: var(--primary);
            color: white;
        }

        .hero {
            text-align: center;
            padding: 4rem 10%;
            background: linear-gradient(rgba(255,255,255,0.7), rgba(255,255,255,0.7)), url('hero-bg.jpg'); /* Opsional */
            background-size: cover;
        }

        .menu-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            padding: 2rem 10%;
        }

        .card {
            background: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            transition: transform 0.3s;
            text-align: center;
            padding-bottom: 1.5rem;
        }

        .card:hover { transform: translateY(-10px); }

        .card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        .card h3 { margin: 1rem 0 0.5rem; }

        .btn-order {
            display: inline-block;
            background-color: #25D366;
            color: white;
            padding: 10px 25px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            margin-top: 1rem;
            transition: 0.3s;
        }

        .btn-order:hover { background-color: #128C7E; transform: scale(1.05); }

        footer { text-align: center; padding: 2rem; font-size: 0.9rem; opacity: 0.7; }
    </style>
</head>
<body>

<header>
    <div class="logo">🍡 Mochi Bites</div>
    <div class="lang-switcher">
        <button onclick="changeLang('id')" id="btn-id" class="active">ID</button>
        <button onclick="changeLang('th')" id="btn-th">TH</button>
        <button onclick="changeLang('ko')" id="btn-ko">KO</button>
    </div>
</header>

<section class="hero">
    <h1 id="hero-title">Mochi Bites Lembut & Lumer</h1>
    <p id="hero-desc">Dibuat dengan cinta dan bahan premium terbaik.</p>
</section>

<div class="menu-container">
    <div class="card">
        <img src="coklat.jpg" alt="Mochi Chocolate">
        <h3 id="p1-title">Cokelat Belgia</h3>
        <p id="p1-desc">Isian cokelat lumer yang melimpah.</p>
        <a href="https://wa.me/6285778508125?text=Halo,%20saya%20mau%20pesan%20Mochi%20Cokelat" class="btn-order" id="p1-btn">Pesan via WA</a>
    </div>

    <div class="card">
        <img src="matcha.jpg" alt="Mochi Matcha">
        <h3 id="p2-title">Matcha Kyoto</h3>
        <p id="p2-desc">Rasa teh hijau autentik yang menenangkan.</p>
        <a href="https://wa.me/6285778508125?text=Halo,%20saya%20mau%20pesan%20Mochi%20Matcha" class="btn-order" id="p2-btn">Pesan via WA</a>
    </div>

    <div class="card">
        <img src="strawberry.jpg" alt="Mochi Strawberry">
        <h3 id="p3-title">Strawberry Cheese</h3>
        <p id="p3-desc">Perpaduan asam segar dan keju gurih.</p>
        <a href="https://wa.me/6285778508125?text=Halo,%20saya%20mau%20pesan%20Mochi%20Strawberry" class="btn-order" id="p3-btn">Pesan via WA</a>
    </div>
</div>

<footer>
    &copy; 2024 Mochi Bites Premium - Freshly Made Everyday
</footer>

<script>
    // Data Bahasa
    const translations = {
        id: {
            heroTitle: "Mochi Bites Lembut & Lumer",
            heroDesc: "Dibuat dengan cinta dan bahan premium terbaik.",
            p1Title: "Cokelat Belgia", p1Desc: "Isian cokelat lumer yang melimpah.",
            p2Title: "Matcha Kyoto", p2Desc: "Rasa teh hijau autentik yang menenangkan.",
            p3Title: "Strawberry Cheese", p3Desc: "Perpaduan asam segar dan keju gurih.",
            btn: "Pesan via WA"
        },
        th: {
            heroTitle: "โมจิไบทส์ นุ่มละมุน",
            heroDesc: "ทำด้วยความรักและวัตถุดิบระดับพรีเมียมที่ดีที่สุด",
            p1Title: "เบลเยียมช็อกโกแลต", p1Desc: "ไส้ช็อกโกแลตเยิ้มๆ สุดฟิน",
            p2Title: "เกียวโตมัทฉะ", p2Desc: "รสชาติชาเขียวแท้จากญี่ปุ่น",
            p3Title: "สตรอว์เบอร์รี่ชีส", p3Desc: "ความลงตัวของรสเปรี้ยวหวานและชีส",
            btn: "สั่งซื้อผ่าน WA"
        },
        ko: {
            heroTitle: "부드럽고 쫄깃한 모찌 바이트",
            heroDesc: "최고의 프리미엄 재료로 정성을 다해 만듭니다.",
            p1Title: "벨기에 초콜릿", p1Desc: "입안 가득 퍼지는 달콤한 초코",
            p2Title: "교토 말차", p2Desc: "진하고 깊은 풍미의 오리지널 말차",
            p3Title: "딸기 치즈", p3Desc: "상큼한 딸기와 고소한 치즈의 조화",
            btn: "WA로 주문하기"
        }
    };

    function changeLang(lang) {
        // Update Teks
        document.getElementById('hero-title').innerText = translations[lang].heroTitle;
        document.getElementById('hero-desc').innerText = translations[lang].heroDesc;
        
        document.getElementById('p1-title').innerText = translations[lang].p1Title;
        document.getElementById('p1-desc').innerText = translations[lang].p1Desc;
        document.getElementById('p1-btn').innerText = translations[lang].btn;

        document.getElementById('p2-title').innerText = translations[lang].p2Title;
        document.getElementById('p2-desc').innerText = translations[lang].p2Desc;
        document.getElementById('p2-btn').innerText = translations[lang].btn;

        document.getElementById('p3-title').innerText = translations[lang].p3Title;
        document.getElementById('p3-desc').innerText = translations[lang].p3Desc;
        document.getElementById('p3-btn').innerText = translations[lang].btn;

        // Update Button Style
        document.querySelectorAll('.lang-switcher button').forEach(btn => btn.classList.remove('active'));
        document.getElementById('btn-' + lang).classList.add('active');
    }
</script>

</body>
</html>
