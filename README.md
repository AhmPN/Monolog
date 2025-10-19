<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Website Video - Kelas & Komentar</title>
    <style>
        /* === Gaya Dasar & Reset === */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            background-color: #f0f2f5; 
            color: #333;
        }
        /* === 1. Gaya Halaman Intro === */
        #intro-page {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            text-align: center;
            background-color: #ffffff;
            transition: opacity 0.5s ease;
        }
        .intro-box {
            padding: 50px 70px;
            border-radius: 12px;
            box-shadow: 0 8px 30px rgba(0,0,0,0.1);
        }
        .intro-box h1 {
            color: #1877f2;
            margin-bottom: 30px;
            font-size: 2em;
        }
        .yes-button {
            background-color: #4CAF50; /* Hijau */
            color: white;
            padding: 15px 35px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.2em;
            font-weight: bold;
            transition: background-color 0.3s, transform 0.1s;
        }
        .yes-button:hover {
            background-color: #45a049;
            transform: translateY(-2px);
        }
        /* === 2. Gaya Halaman Video === */
        #video-page {
            display: none; /* Awalnya tersembunyi */
            max-width: 900px;
            margin: 20px auto;
            background-color: #ffffff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }        
        /* Kontainer Video */
        .video-container {
            margin-bottom: 25px;
            position: relative;
            padding-bottom: 56.25%; /* Rasio aspek 16:9 */
            height: 0;
            overflow: hidden;
            border-radius: 6px;
        }
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }
        /* === 3. Gaya Form Komentar (FormSubmit) === */
        .comment-section {
            margin-top: 40px;
            padding: 25px;
            background: #fcfcfc; 
            border: 1px solid #eee;
            border-radius: 8px; 
        }
        .comment-section h2 {
            font-size: 1.5em;
            color: #333;
            border-bottom: 3px solid #1877f2;
            padding-bottom: 10px;
            margin-top: 0;
            margin-bottom: 25px;
        }
        .comment-form label {
            display: block;
            margin-top: 15px;
            margin-bottom: 5px;
            font-weight: 600;
        }
        .comment-form input[type="text"], 
        .comment-form textarea {
            width: 100%;
            padding: 12px;
            border-radius: 6px;
            border: 1px solid #ccc;
            box-sizing: border-box;
            font-size: 1em;
        }
        .comment-form textarea {
            resize: vertical;
        }
        .comment-form button {
            padding: 12px 20px;
            background: #1877f2; /* Warna Biru */
            color: white;
            border: none;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            margin-top: 20px;
            transition: background-color 0.3s;
        }
        .comment-form button:hover {
            background: #1565c0;
        }
        .note {
            margin-top: 15px;
            text-align: center;
            color: #777;
            font-size: 0.9em;
        }
    </style>
</head>
<body>
    <div id="intro-page">
        <div class="intro-box">
            <h1>Selamat Datang!</h1>
            <p>Apakah Anda siap untuk menonton video pembelajaran?</p>
            <button class="yes-button" onclick="openVideoPage()">Ya, Tonton Sekarang</button>
        </div>
    </div>
    <div id="video-page">
        <h1>Video Materi Terbaru</h1>        
        <div class="video-container">
            <iframe 
                src="https://www.youtube.com/embed/RcYBESkpfMs" 
                title="Video Pembelajaran" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                allowfullscreen>
            </iframe>
        </div>       
        <p>Silakan tonton video di atas, dan berikan tanggapan, pertanyaan, atau masukan Anda di formulir bawah ini.</p>
        <section class="comment-section">
            <h2>Kirim Komentar/Masukan Anda</h2>           
            <form action="https://formsubmit.co/ahmadputra.nur31@GMAIL.COM" method="POST" class="comment-form">    
                <label for="name-input">Nama Lengkap:</label>
                <input type="text" id="name-input" name="Nama Pengirim" required>                
                <label for="comment-input">Tulis Pesan/Komentar:</label>
                <textarea id="comment-input" name="Komentar" required rows="5"></textarea>                
                <input type="hidden" name="_captcha" value="false"> 
                <input type="hidden" name="_template" value="table"> 
                <input type="hidden" name="_subject" value="[KOMENTAR BARU] dari Website Video"> 
                <input type="hidden" name="_next" value="https://formsubmit.co/thankyou.html">                
                <button type="submit">
                    Kirim Komentar 📧
                </button>
            </form>
            <p class="note">
                *Komentar Anda akan dikirimkan ke email administrator (**ahmadputra.nur31@GMAIL.COM**) untuk ditinjau.
            </p>
        </section>
    </div>
    <script>
        // Fungsi untuk menyembunyikan intro dan menampilkan halaman video
        function openVideoPage() {
            const intro = document.getElementById('intro-page');
            intro.style.opacity = '0'; // Mulai memudar
            setTimeout(() => {
                intro.style.display = 'none'; // Sembunyikan setelah memudar
                document.getElementById('video-page').style.display = 'block'; // Tampilkan Video
                window.scrollTo(0, 0); // Gulir ke atas halaman video
            }, 500); // Waktu yang sama dengan durasi transisi
        }
    </script>
</body>
</html>
