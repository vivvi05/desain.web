
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>WORN.IN - Toko Pakaian Online</title>
  <style>
    /* Reset & base */
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      font-family: 'Poppins', sans-serif;

    }
    body {
      background-color: #fafafa;
      color: #333;
      line-height: 1.6;
      scroll-behavior: smooth;
    }
    a {
      text-decoration: none;
      color: inherit;
      cursor: pointer;
    }
    img {
      max-width: 100%;
      display: block;
    }
    /* Container */
    .container {
      width: 90%;
      max-width: 1200px;
      margin: auto;
    }
    /* Header */
    header {
      background-color: #fff;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    .nav-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 15px 0;
      flex-wrap: wrap;
      gap: 15px;
    }
    .logo {
      font-size: 1.8rem;
      font-weight: 700;
      color: #d6336c;
      letter-spacing: 2px;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 25px;
      flex-wrap: wrap;
    }
    nav ul li a {
      font-weight: 600;
      color: #555;
      padding: 8px 12px;
      border-radius: 6px;
      transition: background-color 0.3s ease, color 0.3s ease;
      display: inline-block;
    }
    nav ul li a:hover,
    nav ul li a.active {
      background-color: #d6336c;
      color: rgb(255, 255, 255);
    }
    .icon-cart {
      font-size: 1.5rem;
      color: #d6336c;
      cursor: pointer;
      position: relative;
    }
    .icon-cart::after {
      content: '3';
      position: absolute;
      top: -8px;
      right: -10px;
      background-color: #d6336c;
      color: white;
      font-size: 0.75rem;
      width: 18px;
      height: 18px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
    }
    /* Hero Section */
    .hero {
      background: url('https://images.unsplash.com/photo-1503342217505-b0a15ec3261c?auto=format&fit=crop&w=1400&q=80') no-repeat center center/cover;
      height: 450px;
      display: flex;
      align-items: center;
      color: white;
      position: relative;
      margin-bottom: 50px;
      border-radius: 10px;
      overflow: hidden;
    }
    .hero::after {
      content: '';
      position: absolute;
      inset: 0;
      background: rgba(214, 51, 108, 0.6);
      z-index: 1;
    }
    .hero-content {
      position: relative;
      z-index: 2;
      max-width: 600px;
      margin-left: 50px;
    }
    .hero-content h1 {
      font-size: 3.2rem;
      margin-bottom: 20px;
      font-weight: 700;
      letter-spacing: 2px;
    }
    .hero-content p {
      font-size: 1.2rem;
      margin-bottom: 30px;
    }
    .btn-primary {
      background-color: #fff;
      color: #d6336c;
      padding: 15px 35px;
      font-weight: 700;
      border-radius: 50px;
      transition: background-color 0.3s ease, color 0.3s ease;
      box-shadow: 0 5px 15px rgba(214, 51, 108, 0.4);
      display: inline-block;
    }
    .btn-primary:hover {
      background-color: #d6336c;
      color: white;
      box-shadow: 0 8px 20px rgba(214, 51, 108, 0.7);
    }
    /* Categories */
    .categories {
      display: flex;
      justify-content: space-between;
      margin-bottom: 50px;
      gap: 20px;
      flex-wrap: wrap;
    }
    .category-card {
      background-color: white;
      flex: 1 1 200px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      text-align: center;
      padding: 30px 20px;
      cursor: pointer;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .category-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 12px 24px rgba(214, 51, 108, 0.3);
    }
    .category-card img {
      width: 80px;
      margin-bottom: 15px;
    }
    .category-card h3 {
      font-weight: 700;
      color: #d6336c;
      font-size: 1.2rem;
    }
    /* Produk Grid */
    .produk-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 30px;
      margin-bottom: 60px;
    }
    .produk-item {
      background-color: white;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 6px 15px rgba(0,0,0,0.1);
      display: flex;
      flex-direction: column;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .produk-item:hover {
      transform: translateY(-8px);
      box-shadow: 0 15px 30px rgba(214, 51, 108, 0.4);
    }
    .produk-img {
      width: 100%;
      height: 280px;
      object-fit: cover;
    }
    .produk-info {
      padding: 20px;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .produk-info h4 {
      color: #d6336c;
      margin-bottom: 10px;
      font-size: 1.3rem;
      font-weight: 700;
    }
    .produk-info .harga {
      font-weight: 700;
      font-size: 1.2rem;
      margin-bottom: 15px;
      color: #333;
    }
    .btn-beli {
      background-color: #d6336c;
      color: white;
      padding: 12px 0;
      border-radius: 8px;
      font-weight: 700;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    .btn-beli:hover {
      background-color: #a0274f;
    }
    /* Testimoni Section */
    .testimoni {
      background-color: #d6336c;
      color: white;
      padding: 50px 20px;
      border-radius: 15px;
      margin-bottom: 60px;
      box-shadow: 0 8px 25px rgba(214, 51, 108, 0.4);
    }
    .testimoni h2 {
      text-align: center;
      margin-bottom: 40px;
      font-weight: 700;
      font-size: 2rem;
      letter-spacing: 1.5px;
    }
    .testimoni-cards {
      display: flex;
      gap: 30px;
      justify-content: center;
      flex-wrap: wrap;
    }
    .testimoni-card {
      background-color: white;
      color: #333;
      border-radius: 12px;
      padding: 25px;
      max-width: 300px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.1);
      font-style: italic;
      position: relative;
    }
    .testimoni-card::before {
      content: "“";
      font-size: 3rem;
      color: #d6336c;
      position: absolute;
      top: 10px;
      left: 15px;
      font-weight: 700;
    }
    .testimoni-card p {
      margin-bottom: 15px;
      font-size: 1rem;
    }
    .testimoni-card .author {
      font-weight: 700;
      font-style: normal;
      text-align: right;
      color: #d6336c;
    }
    /* Footer */
    footer {
      background-color: #222;
      color: #ddd;
      padding: 40px 20px;
      text-align: center;
      font-size: 0.9rem;
    }
    footer .social-icons {
      margin: 20px 0;
    }
    footer .social-icons a {
      color: #ddd;
      margin: 0 10px;
      font-size: 1.5rem;
      transition: color 0.3s ease;
    }
    footer .social-icons a:hover {
      color: #d6336c;
    }
    /* Layout dua kolom untuk Promo dan Contact */
    .promo-contact-wrapper {
      display: flex;
      gap: 40px;
      margin-bottom: 60px;
      flex-wrap: wrap;
    }
    .promo,
    .contact-centre {
      background-color: white;
      border-radius: 15px;
      padding: 30px 25px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.1);
      flex: 1 1 400px;
    }
    .promo h2,
    .contact-centre h2 {
      color: #d6336c;
      margin-bottom: 25px;
      text-align: center;
    }
    .promo-item {
      background: #fce4ec;
      padding: 20px;
      border-radius: 12px;
      margin-bottom: 20px;
      box-shadow: 0 4px 12px rgba(214,51,108,0.2);
      text-align: center;
    }
    .promo-item h3 {
      margin-bottom: 10px;
      color: #d6336c;
    }
    .promo-item p {
      font-weight: 600;
    }
    /* Contact Centre */
    .contact-centre p {
      margin: 8px 0;
      font-size: 1rem;
    }
    .contact-centre strong {
      color: #d6336c;
    }
    .contact-centre form {
      display: flex;
      flex-direction: column;
      gap: 15px;
      margin-top: 15px;
    }
    .contact-centre input[type="text"],
    .contact-centre input[type="email"],
    .contact-centre textarea {
      padding: 12px 15px;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 1rem;
      resize: vertical;
    }
    .contact-centre textarea {
      min-height: 100px;
    }
    .contact-centre button {
      background-color: #d6336c;
      color: white;
      padding: 12px;
      font-size: 1.1rem;
      font-weight: bold;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    .contact-centre button:hover {
      background-color: #a0274f;
    }
    /* Responsive */
    @media (max-width: 960px) {
      .promo-contact-wrapper {
        flex-direction: column;
      }
    }
    @media (max-width: 768px) {
      .nav-container {
        flex-direction: column;
        gap: 10px;
      }
      .categories {
        flex-direction: column;
      }
      .testimoni-cards {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
  <!-- Google Fonts Poppins -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet" />
  <!-- Font Awesome for cart icon -->
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
</head>
<body>

<header>
  <div class="container nav-container">
    <title>-WORN.IN WEAR:TOKO PAKAIAN-</title>
    <link rel="stylesheet" href="Untitled-1.css">
    <div class="logo">WORN.IN</div>
    <nav>
      <ul>
        <li><a href="#beranda" class="nav-link">Beranda</a></li>
        <li><a href="#pria" class="nav-link">Pria</a></li>
        <li><a href="#wanita" class="nav-link">Wanita</a></li>
        <li><a href="#anak" class="nav-link">Anak-anak</a></li>
        <li><a href="#aksesoris" class="nav-link">Aksesoris</a></li>
        <li><a href="#promo" class="nav-link">Promo</a></li>
        <li><a href="#contact-centre" class="nav-link">Contact Centre</a></li>
      </ul>
    </nav>
    <div class="icon-cart" title="Keranjang Belanja">
    <head>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
</head>
<div style="position: fixed; top: 20px; right: 20px; z-index: 999;">
  <a href="#keranjang" style="color: pink; font-size: 24px;">
    <i class="fas fa-shopping-cart"></i>
  </a>
</div>
      <i class="fas fa-shopping-cart"></i>
    </div>
  </div>
</header>

<!-- Beranda -->
<section id="beranda" class="container">
  <section class="hero">
    <div class="hero-content">
      <h1>Temukan Gaya Terbaikmu</h1>
      <p>Koleksi pakaian terbaru dan trendi untuk semua usia dan gaya.</p>
      <a href="#promo" class="btn-primary">Belanja Sekarang</a>
    </div>
  </section>

  <section class="categories">
    <a href="#pria" class="category-card">
      <img src="https://img.icons8.com/ios-filled/100/d6336c/t-shirt.png" alt="Kategori Pria" />
      <h3>Pria</h3>
    </a>
    <a href="#wanita" class="category-card">
      <img src="https://img.icons8.com/?size=60&id=73t1X3MvCFLA&format=png" alt="Kategori Wanita" />
      <h3>Wanita</h3>
    </a>
    <a href="#anak" class="category-card">
      <img src="https://img.icons8.com/ios-filled/100/d6336c/baby.png" alt="Kategori Anak-anak" />
      <h3>Anak-anak</h3>
    </a>
    <a href="#aksesoris" class="category-card">
      <img src="https://img.icons8.com/?size=24&id=QTWRmCUuctkE&format=png" alt="Kategori Aksesoris" />
      <h3>Aksesoris</h3>
    </a>
  </section>

  <section class="produk-grid">
    <article class="produk-item">
      <img class="produk-img" src="https://images.unsplash.com/photo-1520975693146-7a5d9e8f9e6f?auto=format&fit=crop&w=400&q=80" alt="Jaket Kulit" />
      <div class="produk-info">
        <h4>Jaket Kulit</h4>
        <div class="rating">★★★★★</div>
        <div class="harga">Rp 350.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
    <article class="produk-item">
      <img class="produk-img" src="https://images.unsplash.com/photo-1520975693146-7a5d9e8f9e6f?auto=format&fit=crop&w=400&q=80" alt="Kaos Polos" />
      <div class="produk-info">
        <h4>Kaos Polos</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 120.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
    <article class="produk-item">
      <img class="produk-img" src="https://images.unsplash.com/photo-1512436991641-6745cdb1723f?auto=format&fit=crop&w=400&q=80" alt="Sweater Hoodie" />
      <div class="produk-info">
        <h4>Sweater Hoodie</h4>
        <div class="rating">★★★★★</div>
        <div class="harga">Rp 250.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
    <article class="produk-item">
      <img class="produk-img" src="https://images.unsplash.com/photo-1562158070-3b8e6f9b4d8b?auto=format&fit=crop&w=400&q=80" alt="Celana Jeans" />
      <div class="produk-info">
        <h4>Celana Jeans</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 300.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
  </section>

  <section class="testimoni">
    <h2>Apa Kata Pelanggan Kami?</h2>
    <div class="testimoni-cards">
      <div class="testimoni-card">
        <p> Pelayanan cepat dan produk berkualitas! Saya sangat puas dengan pembelian saya.</p>
        <div class="author"> - Rina S.</div>
      </div>
      <div class="testimoni-card">
        <p> Desainnya keren dan bahannya nyaman dipakai. Recommended banget!</p>
        <div class="author"> - Andi P.</div>
      </div>
      <div class="testimoni-card">
        <p> Pengiriman tepat waktu dan customer service ramah. Terima kasih WORN.IN!</p>
        <div class="author"> - Maya L.</div>
      </div>
    </div>
  </section>
</section>

<!-- Pria -->
<section id="pria" class="container">
  <h2>Produk Pria</h2>
  <div class="produk-grid">
    <article class="produk-item">
      <img src="https://images.unsplash.com/photo-1520975693146-7a5d9e8f9e6f?auto=format&fit=crop&w=400&q=80" alt="Jaket Kulit" />
      <div class="produk-info">
        <h4>Jaket Kulit</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 350.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
    <article class="produk-item">
      <img src="https://images.unsplash.com/photo-1503342217505-b0a15ec3261c?auto=format&fit=crop&w=400&q=80" alt="Kaos Polos" />
      <div class="produk-info">
        <h4>Kaos Polos</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 120.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
  </div>
</section>

<!-- Wanita -->
<section id="wanita" class="container">
  <h2>Produk Wanita</h2>
  <div class="produk-grid">
    <article class="produk-item">
      <img src="https://images.unsplash.com/photo-1512436991641-6745cdb1723f?auto=format&fit=crop&w=400&q=80" alt="Sweater Hoodie" />
      <div class="produk-info">
        <h4>Sweater Hoodie</h4>
          <div class="rating">★★★★☆</div>
        <div class="harga">Rp 250.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
    <article class="produk-item">
      <img src="https://images.unsplash.com/photo-1562158070-3b8e6f9b4d8b?auto=format&fit=crop&w=400&q=80" alt="Celana Jeans" />
      <div class="produk-info">
        <h4>Celana Jeans</h4>
          <div class="rating">★★★★☆</div>
        <div class="harga">Rp 300.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
  </div>
</section>

<!-- Anak-anak -->
<section id="anak" class="container">
  <h2>Produk Anak-anak</h2>
  <div class="produk-grid">
    <article class="produk-item">
      <img src="https://images.unsplash.com/photo-1601925240970-98447486fcdb?q=80&w=580&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Kaos Anak" />
      <div class="produk-info">
        <h4>Kaos Anak</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 90.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
    <article class="produk-item">
      <img src="https://plus.unsplash.com/premium_photo-1675183689638-a68fe7048da9?q=80&w=870&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Celana Pendek Anak" />
      <div class="produk-info">
        <h4>Outfit Set For Baby</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 110.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
  </div>
</section>

<!-- Aksesoris -->
<section id="aksesoris" class="container">
  <h2>Aksesoris</h2>
  <div class="produk-grid">
    <article class="produk-item">
      <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=400&q=80" alt="Kacamata Hitam" />
      <div class="produk-info">
        <h4>Kacamata Hitam</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 150.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
    <article class="produk-item">
      <img src="https://images.unsplash.com/photo-1526170375885-4d8ecf77b99f?auto=format&fit=crop&w=400&q=80" alt="Topi Baseball" />
      <div class="produk-info">
        <h4>Topi Baseball</h4>
        <div class="rating">★★★★☆</div>
        <div class="harga">Rp 80.000,-</div>
        <div class="btn-beli">Beli Sekarang</div>
      </div>
    </article>
  </div>
</section>

<!-- Promo dan Contact Centre berdampingan -->
<section class="container promo-contact-wrapper">
  <section id="promo" class="promo">
    <h2>Promo Spesial</h2>
    <div class="promo-item">
      <h3>Diskon 30% untuk Jaket Kulit</h3>
      <p>Beli jaket kulit sekarang dan dapatkan potongan harga spesial!</p>
    </div>
    <div class="promo-item">
      <h3>Beli 2 Kaos Polos Gratis 1</h3>
      <p>Promo beli 2 kaos polos untuk semua kategori pria dan wanita.</p>
    </div>
  </section>

  <section id="contact-centre" class="contact-centre">
    <h2>Contact Centre</h2>
     <!-- Social Links as Text -->
  <div style="margin-top: 10px;">
    <p><strong>Owners:</strong>  <a href="https://www.instagram.com/vivvilooo_?igsh=MWF1YjVyZHNqdWJ3cA==" target="_blank" style="margin: 0 10px; text-decoration: none; color: #4267B2;">Vivi Handayani</a>
    <a href="https://instagram.com/pipay.cantik" target="_blank" style="margin: 0 10px; text-decoration: none; color: #E1306C;">Salni Fitra</a>
    <a href="https://www.instagram.com/dahlia_munthee?igsh=MXJuanljNmZlOTNwOA==" target="_blank" style="margin: 0 10px; text-decoration: none; color: #1DA1F2;"> Dahlia Kumala Sari</a>
   <a href="https://instagram.com/pipay.cantik" target="_blank" style="margin: 0 10px; text-decoration: none; color: #0fa10a;"> Isdah Riadoh </a>
    <p><strong>Telepon:</strong> 021-1234-5678</p>
    <p><strong>Email:</strong> support@worn.in.com</p>
    <p><strong>Alamat:</strong> Jl. Merdeka, no 059, Kota Padangsidimpuan</p>
    <p><strong>Jam Operasional:</strong> Senin - Minggu, 07:00 - 23:00 WIB</p>

    <form action="#" method="post">
      <input type="text" name="nama" placeholder="Nama Lengkap" required />
      <input type="email" name="email" placeholder="Email Anda" required />
      <textarea name="pesan" placeholder="Tulis pesan Anda di sini..." required></textarea>
      <button type="submit">Kirim Pesan</button>
    </form>
 

<footer>
  <p>© 2025 WORN.IN. Semua hak cipta dilindungi.</p>
  <div class="social-icons">
  <!-- Social Media Icons + Text Horizontal -->
  <div style="display: flex; justify-content: center; gap: 30px; margin-top: 15px;">
    
    <!-- Facebook -->
    <a href="https://facebook.com/akunpipay" target="_blank" style="text-decoration: none; color: inherit;">
      <div style="display: flex; flex-direction: column; align-items: center;">
        <img src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/facebook.svg" alt="Facebook" width="30" height="30">
        <span style="margin-top: 5px;">Facebook</span>
      </div>
    </a>

    <!-- Instagram -->
    <a href="https://www.instagram.com/vivvilooo_?igsh=MWF1YjVyZHNqdWJ3cA==" target="_blank" style="text-decoration: none; color: inherit;">
      <div style="display: flex; flex-direction: column; align-items: center;">
        <img src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/instagram.svg" alt="Instagram" width="30" height="30">
        <span style="margin-top: 5px;">Instagram</span>
      </div>
    </a>

    <!-- Twitter -->
    <a href="https://twitter.com/akunpipay" target="_blank" style="text-decoration: none; color: inherit;">
      <div style="display: flex; flex-direction: column; align-items: center;">
        <img src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/twitter.svg" alt="Twitter" width="30" height="30">
        <span style="margin-top: 5px;">Twitter</span>
      </div>
    </a>




