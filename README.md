<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Paskibra SMKN 11 Pandeglang</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background-color: #f5f5f5;
            color: #222;
        }

        /* NAVBAR */
        nav {
            width: 100%;
            background-color: #b30000;
            color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 8%;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        nav .logo-text {
            font-size: 20px;
            font-weight: bold;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            cursor: pointer;
        }

        nav ul li a:hover {
            color: #ffd700;
        }

        .menu-button {
            display: none;
            font-size: 25px;
            cursor: pointer;
        }

        /* HALAMAN */
        .page {
            display: none;
            min-height: 85vh;
            padding: 40px 8%;
        }

        .page.active {
            display: block;
        }

        /* BERANDA */
        #beranda {
            padding: 0;
            min-height: 90vh;
            background: linear-gradient(
                to bottom,
                #c40000 0%,
                #c40000 50%,
                white 50%,
                white 100%
            );
            display: none;
            align-items: center;
            justify-content: center;
        }

        #beranda.active {
            display: flex;
        }

        .hero-box {
            background-color: white;
            width: 90%;
            max-width: 850px;
            text-align: center;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
        }

        .school-logo {
            width: 150px;
            height: 150px;
            object-fit: contain;
            margin-bottom: 20px;
            border-radius: 50%;
        }

        .hero-box h1 {
            color: #b30000;
            font-size: 45px;
            margin-bottom: 10px;
        }

        .hero-box h2 {
            color: #222;
            margin-bottom: 20px;
        }

        .hero-box p {
            line-height: 1.8;
            font-size: 17px;
        }

        .button {
            display: inline-block;
            margin-top: 25px;
            padding: 12px 25px;
            background-color: #b30000;
            color: white;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            cursor: pointer;
        }

        .button:hover {
            background-color: #800000;
        }

        /* JUDUL HALAMAN */
        .page-title {
            text-align: center;
            color: #b30000;
            margin-bottom: 35px;
            font-size: 32px;
        }

        /* CARD */
        .card-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
            gap: 25px;
        }

        .card {
            background-color: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.12);
            text-align: center;
        }

        .card h3 {
            color: #b30000;
            margin-bottom: 15px;
        }

        .card p {
            line-height: 1.6;
        }

        /* SELEKSI */
        .steps {
            max-width: 750px;
            margin: auto;
        }

        .step {
            background-color: white;
            margin-bottom: 18px;
            padding: 20px;
            border-left: 7px solid #b30000;
            border-radius: 8px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }

        .step h3 {
            color: #b30000;
            margin-bottom: 8px;
        }

        /* GALERI */
        .gallery-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
            gap: 25px;
        }

        .gallery-card {
            background-color: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        }

        .gallery-card img {
            width: 100%;
            height: 230px;
            object-fit: cover;
            display: block;
        }

        .gallery-card p {
            padding: 15px;
            text-align: center;
            font-weight: bold;
            color: #b30000;
        }

        /* FOOTER */
        footer {
            background-color: #b30000;
            color: white;
            text-align: center;
            padding: 20px;
            line-height: 1.8;
        }

        footer a {
            color: white;
        }

        /* RESPONSIVE */
        @media screen and (max-width: 768px) {
            nav ul {
                display: none;
                position: absolute;
                top: 60px;
                right: 0;
                background-color: #b30000;
                width: 100%;
                flex-direction: column;
                text-align: center;
                padding: 20px;
                gap: 20px;
            }

            nav ul.show {
                display: flex;
            }

            .menu-button {
                display: block;
            }

            .hero-box {
                padding: 25px;
            }

            .hero-box h1 {
                font-size: 35px;
            }

            .hero-box h2 {
                font-size: 20px;
            }

            .school-logo {
                width: 120px;
                height: 120px;
            }
        }
    </style>
</head>

