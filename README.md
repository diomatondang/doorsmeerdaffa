<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Azaria Rent Car - Rental Mobil Nyaman & Terpercaya</title>
    
    <style>
        /* RESET DASAR */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Ganti Font */
        }

        body {
            line-height: 1.6;
            background-color: #f4f4f4; 
            color: #333;
        }

        /* WARNA PALET */
        :root {
            --primary-color: #0056b3; /* Biru terang */
            --secondary-color: #ff9900; /* Oranye */
            --text-dark: #333;
            --bg-light: #ffffff;
        }

        /* 1. HEADER & NAVIGASI */
        header {
            background-color: var(--primary-color);
            color: var(--bg-light);
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15); /* Bayangan yang lebih tegas */
            position: sticky; /* Sticky header agar navigasi selalu terlihat */
            top: 0;
            z-index: 1000;
        }

        header h1 {
            font-size: 26px;
            letter-spacing: 1.5px;
        }

        nav ul {
            list-style: none;
            display: flex;
        }

        nav ul li a {
            color: var(--bg-light);
            text-decoration: none;
            padding: 10px 18px;
            transition: background-color 0.3s, color 0.3s;
            font-weight: 500;
        }

        nav ul li a:hover {
            background-color: var(--secondary-color); /* Hover ke warna oranye */
            color: var(--text-dark);
            border-radius: 4px;
        }

        /* 2. HERO SECTION & FORM PENCARIAN */
        .hero {
            background: url('https://picsum.photos/1600/600/?car,road') no-repeat center center/cover; 
            color: var(--bg-light);
            text-align: center;
            padding: 180px 5% 50px;
            position: relative;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 0, 0.6); /* Overlay lebih gelap */
            z-index: 1;
        }
        
        .hero-content, .search-form {
            position: relative;
            z-index: 2;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto 30px;
        }

        .hero h2 {
            font-size: 52px;
            margin-bottom: 15px;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.9);
        }

        .hero p {
            font-size: 22px;
            margin-bottom: 30px;
        }

        /* Tombol Aksi Utama (CTA) */
        .cta-button {
            display: inline-block;
            background-color: var(--secondary-color);
            color: var(--text-dark);
            padding: 15px 40px;
            text-decoration: none;
            font-weight: bold;
            border-radius: 50px; /* Lebih bulat */
            transition: background-color 0.3s, transform 0.2s;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            text-transform: uppercase;
        }

        .cta-button:hover {
            background-color: #e68a00; 
            transform: translateY(-2px); /* Efek mengangkat */
        }

        /* Form Pencarian */
        .search-form {
            background-color: var(--bg-light);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2); /* Bayangan lebih dramatis */
            max-width: 90%;
            margin: 0 auto;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 20px;
            transform: translateY(50%); /* Geser ke atas (menimpa konten di bawahnya) */
        }
        
        /* Mengatur tata letak agar form terpusat dan memiliki ruang */
        main {
            padding-top: 50px; /* Kompensasi untuk sticky header */
        }
        
        /* Mengatur agar konten berikutnya tidak bertabrakan dengan form */
        .features {
            padding-top: 150px; /* Beri ruang ekstra di atas section features */
        }


        .search-form h3 {
            width: 100%;
            text-align: left;
            color: var(--primary-color);
            margin-bottom: 15px;
            font-size: 20px;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
        }

        .search-form div {
            flex: 1;
            min-width: 200px; 
        }

        .search-form label {
            display: block;
            font-weight: bold;
            margin-bottom: 5px;
            color: var(--text-dark);
        }

        .search-form input[type="text"],
        .search-form input[type="date"] {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-size: 16px;
        }

        .search-form button {
            background-color: var(--primary-color);
            color: var(--bg-light);
            border: none;
            padding: 12px 30px;
            cursor: pointer;
            border-radius: 6px;
            transition: background-color 0.3s;
            font-weight: bold;
            flex: 0 0 auto; 
            align-self: flex-end; 
        }

        .search-form button:hover {
            background-color: #004494;
        }

        /* 3. KEUNGGULAN KAMI (FEATURES) */
        .features {
            padding: 80px 5%; /* Padding lebih besar */
            text-align: center;
            background-color: #f9f9f9;
        }

        .features h2 {
            margin-bottom: 50px;
            color: var(--text-dark);
            font-size: 32px;
            position: relative;
        }
        
        .features h2::after {
            content: '';
            display: block;
            width: 60px;
            height: 3px;
            background-color: var(--secondary-color);
            margin: 10px auto 0;
        }

        .feature-list {
            display: flex;
            justify-content: space-around;
            gap: 30px;
        }

        .feature-item {
            flex: 1;
            padding: 30px;
            border-radius: 10px;
            background-color: var(--bg-light);
            transition: transform 0.4s, box-shadow 0.4s;
            border-top: 5px solid var(--secondary-color); /* Garis tegas di atas */
        }

        .feature-item:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .feature-item h3 {
            margin: 15px 0;
            color: var(--primary-color);
        }
        
        .feature-item p {
            color: #666;
        }

        /* 4. MOBIL POPULER */
        .popular-cars {
            padding: 60px 5%;
            background-color: var(--bg-light);
            text-align: center;
        }

        .popular-cars h2 {
            margin-bottom: 50px;
            color: var(--primary-color);
            font-size: 32px;
        }

        .car-list {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-bottom: 40px;
        }

        .car-card {
            border: 1px solid #eee;
            border-radius: 12px;
            width: 320px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            text-align: left;
            background-color: #fff;
            overflow: hidden; /* Pastikan gambar tidak keluar dari radius */
            transition: box-shadow 0.3s;
        }

        .car-card:hover {
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }
        
        .car-image {
            width: 100%;
            height: 200px;
            background-color: #ccc; /* Placeholder warna jika gambar belum ada */
            text-align: center;
            line-height: 200px;
            color: #666;
            font-size: 14px;
        }
        
        .car-details {
            padding: 20px;
        }

        .car-details h3 {
            color: var(--primary-color);
            margin: 5px 0;
            font-size: 22px;
        }
        
        .car-details p {
            margin-bottom: 10px;
            color: #555;
            font-size: 14px;
        }

        .car-details .price {
            font-size: 20px;
            margin: 15px 0;
            font-weight: normal;
        }

        .car-details .price span {
            font-weight: bold;
            color: var(--secondary-color);
            font-size: 28px;
        }

        .detail-button {
            display: block;
            text-align: center;
            background-color: var(--primary-color);
            color: var(--bg-light);
            padding: 12px;
            text-decoration: none;
            border-radius: 6px;
            transition: background-color 0.3s;
            margin-top: 15px;
        }

        .detail-button:hover {
            background-color: #004494;
        }

        .cta-button-secondary {
            margin-top: 20px;
            background-color: var(--text-dark);
            color: var(--bg-light);
            padding: 12px 30px;
            border-radius: 4px;
        }

        .cta-button-secondary:hover {
            background-color: #555;
        }

        /* 5. FOOTER */
        footer {
            background-color: var(--text-dark);
            color: #ccc;
            text-align: center;
            padding: 30px 5%;
            font-size: 14px;
            margin-top: 100px; /* Mendorong footer ke bawah setelah form */
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-links a {
            color: #ccc;
            text-decoration: none;
            margin: 0 15px;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--secondary-color);
        }
        
        /* Responsif Sederhana */
        @media (max-width: 768px) {
            .hero h2 { font-size: 36px; }
            .feature-list, .car-list { flex-direction: column; align-items: center; }
            .search-form { transform: translateY(0); padding-bottom: 20px; gap: 10px; }
            .search-form button { width: 100%; margin-top: 10px; }
            .features { padding-top: 50px; }
            .car-card { width: 90%; }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">
            <h1>Azaria Rent Car</h1>
        </div>
        <nav>
            <ul>
                <li><a href="index.html">Beranda</a></li>
                <li><a href="fleet.html">Daftar Mobil</a></li>
                <li><a href="how-to-rent.html">Cara Sewa</a></li>
                <li><a href="contact.html">Kontak</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="hero">
            <div class="hero-content">
                <h2>Perjalanan Nyaman, Harga Terjangkau.</h2>
                <p>Sewa mobil terbaik untuk segala kebutuhan Anda di *[Nama Kota/Area Anda]*.</p>
                <a href="fleet.html" class="cta-button">Lihat Semua Mobil</a>
            </div>
            
            </section>

        <div class="search-form">
            <h3>Cari Mobil Impian Anda</h3>
            <form action="/search-results" method="GET">
                <div>
                    <label for="lokasi">Lokasi Ambil</label>
                    <input type="text" id="lokasi" name="lokasi" placeholder="Masukkan lokasi" required>
                </div>
                <div>
                    <label for="tanggal-ambil">Tanggal Ambil</label>
                    <input type="date" id="tanggal-ambil" name="tanggal-ambil" required>
                </div>
                <div>
                    <label for="tanggal-kembali">Tanggal Kembali</label>
                    <input type="date" id="tanggal-kembali" name="tanggal-kembali" required>
                </div>
                <button type="submit">Cari Mobil</button>
            </form>
        </div>


        <section class="features">
            <h2>Mengapa Memilih Azaria Rent Car?</h2>
            <div class="feature-list">
                <div class="feature-item">
                    
                    <h3>Pilihan Lengkap</h3>
                    <p>Berbagai jenis mobil mulai dari MPV ekonomis, SUV, hingga Van keluarga.</p>
                </div>
                <div class="feature-item">
                    
                    <h3>Harga Transparan</h3>
                    <p>Harga sewa jelas tanpa biaya tersembunyi. Mulai dari harga yang ramah di kantong.</p>
                </div>
                <div class="feature-item">
                    

[Image of 24 Hour Service Icon]

                    <h3>Layanan 24 Jam</h3>
                    <p>Tim dukungan pelanggan kami siap membantu Anda kapan saja, 24 jam sehari.</p>
                </div>
            </div>
        </section>

        <section class="popular-cars">
            <h2>Mobil Pilihan Populer</h2>
            <div class="car-list">
                
                <article class="car-card">
                    <div class="car-image"></div>
                    <div class="car-details">
                        <h3>Toyota Avanza</h3>
                        <p>7 Penumpang | Otomatis/Manual | AC Dingin</p>
                        <p class="price">Mulai dari <span>Rp 350.000</span> / hari</p>
                        <a href="detail-avanza.html" class="detail-button">Pesan Sekarang</a>
                    </div>
                </article>

                <article class="car-card">
                    <div class="car-image"></div>
                    <div class="car-details">
                        <h3>Honda Brio</h3>
                        <p>5 Penumpang | Otomatis | Irit BBM</p>
                        <p class="price">Mulai dari <span>Rp 280.000</span> / hari</p>
                        <a href="detail-brio.html" class="detail-button">Pesan Sekarang</a>
                    </div>
                </article>
                
                <article class="car-card">
                    <div class="car-image"></div>
                    <div class="car-details">
                        <h3>Innova Reborn</h3>
                        <p>7 Penumpang | Otomatis | Mewah & Nyaman</p>
                        <p class="price">Mulai dari <span>Rp 500.000</span> / hari</p>
                        <a href="detail-innova.html" class="detail-button">Pesan Sekarang</a>
                    </div>
                </article>

            </div>
            <a href="fleet.html" class="cta-button cta-button-secondary">Lihat Semua 25+ Pilihan Mobil</a>
        </section>

    </main>

    <footer>
        <div class="footer-content">
            <p>&copy; 2025 Azaria Rent Car. Hak Cipta Dilindungi.</p>
            <div class="footer-links">
                <a href="#">Kebijakan Privasi</a> | 
                <a href="#">Syarat & Ketentuan</a> | 
                <a href="contact.html">Kontak Kami</a>
            </div>
            <p>Layanan Pelanggan 24/7: *+62 812-3456-7890*</p>
        </div>
    </footer>

</body>
</html>