<body>

    <!-- NAVBAR -->
    <nav>
        <div class="logo-text">PASKIBRA SMKN 11</div>

        <div class="menu-button" onclick="toggleMenu()">☰</div>

        <ul id="navMenu">
            <li><a onclick="showPage('beranda')">Beranda</a></li>
            <li><a onclick="showPage('kegiatan')">Kegiatan</a></li>
            <li><a onclick="showPage('prestasi')">Prestasi</a></li>
            <li><a onclick="showPage('seleksi')">Seleksi</a></li>
            <li><a onclick="showPage('galeri')">Galeri</a></li>
        </ul>
    </nav>

    <!-- BERANDA -->
    <section id="beranda" class="page active">
        <div class="hero-box">

            <img
                class="school-logo"
                src="https://commons.wikimedia.org/wiki/Special:Redirect/file/Logo-smkn11-pandeglang.jpg"
                alt="Logo SMKN 11 Pandeglang">

            <h1>PASKIBRA</h1>

            <h2>SMKN 11 PANDEGLANG</h2>

            <p>
                Selamat datang di website resmi Paskibra SMKN 11 Pandeglang.
                Website ini berisi informasi mengenai kegiatan, prestasi,
                proses seleksi, dan dokumentasi Paskibra.
            </p>

            <a class="button" onclick="showPage('kegiatan')">
                Lihat Kegiatan
            </a>

        </div>
    </section>

    <!-- KEGIATAN -->
    <section id="kegiatan" class="page">

        <h2 class="page-title">Kegiatan Paskibra</h2>

        <div class="card-container">

            <div class="card">
                <h3>Latihan Baris-Berbaris</h3>
                <p>
                    Latihan rutin untuk meningkatkan kedisiplinan,
                    kekompakan, ketepatan gerakan, dan tanggung jawab anggota.
                </p>
            </div>

            <div class="card">
                <h3>Upacara Bendera</h3>
                <p>
                    Anggota Paskibra bertugas dalam pelaksanaan upacara
                    bendera di lingkungan sekolah.
                </p>
            </div>

            <div class="card">
                <h3>Latihan Fisik</h3>
                <p>
                    Kegiatan olahraga dan latihan fisik untuk menjaga
                    kebugaran serta meningkatkan daya tahan tubuh.
                </p>
            </div>

            <div class="card">
                <h3>Pelatihan Kepemimpinan</h3>
                <p>
                    Kegiatan untuk melatih sikap kepemimpinan,
                    keberanian, kerja sama, dan rasa tanggung jawab.
                </p>
            </div>

        </div>
    </section>

    <!-- PRESTASI -->
    <section id="prestasi" class="page">

        <h2 class="page-title">Prestasi Paskibra</h2>

        <div class="card-container">

            <div class="card">
                <h3>Prestasi Baris-Berbaris</h3>
                <p>
                    Paskibra berusaha mengikuti berbagai perlombaan
                    baris-berbaris untuk mengembangkan kemampuan anggota.
                </p>
            </div>

            <div class="card">
                <h3>Prestasi Upacara</h3>
                <p>
                    Anggota Paskibra berpartisipasi dalam berbagai
                    kegiatan upacara di sekolah maupun di luar sekolah.
                </p>
            </div>

            <div class="card">
                <h3>Prestasi Kedisiplinan</h3>
                <p>
                    Anggota dilatih untuk menjadi pribadi yang disiplin,
                    bertanggung jawab, dan mampu bekerja sama.
                </p>
            </div>

        </div>
    </section>

    <!-- SELEKSI -->
    <section id="seleksi" class="page">

        <h2 class="page-title">Tahapan Seleksi Paskibra</h2>

        <div class="steps">

            <div class="step">
                <h3>1. Pendaftaran</h3>
                <p>
                    Calon anggota mengisi formulir pendaftaran
                    dan mengikuti ketentuan yang telah ditentukan.
                </p>
            </div>

            <div class="step">
                <h3>2. Pemeriksaan Kesehatan</h3>
                <p>
                    Calon anggota mengikuti pemeriksaan kesehatan
                    untuk mengetahui kondisi fisik.
                </p>
            </div>

            <div class="step">
                <h3>3. Tes Fisik</h3>
                <p>
                    Calon anggota mengikuti tes fisik seperti
                    lari, push-up, sit-up, dan latihan ketahanan.
                </p>
            </div>

            <div class="step">
                <h3>4. Tes Baris-Berbaris</h3>
                <p>
                    Calon anggota diuji dalam ketepatan gerakan,
                    sikap sempurna, kekompakan, dan kedisiplinan.
                </p>
            </div>

            <div class="step">
                <h3>5. Pengumuman</h3>
                <p>
                    Peserta yang memenuhi kriteria akan diumumkan
                    sebagai anggota Paskibra.
                </p>
            </div>

        </div>
    </section>

    <!-- GALERI -->
    <section id="galeri" class="page">

        <h2 class="page-title">Galeri Paskibra</h2>

        <div class="gallery-container">

            <div class="gallery-card">
                <img
                    src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Paskibraka.jpg/640px-Paskibraka.jpg"
                    alt="Kegiatan Paskibra">

                <p>Latihan dan Kegiatan Paskibra</p>
            </div>

            <div class="gallery-card">
                <img
                    src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/Indonesian_flag_raising_ceremony.jpg/640px-Indonesian_flag_raising_ceremony.jpg"
                    alt="Upacara Pengibaran Bendera">

                <p>Upacara Pengibaran Bendera</p>
            </div>

            <div class="gallery-card">
                <img
                    src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Indonesian_students_flag_ceremony.jpg/640px-Indonesian_students_flag_ceremony.jpg"
                    alt="Siswa dalam Upacara">

                <p>Kekompakan Anggota</p>
            </div>

            <div class="gallery-card">
                <img
                    src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9c/Indonesian_flag_ceremony.jpg/640px-Indonesian_flag_ceremony.jpg"
                    alt="Upacara Bendera Indonesia">

                <p>Semangat Merah Putih</p>
            </div>

        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <p><strong>PASKIBRA SMKN 11 PANDEGLANG</strong></p>
        <p>Dibuat oleh : Nesya Maulida</p>
        <p>
            Logo sekolah digunakan sebagai identitas SMKN 11 Pandeglang.
        </p>
    </footer>

    <script>
        function showPage(pageId) {
            let pages = document.querySelectorAll(".page");

            pages.forEach(function(page) {
                page.classList.remove("active");
            });

            document.getElementById(pageId).classList.add("active");

            document.getElementById("navMenu").classList.remove("show");

            window.scrollTo({
                top: 0,
                behavior: "smooth"
            });
        }

        function toggleMenu() {
            document.getElementById("navMenu").classList.toggle("show");
        }
    </script>

</body>
</html>
