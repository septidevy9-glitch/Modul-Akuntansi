# Modul-Akuntansi
Mata Pelajaran Ekonomi XII Fase F
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-Modul Akuntansi Bab 4 - MAN 1 Lampung Timur</title>
    <style>
        :root {
            --primary: #047857;
            --primary-dark: #065f46;
            --secondary: #0284c7;
            --accent: #10b981;
            --bg: #f3f4f6;
            --card-bg: #ffffff;
            --text: #1f2937;
            --text-light: #4b5563;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
            padding-bottom: 40px;
        }

        .app-container {
            max-width: 600px;
            margin: 0 auto;
            background: var(--card-bg);
            min-height: 100vh;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }

        header {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            color: white;
            padding: 25px 20px;
            text-align: center;
            border-bottom-left-radius: 20px;
            border-bottom-right-radius: 20px;
        }

        .badge {
            background: rgba(255, 255, 255, 0.2);
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            display: inline-block;
            margin-bottom: 8px;
        }

        header h1 { font-size: 1.3rem; font-weight: 700; margin-bottom: 5px; }
        header p { font-size: 0.85rem; opacity: 0.9; }
        .meta-info {
            margin-top: 15px; padding-top: 10px; border-top: 1px solid rgba(255,255,255,0.2);
            font-size: 0.8rem; display: flex; justify-content: space-around;
        }

        .nav-scroller {
            display: flex; overflow-x: auto; background: #e5e7eb; padding: 8px; gap: 6px;
            position: sticky; top: 0; z-index: 100;
        }
        .nav-scroller::-webkit-scrollbar { display: none; }
        .nav-btn {
            flex: 0 0 auto; padding: 10px 14px; border: none; background: white; color: var(--text);
            border-radius: 8px; font-size: 0.8rem; font-weight: 600; cursor: pointer; transition: all 0.2s ease;
        }
        .nav-btn.active { background: var(--primary); color: white; box-shadow: 0 2px 5px rgba(4, 120, 87, 0.3); }

        .tab-content { display: none; padding: 20px; animation: fadeIn 0.3s ease-in-out; }
        .tab-content.active { display: block; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(5px); } to { opacity: 1; transform: translateY(0); } }

        h2 { font-size: 1.15rem; color: var(--primary-dark); margin: 20px 0 10px 0; border-bottom: 2px solid var(--accent); padding-bottom: 4px; }
        h3 { font-size: 0.98rem; color: var(--secondary); margin: 15px 0 8px 0; }
        p, li { font-size: 0.88rem; color: var(--text-light); margin-bottom: 10px; text-align: justify; }
        ul, ol { padding-left: 20px; margin-bottom: 12px; }

        .card {
            background: #f9fafb; border: 1px solid #e5e7eb; border-left: 4px solid var(--primary);
            border-radius: 8px; padding: 14px; margin: 12px 0;
        }
        .card-title { font-weight: 700; color: var(--primary-dark); font-size: 0.9rem; margin-bottom: 6px; }
        .formula-box {
            background: #ecfdf5; border: 1px dashed var(--primary); padding: 12px;
            border-radius: 8px; text-align: center; font-weight: bold; color: var(--primary-dark); margin: 12px 0; font-size: 0.95rem;
        }

        /* LOCKED SYSTEM STYLES */
        .step-section {
            background: #ffffff; border: 1px solid #e5e7eb; border-radius: 8px; padding: 15px; margin-bottom: 15px;
        }
        .step-locked { opacity: 0.5; pointer-events: none; filter: grayscale(80%); }
        .lock-badge { background: #fee2e2; color: #991b1b; padding: 2px 8px; border-radius: 4px; font-size: 0.75rem; font-weight: bold; display: inline-block; margin-bottom: 5px; }
        .unlock-badge { background: #ecfdf5; color: #065f46; padding: 2px 8px; border-radius: 4px; font-size: 0.75rem; font-weight: bold; display: inline-block; margin-bottom: 5px; }
        
        .btn-next-step {
            background: var(--secondary); color: white; border: none; padding: 8px 14px; border-radius: 6px;
            font-size: 0.8rem; font-weight: bold; cursor: pointer; margin-top: 10px; display: block; width: 100%; text-align: center;
        }
        .btn-next-step:hover { background: #0369a1; }

        /* TABLE & LABIRIN */
        .table-responsive { overflow-x: auto; margin: 12px 0; border-radius: 6px; border: 1px solid #d1d5db; }
        table { width: 100%; border-collapse: collapse; font-size: 0.78rem; min-width: 480px; }
        th, td { border: 1px solid #d1d5db; padding: 6px 8px; text-align: left; }
        th { background: #e5e7eb; color: var(--primary-dark); font-weight: bold; }

        .game-card { background: linear-gradient(135deg, #e0f2fe, #bae6fd); border-radius: 12px; padding: 16px; margin: 15px 0; }
        
        /* MAZE GAME STYLES */
        #maze-board {
            width: 220px; height: 220px; display: grid; grid-template-columns: repeat(5, 1fr);
            grid-template-rows: repeat(5, 1fr); gap: 3px; background: #1e293b; padding: 5px; border-radius: 8px; margin: 15px auto;
        }
        .maze-cell { background: #ffffff; border-radius: 3px; display: flex; align-items: center; justify-content: center; font-size: 1.2rem; }
        .maze-wall { background: #334155; }
        .maze-start { background: #10b981; color: white; font-weight: bold; font-size: 0.7rem; }
        .maze-goal { background: #f59e0b; color: white; font-weight: bold; font-size: 0.7rem; }
        .maze-player { background: #0284c7; border-radius: 50%; width: 25px; height: 25px; display: flex; align-items: center; justify-content: center; color: white; font-size: 0.8rem; }
        
        .controls-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 5px; max-width: 180px; margin: 0 auto; }
        .ctrl-btn { background: var(--primary); color: white; border: none; padding: 10px; border-radius: 6px; font-weight: bold; cursor: pointer; font-size: 1rem; }

        /* LKPD INTERAKTIF INPUT */
        .lkpd-input { width: 90px; padding: 4px; font-size: 0.8rem; border: 1px solid #ccc; border-radius: 4px; text-align: right; }

        /* ASESMEN A-E */
        .question-card { background: #ffffff; border: 1px solid #e5e7eb; border-radius: 10px; padding: 14px; margin-bottom: 15px; }
        .question-title { font-weight: 600; font-size: 0.88rem; color: var(--text); margin-bottom: 10px; }
        .option-label { display: block; background: #f9fafb; border: 1px solid #e5e7eb; padding: 8px 10px; border-radius: 6px; margin-bottom: 6px; font-size: 0.82rem; cursor: pointer; }
        .option-label:hover { background: #f3f4f6; }
        .option-label input { margin-right: 8px; }

        .btn-submit {
            width: 100%; background: var(--primary); color: white; border: none; padding: 14px;
            border-radius: 10px; font-size: 0.95rem; font-weight: bold; cursor: pointer; margin-top: 15px;
        }
        .score-box { display: none; background: #ecfdf5; border: 2px solid var(--accent); border-radius: 10px; padding: 20px; text-align: center; margin-top: 20px; }
        .score-number { font-size: 2.5rem; font-weight: 800; color: var(--primary-dark); }
        footer { text-align: center; padding: 20px; font-size: 0.75rem; color: #9ca3af; background: #f9fafb; border-top: 1px solid #e5e7eb; margin-top: 20px; }
    </style>
</head>
<body>

<div class="app-container">
    <header>
        <span class="badge">E-Modul Akuntansi Berbasis Sekuensial</span>
        <h1>MAN 1 LAMPUNG TIMUR</h1>
        <p>Bab 4 — Siklus Akuntansi & Laporan Keuangan</p>
        <div class="meta-info">
            <span><b>Penyusun:</b> Devy Septianasari, S.Pd.</span>
            <span><b>Kelas:</b> XII / Ganjil</span>
        </div>
    </header>

    <div class="nav-scroller">
        <button class="nav-btn active" onclick="openTab(event, 'petunjuk')">📌 Petunjuk</button>
        <button class="nav-btn" onclick="openTab(event, 'materi')">📖 Materi Berurutan</button>
        <button class="nav-btn" onclick="openTab(event, 'game')">🕹️ 10 Challenge & Labirin</button>
        <button class="nav-btn" onclick="openTab(event, 'lkpd')">📋 LKPD Interaktif</button>
        <button class="nav-btn" onclick="openTab(event, 'asesmen')">✍️ Asesmen (A-E)</button>
    </div>

    <!-- TAB 1: PETUNJUK -->
    <div id="petunjuk" class="tab-content active">
        <h2>Petunjuk Pembelajaran Sistem Berurutan</h2>
        <p>E-modul ini menerapkan sistem belajar **berurutan (*sequential learning*)**. Anda **tidak dapat** membuka materi berikutnya sebelum menuntaskan dan mengeklik tombol "Selesai Membaca" di poin sebelumnya.</p>
        <div class="card">
            <div class="card-title">✨ Fitur Unggulan Modul Ini:</div>
            <ul>
                <li><b>Materi Terkunci:</b> Melatih kedisiplinan membaca runtut dari Bab I hingga Bab XI.</li>
                <li><b>10 Challenge & Labirin Bintang (1-5):</b> Game edukasi ketepatan & kecepatan menghitung labirin akuntansi.</li>
                <li><b>LKPD Validasi Otomatis:</b> Lembar kerja interaktif langsung di modul dengan cek poin tepat/tidak.</li>
                <li><b>Asesmen Pilihan Ganda (A s.d E):</b> 20 soal evaluasi lengkap dengan skor otomatis.</li>
            </ul>
        </div>
    </div>

    <!-- TAB 2: MATERI BERURUTAN (LOCKED SYSTEM) -->
    <div id="materi" class="tab-content">
        <h2>Materi Pembelajaran Bab 4 (Wajib Berurutan)</h2>

        <!-- STEP 1 -->
        <div id="step-1" class="step-section">
            <span class="unlock-badge">✔ Bab 1: Pengantar Akuntansi (Terbuka)</span>
            <h3>1. Pengertian & Tujuan Akuntansi</h3>
            <p>Akuntansi adalah proses mengidentifikasi, mengukur, mencatat, menggolongkan, meringkas, dan melaporkan transaksi keuangan suatu entitas untuk menghasilkan informasi bagi pengambilan keputusan (*language of business*).</p>
            <button class="btn-next-step" onclick="unlockStep(2)">Selesai Membaca Bab 1 & Lanjut ➔</button>
        </div>

        <!-- STEP 2 -->
        <div id="step-2" class="step-section step-locked">
            <span id="badge-2" class="lock-badge">🔒 Terkunci (Selesaikan Bab 1 Dulu)</span>
            <h3>2. Pengguna & Prinsip Dasar Akuntansi</h3>
            <p>Pengguna informasi akuntansi terbagi menjadi pihak internal (manajemen, pemilik) dan eksternal (kreditur, pemerintah, investor). Prinsip dasar meliputi Entitas Ekonomi, Kelangsungan Usaha, dan Basis Akrual.</p>
            <button class="btn-next-step" onclick="unlockStep(3)">Selesai Membaca Bab 2 & Lanjut ➔</button>
        </div>

        <!-- STEP 3 -->
        <div id="step-3" class="step-section step-locked">
            <span id="badge-3" class="lock-badge">🔒 Terkunci (Selesaikan Bab 2 Dulu)</span>
            <h3>3. Persamaan Dasar Akuntansi (PDA)</h3>
            <p>Rumus utama keseimbangan akuntansi: <b>Aset = Liabilitas + Ekuitas</b>. Diperluas menjadi: <i>Aset = Liabilitas + Modal + Pendapatan − Beban − Prive</i>.</p>
            <button class="btn-next-step" onclick="unlockStep(4)">Selesai Membaca Bab 3 & Lanjut ➔</button>
        </div>

        <!-- STEP 4 -->
        <div id="step-4" class="step-section step-locked">
            <span id="badge-4" class="lock-badge">🔒 Terkunci (Selesaikan Bab 3 Dulu)</span>
            <h3>4. Siklus Jurnal Umum & Aturan Debit-Kredit</h3>
            <p>Aturan saldo normal: Aset, Beban, dan Prive bersaldo normal <b>Debit</b> (bertambah di debit). Liabilitas, Modal, dan Pendapatan bersaldo normal <b>Kredit</b> (bertambah di kredit).</p>
            <button class="btn-next-step" onclick="unlockStep(5)">Selesai Membaca Bab 4 & Lanjut ➔</button>
        </div>

        <!-- STEP 5 -->
        <div id="step-5" class="step-section step-locked">
            <span id="badge-5" class="lock-badge">🔒 Terkunci (Selesaikan Bab 4 Dulu)</span>
            <h3>5. Buku Besar, Neraca Saldo & Penyesuaian</h3>
            <p>Posting jurnal ke buku besar untuk melihat saldo akhir masing-masing akun. Di akhir periode, dibuat jurnal penyesuaian untuk memperbarui akun seperti perlengkapan terpakai dan penyusutan aset.</p>
            <button class="btn-next-step" onclick="unlockStep(6)">Selesai Membaca Bab 5 & Lanjut ➔</button>
        </div>

        <!-- STEP 6 -->
        <div id="step-6" class="step-section step-locked">
            <span id="badge-6" class="lock-badge">🔒 Terkunci (Selesaikan Bab 5 Dulu)</span>
            <h3>6. Laporan Keuangan SAK-EMKM</h3>
            <p>Komponen laporan keuangan utama mencakup: Laporan Laba Rugi (Kinerja), Laporan Perubahan Modal, Laporan Posisi Keuangan (Neraca), Laporan Arus Kas, dan Catatan Atas Laporan Keuangan (CALK).</p>
            <p style="color:var(--primary); font-weight:bold; margin-top:10px;">🎉 Selamat! Anda telah menyelesaikan seluruh urutan materi Bab 4 dengan tuntas.</p>
        </div>
    </div>

    <!-- TAB 3: 10 CHALLENGE & LABIRIN BINTANG -->
    <div id="game" class="tab-content">
        <h2>🕹️ Game Edukasi: 10 Challenge & Labirin Bintang</h2>
        <p>Uji kecepatan dan ketepatan Anda dalam 10 tantangan akuntansi, lalu mainkan game labirin!</p>

        <!-- 10 CHALLENGE -->
        <div class="game-card">
            <h3>🎯 10 Challenge Kilat Akuntansi</h3>
            <div id="challenge-container" style="margin-top:10px;">
                <p id="chal-question" style="font-weight:600; font-size:0.88rem;"></p>
                <div id="chal-options" style="display:flex; flex-direction:column; gap:5px; margin-top:8px;"></div>
                <p id="chal-feedback" style="margin-top:8px; font-weight:bold; font-size:0.85rem;"></p>
            </div>
        </div>

        <!-- MAZE GAME -->
        <div class="game-card" style="background:linear-gradient(135deg, #fef3c7, #fde68a); text-align:center;">
            <h3>🧩 Labirin Akuntansi Berbintang</h3>
            <p style="font-size:0.8rem; color:#b45309;">Pandu ikon 💰 ke kotak FINIS 🏁 secepat mungkin untuk meraih Bintang 5!</p>
            <p id="maze-timer" style="font-weight:bold; font-size:0.9rem; margin-top:5px;">Waktu: 0 detik</p>
            
            <div id="maze-board"></div>
            
            <div class="controls-grid" style="margin-top:10px;">
                <div></div>
                <button class="ctrl-btn" onclick="movePlayer(0, -1)">⬆️</button>
                <div></div>
                <button class="ctrl-btn" onclick="movePlayer(-1, 0)">⬅️</button>
                <button class="ctrl-btn" onclick="movePlayer(0, 1)">⬇️</button>
                <button class="ctrl-btn" onclick="movePlayer(1, 0)">➡️</button>
            </div>
            <div id="maze-result" style="margin-top:10px; font-weight:bold; font-size:0.95rem;"></div>
        </div>
    </div>

    <!-- TAB 4: LKPD INTERAKTIF LANGSUNG -->
    <div id="lkpd" class="tab-content">
        <h2>📋 LKPD Interaktif: Studi Kasus Kasir</h2>
        <p>Isi tabel persamaan dasar akuntansi di bawah ini berdasarkan transaksi: Setor modal Kas Rp10.000.000 dan Peralatan Rp5.000.000.</p>

        <div class="card">
            <div class="card-title">Lembar Kerja Hitung Saldo:</div>
            <table style="margin-top:10px;">
                <tr><th>Komponen Akun</th><th>Masukkan Nilai (Rp)</th></tr>
                <tr><td>Kas</td><td><input type="number" id="lk-kas" class="lkpd-input" placeholder="0"></td></tr>
                <tr><td>Peralatan</td><td><input type="number" id="lk-peralatan" class="lkpd-input" placeholder="0"></td></tr>
                <tr><td>Modal Pemilik</td><td><input type="number" id="lk-modal" class="lkpd-input" placeholder="0"></td></tr>
            </table>
            <button class="btn-submit" onclick="checkLkpd()" style="margin-top:10px; padding:10px;">Validasi Jawaban LKPD</button>
            <div id="lkpd-feedback" style="margin-top:10px; font-weight:bold; text-align:center;"></div>
        </div>
    </div>

    <!-- TAB 5: ASESMEN PILIHAN GANDA (A-E) -->
    <div id="asesmen" class="tab-content">
        <h2>✍️ Asesmen Sumatif (20 Soal Pilihan Ganda A - E)</h2>
        <p style="margin-bottom: 15px;">Pilihlah salah satu jawaban yang paling tepat (A, B, C, D, atau E)!</p>

        <form id="quiz-form">
            <!-- SOAL 1-20 DENGAN OPSI A-E -->
            <div class="question-card">
                <div class="question-title">1. Akuntansi sering dijuluki sebagai "language of business" karena...</div>
                <label class="option-label"><input type="radio" name="q1" value="A"> A. Menggunakan bahasa internasional resmi</label>
                <label class="option-label"><input type="radio" name="q1" value="B"> B. Menyediakan informasi keuangan untuk dasar pengambilan keputusan</label>
                <label class="option-label"><input type="radio" name="q1" value="C"> C. Menggunakan rumus matematik yang sangat rumit</label>
                <label class="option-label"><input type="radio" name="q1" value="D"> D. Hanya dipahami oleh kalangan akuntan publik</label>
                <label class="option-label"><input type="radio" name="q1" value="E"> E. Wajib dicatat menggunakan mata uang asing</label>
            </div>

            <div class="question-card">
                <div class="question-title">2. Diterima pendapatan jasa secara tunai sebesar Rp5.000.000. Pengaruhnya dalam persamaan dasar akuntansi adalah...</div>
                <label class="option-label"><input type="radio" name="q2" value="A"> A. Kas bertambah dan Utang bertambah</label>
                <label class="option-label"><input type="radio" name="q2" value="B"> B. Kas bertambah dan Modal bertambah</label>
                <label class="option-label"><input type="radio" name="q2" value="C"> C. Kas bertambah dan Piutang berkurang</label>
                <label class="option-label"><input type="radio" name="q2" value="D"> D. Kas berkurang dan Modal berkurang</label>
                <label class="option-label"><input type="radio" name="q2" value="E"> E. Peralatan bertambah dan Kas berkurang</label>
            </div>

            <div class="question-card">
                <div class="question-title">3. Dibeli peralatan seharga Rp8.000.000, baru dibayar tunai Rp3.000.000 dan sisanya dibayar kredit. Pencatatan yang tepat adalah...</div>
                <label class="option-label"><input type="radio" name="q3" value="A"> A. Peralatan (+) Rp8jt, Kas (-) Rp8jt</label>
                <label class="option-label"><input type="radio" name="q3" value="B"> B. Peralatan (+) Rp8jt, Kas (-) Rp3jt, Utang (+) Rp5jt</label>
                <label class="option-label"><input type="radio" name="q3" value="C"> C. Peralatan (+) Rp8jt, Utang (+) Rp8jt</label>
                <label class="option-label"><input type="radio" name="q3" value="D"> D. Kas (+) Rp8jt, Peralatan (-) Rp8jt</label>
                <label class="option-label"><input type="radio" name="q3" value="E"> E. Peralatan (-) Rp8jt, Utang (-) Rp8jt</label>
            </div>

            <div class="question-card">
                <div class="question-title">4. Bukti transaksi atas penjualan barang atau jasa secara kredit dinamakan...</div>
                <label class="option-label"><input type="radio" name="q4" value="A"> A. Kuitansi</label>
                <label class="option-label"><input type="radio" name="q4" value="B"> B. Nota Kontan</label>
                <label class="option-label"><input type="radio" name="q4" value="C"> C. Faktur</label>
                <label class="option-label"><input type="radio" name="q4" value="D"> D. Cek Bank</label>
                <label class="option-label"><input type="radio" name="q4" value="E"> E. Nota Debit</label>
            </div>

            <div class="question-card">
                <div class="question-title">5. Kelompok Akun Riil (Laporan Posisi Keuangan / Neraca) terdiri dari...</div>
                <label class="option-label"><input type="radio" name="q5" value="A"> A. Kas, Piutang, dan Utang Usaha</label>
                <label class="option-label"><input type="radio" name="q5" value="B"> B. Pendapatan Jasa dan Beban Gaji</label>
                <label class="option-label"><input type="radio" name="q5" value="C"> C. Beban Sewa dan Kas</label>
                <label class="option-label"><input type="radio" name="q5" value="D"> D. Pendapatan Bunga dan Prive</label>
                <label class="option-label"><input type="radio" name="q5" value="E"> E. Ikhtisar Laba Rugi</label>
            </div>

            <div class="question-card">
                <div class="question-title">6. Data keuangan: Pendapatan Rp20jt, Beban Gaji Rp5jt, Beban Sewa Rp3jt. Besarnya Laba Bersih adalah...</div>
                <label class="option-label"><input type="radio" name="q6" value="A"> A. Rp20.000.000</label>
                <label class="option-label"><input type="radio" name="q6" value="B"> B. Rp12.000.000</label>
                <label class="option-label"><input type="radio" name="q6" value="C"> C. Rp8.000.000</label>
                <label class="option-label"><input type="radio" name="q6" value="D"> D. Rp15.000.000</label>
                <label class="option-label"><input type="radio" name="q6" value="E"> E. Rp28.000.000</label>
            </div>

            <div class="question-card">
                <div class="question-title">7. Bukti transaksi internal yang dibuat pimpinan perusahaan untuk bagian akuntansi disebut...</div>
                <label class="option-label"><input type="radio" name="q7" value="A"> A. Cek</label>
                <label class="option-label"><input type="radio" name="q7" value="B"> B. Memo</label>
                <label class="option-label"><input type="radio" name="q7" value="C"> C. Nota Kredit</label>
                <label class="option-label"><input type="radio" name="q7" value="D"> D. Faktur Penjualan</label>
                <label class="option-label"><input type="radio" name="q7" value="E"> E. Kuitansi Pembayaran</label>
            </div>

            <div class="question-card">
                <div class="question-title">8. Pembayaran utang usaha kepada kreditur secara tunai akan mengakibatkan...</div>
                <label class="option-label"><input type="radio" name="q8" value="A"> A. Kas berkurang dan Utang berkurang</label>
                <label class="option-label"><input type="radio" name="q8" value="B"> B. Kas bertambah dan Utang berkurang</label>
                <label class="option-label"><input type="radio" name="q8" value="C"> C. Kas berkurang dan Modal berkurang</label>
                <label class="option-label"><input type="radio" name="q8" value="D"> D. Kas bertambah dan Modal bertambah</label>
                <label class="option-label"><input type="radio" name="q8" value="E"> E. Utang bertambah dan Modal berkurang</label>
            </div>

            <div class="question-card">
                <div class="question-title">9. Saldo Perlengkapan Rp2.000.000, sisa fisik akhir periode Rp700.000. Jurnal penyesuaian mencatatkan Beban Perlengkapan sebesar...</div>
                <label class="option-label"><input type="radio" name="q9" value="A"> A. Rp2.000.000</label>
                <label class="option-label"><input type="radio" name="q9" value="B"> B. Rp1.300.000</label>
                <label class="option-label"><input type="radio" name="q9" value="C"> C. Rp700.000</label>
                <label class="option-label"><input type="radio" name="q9" value="D"> D. Rp2.700.000</label>
                <label class="option-label"><input type="radio" name="q9" value="E"> E. Rp1.500.000</label>
            </div>

            <div class="question-card">
                <div class="question-title">10. Pengambilan kas perusahaan untuk keperluan pribadi pemilik dinamakan...</div>
                <label class="option-label"><input type="radio" name="q10" value="A"> A. Beban Pribadi</label>
                <label class="option-label"><input type="radio" name="q10" value="B"> B. Prive</label>
                <label class="option-label"><input type="radio" name="q10" value="C"> C. Utang Pemilik</label>
                <label class="option-label"><input type="radio" name="q10" value="D"> D. Modal Tambahan</label>
                <label class="option-label"><input type="radio" name="q10" value="E"> E. Investasi Netto</label>
            </div>

            <div class="question-card">
                <div class="question-title">11. Akun yang termasuk ke dalam kelompok akun sementara dan ditutup pada akhir periode adalah...</div>
                <label class="option-label"><input type="radio" name="q11" value="A"> A. Pendapatan, Beban, dan Prive</label>
                <label class="option-label"><input type="radio" name="q11" value="B"> B. Kas, Perlengkapan, dan Modal</label>
                <label class="option-label"><input type="radio" name="q11" value="C"> C. Peralatan dan Utang Usaha</label>
                <label class="option-label"><input type="radio" name="q11" value="D"> D. Akumulasi Penyusutan</label>
                <label class="option-label"><input type="radio" name="q11" value="E"> E. Piutang Usaha</label>
            </div>

            <div class="question-card">
                <div class="question-title">12. Laporan keuangan yang menyajikan saldo Aset, Liabilitas, dan Ekuitas pada tanggal tertentu adalah...</div>
                <label class="option-label"><input type="radio" name="q12" value="A"> A. Laporan Laba Rugi</label>
                <label class="option-label"><input type="radio" name="q12" value="B"> B. Laporan Posisi Keuangan (Neraca)</label>
                <label class="option-label"><input type="radio" name="q12" value="C"> C. Laporan Arus Kas</label>
                <label class="option-label"><input type="radio" name="q12" value="D"> D. Laporan Perubahan Ekuitas</label>
                <label class="option-label"><input type="radio" name="q12" value="E"> E. Jurnal Penutup</label>
            </div>

            <div class="question-card">
                <div class="question-title">13. Diterima pelunasan piutang dari pelanggan sebesar Rp2.000.000. Pengaruhnya adalah...</div>
                <label class="option-label"><input type="radio" name="q13" value="A"> A. Kas bertambah dan Piutang berkurang</label>
                <label class="option-label"><input type="radio" name="q13" value="B"> B. Kas bertambah dan Modal bertambah</label>
                <label class="option-label"><input type="radio" name="q13" value="C"> C. Piutang bertambah dan Utang berkurang</label>
                <label class="option-label"><input type="radio" name="q13" value="D"> D. Kas berkurang dan Piutang bertambah</label>
                <label class="option-label"><input type="radio" name="q13" value="E"> E. Kas bertambah dan Utang bertambah</label>
            </div>

            <div class="question-card">
                <div class="question-title">14. Konsep akuntansi yang mengharuskan pemisahan tegas antara kekayaan pribadi pemilik dan kekayaan perusahaan adalah...</div>
                <label class="option-label"><input type="radio" name="q14" value="A"> A. Kelangsungan Usaha</label>
                <label class="option-label"><input type="radio" name="q14" value="B"> B. Entitas Ekonomi (*Economic Entity*)</label>
                <label class="option-label"><input type="radio" name="q14" value="C"> C. Satuan Moneter</label>
                <label class="option-label"><input type="radio" name="q14" value="D"> D. Periode Akuntansi</label>
                <label class="option-label"><input type="radio" name="q14" value="E"> E. Konsistensi</label>
            </div>

            <div class="question-card">
                <div class="question-title">15. Jurnal khusus yang digunakan secara spesifik untuk mencatat transaksi penjualan barang dagang secara kredit adalah...</div>
                <label class="option-label"><input type="radio" name="q15" value="A"> A. Jurnal Penerimaan Kas</label>
                <label class="option-label"><input type="radio" name="q15" value="B"> B. Jurnal Penjualan</label>
                <label class="option-label"><input type="radio" name="q15" value="C"> C. Jurnal Umum</label>
                <label class="option-label"><input type="radio" name="q15" value="D"> D. Jurnal Pembelian</label>
                <label class="option-label"><input type="radio" name="q15" value="E"> E. Jurnal Pengeluaran Kas</label>
            </div>

            <div class="question-card">
                <div class="question-title">16. Diketahui Total Aset perusahaan Rp85.000.000 dan Total Liabilitas Rp25.000.000. Besarnya Ekuitas adalah...</div>
                <label class="option-label"><input type="radio" name="q16" value="A"> A. Rp110.000.000</label>
                <label class="option-label"><input type="radio" name="q16" value="B"> B. Rp60.000.000</label>
                <label class="option-label"><input type="radio" name="q16" value="C"> C. Rp25.000.000</label>
                <label class="option-label"><input type="radio" name="q16" value="D"> D. Rp85.000.000</label>
                <label class="option-label"><input type="radio" name="q16" value="E"> E. Rp50.000.000</label>
            </div>

            <div class="question-card">
                <div class="question-title">17. Proses pemindahan catatan informasi dari Jurnal Umum ke masing-masing buku besar disebut...</div>
                <label class="option-label"><input type="radio" name="q17" value="A"> A. Posting</label>
                <label class="option-label"><input type="radio" name="q17" value="B"> B. Ikhtisar</label>
                <label class="option-label"><input type="radio" name="q17" value="C"> C. Penyesuaian</label>
                <label class="option-label"><input type="radio" name="q17" value="D"> D. Closing</label>
                <label class="option-label"><input type="radio" name="q17" value="E"> E. Reversing</label>
            </div>

            <div class="question-card">
                <div class="question-title">18. Bukti penerimaan kembali barang yang telah dijual secara kredit (retur penjualan) bagi pihak penjual dinamakan...</div>
                <label class="option-label"><input type="radio" name="q18" value="A"> A. Nota Kredit</label>
                <label class="option-label"><input type="radio" name="q18" value="B"> B. Nota Debit</label>
                <label class="option-label"><input type="radio" name="q18" value="C"> C. Faktur Penjualan</label>
                <label class="option-label"><input type="radio" name="q18" value="D"> D. Kuitansi</label>
                <label class="option-label"><input type="radio" name="q18" value="E"> E. Nota Kontan</label>
            </div>

            <div class="question-card">
                <div class="question-title">19. Modal Awal Rp10.000.000, Laba Bersih Rp2.000.000, dan Prive Rp500.000. Besarnya Modal Akhir adalah...</div>
                <label class="option-label"><input type="radio" name="q19" value="A"> A. Rp12.500.000</label>
                <label class="option-label"><input type="radio" name="q19" value="B"> B. Rp11.500.000</label>
                <label class="option-label"><input type="radio" name="q19" value="C"> C. Rp8.000.000</label>
                <label class="option-label"><input type="radio" name="q19" value="D"> D. Rp10.000.000</label>
                <label class="option-label"><input type="radio" name="q19" value="E"> E. Rp12.000.000</label>
            </div>

            <div class="question-card">
                <div class="question-title">20. Jurnal yang dibuat pada awal periode berikutnya untuk membalik penyesuaian tertentu dinamakan...</div>
                <label class="option-label"><input type="radio" name="q20" value="A"> A. Jurnal Penutup</label>
                <label class="option-label"><input type="radio" name="q20" value="B"> B. Jurnal Pembalik</label>
                <label class="option-label"><input type="radio" name="q20" value="C"> C. Jurnal Khusus</label>
                <label class="option-label"><input type="radio" name="q20" value="D"> D. Jurnal Penyesuaian</label>
                <label class="option-label"><input type="radio" name="q20" value="E"> E. Jurnal Pemula</label>
            </div>

            <button type="button" class="btn-submit" onclick="submitQuiz()">Kirim Jawaban & Cek Hasil</button>
        </form>

        <div id="score-box" class="score-box">
            <h3>Hasil Asesmen Anda:</h3>
            <div id="score-number" class="score-number">0</div>
            <p id="score-text">Status: Selesai</p>
        </div>
    </div>

    <footer>
        &copy; 2026 MAN 1 Lampung Timur • Devy Septianasari, S.Pd.<br>
        <i>Modul Pembelajaran Interaktif Berbasis Mobile-First</i>
    </footer>
</div>

<script>
    // TAB NAVIGATOR
    function openTab(evt, tabName) {
        let contents = document.getElementsByClassName("tab-content");
        for (let i = 0; i < contents.length; i++) contents[i].classList.remove("active");
        let buttons = document.getElementsByClassName("nav-btn");
        for (let i = 0; i < buttons.length; i++) buttons[i].classList.remove("active");
        document.getElementById(tabName).classList.add("active");
        evt.currentTarget.classList.add("active");
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // STEP UNLOCK SYSTEM
    function unlockStep(stepNum) {
        let target = document.getElementById("step-" + stepNum);
        if(target) {
            target.classList.remove("step-locked");
            let badge = document.getElementById("badge-" + stepNum);
            if(badge) {
                badge.className = "unlock-badge";
                badge.innerText = "✔ Bab " + stepNum + " (Terbuka)";
            }
            target.scrollIntoView({ behavior: 'smooth' });
        }
    }

    // 10 CHALLENGE ENGINE
    const challenges = [
        { q: "1. Saldo normal akun Beban adalah...", opts: ["Debit", "Kredit", "Utang"], ans: 0 },
        { q: "2. Aset = Liabilitas + ...", opts: ["Modal", "Beban", "Pendapatan"], ans: 0 },
        { q: "3. Bukti transaksi pembelian tunai disebut...", opts: ["Faktur", "Nota Kontan", "Memo"], ans: 1 },
        { q: "4. Pengambilan pribadi oleh pemilik disebut...", opts: ["Prive", "Deviden", "Modal"], ans: 0 },
        { q: "5. Pendapatan jasa diterima tunai menambah...", opts: ["Kas", "Utang", "Beban"], ans: 0 },
        { q: "6. Pembelian perlengkapan kredit menambah...", opts: ["Kas", "Utang Usaha", "Prive"], ans: 1 },
        { q: "7. Akun yang dicatat di sisi kiri disebut...", opts: ["Debit", "Kredit", "Saldo"], ans: 0 },
        { q: "8. Laporan yang menyajikan posisi aset dan utang adalah...", opts: ["Laba Rugi", "Neraca", "Arus Kas"], ans: 1 },
        { q: "9. Proses memindahkan jurnal ke buku besar disebut...", opts: ["Posting", "Closing", "Adjusting"], ans: 0 },
        { q: "10. Sisa perlengkapan akhir periode dicatat sebagai...", opts: ["Beban", "Aset", "Modal"], ans: 1 }
    ];
    let currentChal = 0;

    function loadChallenge() {
        if(currentChal >= challenges.length) {
            document.getElementById("challenge-container").innerHTML = "<p style='color:var(--primary); font-weight:bold; text-align:center;'>🎉 Luar biasa! Anda telah menuntaskan 10 Challenge Akuntansi.</p>";
            return;
        }
        let c = challenges[currentChal];
        document.getElementById("chal-question").innerText = c.q;
        let optDiv = document.getElementById("chal-options");
        optDiv.innerHTML = "";
        c.opts.forEach((opt, idx) => {
            let btn = document.createElement("button");
            btn.className = "nav-btn";
            btn.style.width = "100%";
            btn.style.textAlign = "left";
            btn.innerText = opt;
            btn.onclick = () => checkChallenge(idx, c.ans);
            optDiv.appendChild(btn);
        });
    }

    function checkChallenge(selected, correct) {
        let fb = document.getElementById("chal-feedback");
        if(selected === correct) {
            fb.style.color = "green";
            fb.innerText = "✔ Benar! Lanjut tantangan berikutnya.";
            currentChal++;
            setTimeout(() => { fb.innerText = ""; loadChallenge(); }, 1000);
        } else {
            fb.style.color = "red";
            fb.innerText = "❌ Kurang tepat, coba lagi!";
        }
    }
    loadChallenge();

    // MAZE GAME ENGINE
    let maze = [
        [1, 0, 1, 1, 1],
        [1, 0, 0, 0, 1],
        [1, 1, 1, 0, 1],
        [0, 0, 0, 0, 2],
        [0, 1, 1, 1, 1]
    ]; // 0: path, 1: wall, 2: goal (Start at 0,0)
    let pX = 0, pY = 0;
    let seconds = 0, timerInterval = null, gameStarted = false;

    function initMaze() {
        pX = 0; pY = 0; seconds = 0; gameStarted = true;
        if(timerInterval) clearInterval(timerInterval);
        timerInterval = setInterval(() => { seconds++; document.getElementById("maze-timer").innerText = "Waktu: " + seconds + " detik"; }, 1000);
        renderMaze();
    }

    function renderMaze() {
        let board = document.getElementById("maze-board");
        board.innerHTML = "";
        for(let r=0; r<5; r++) {
            for(let c=0; c<5; c++) {
                let cell = document.createElement("div");
                cell.className = "maze-cell";
                if(r === pX && c === pY) {
                    cell.className += " maze-player";
                    cell.innerText = "💰";
                } else if(r === 3 && c === 4) {
                    cell.className += " maze-goal";
                    cell.innerText = "🏁";
                } else if(maze[r][c] === 1) {
                    cell.className += " maze-wall";
                }
                board.appendChild(cell);
            }
        }
    }

    function movePlayer(dx, dy) {
        if(!gameStarted) return;
        let nx = pX + dx;
        let ny = pY + dy;
        if(nx >= 0 && nx < 5 && ny >= 0 && ny < 5 && maze[nx][ny] !== 1) {
            pX = nx; pY = ny;
            renderMaze();
            if(pX === 3 && pY === 4) {
                clearInterval(timerInterval);
                gameStarted = false;
                let stars = seconds <= 10 ? "⭐⭐⭐⭐⭐ (Bintang 5)" : (seconds <= 20 ? "⭐⭐⭐⭐ (Bintang 4)" : "⭐⭐⭐ (Bintang 3)");
                document.getElementById("maze-result").innerHTML = `🎉 Menang dalam ${seconds} detik! Perolehan: ${stars}`;
            }
        }
    }
    initMaze();

    // LKPD VALIDATOR
    function checkLkpd() {
        let kas = parseInt(document.getElementById("lk-kas").value) || 0;
        let peralatan = parseInt(document.getElementById("lk-peralatan").value) || 0;
        let modal = parseInt(document.getElementById("lk-modal").value) || 0;
        let fb = document.getElementById("lkpd-feedback");

        if(kas === 10000000 && peralatan === 5000000 && modal === 15000000) {
            fb.style.color = "green";
            fb.innerText = "✔ TEPAT SEKALI! Sisi Aset (Rp15jt) seimbang dengan Modal (Rp15jt).";
        } else {
            fb.style.color = "red";
            fb.innerText = "❌ Belum Tepat. Periksa kembali setoran modal Kas dan Peralatan!";
        }
    }

    // ASESMEN SUBMIT (A-E)
    function submitQuiz() {
        const key = {
            q1: "B", q2: "B", q3: "B", q4: "C", q5: "A",
            q6: "B", q7: "B", q8: "A", q9: "B", q10: "B",
            q11: "A", q12: "B", q13: "A", q14: "B", q15: "B",
            q16: "B", q17: "A", q18: "A", q19: "B", q20: "B"
        };
        let correct = 0, total = 20;
        for (let i = 1; i <= total; i++) {
            let selected = document.querySelector(`input[name="q${i}"]:checked`);
            if (selected && selected.value === key[`q${i}`]) correct++;
        }
        let finalScore = (correct / total) * 100;
        let scoreBox = document.getElementById("score-box");
        scoreBox.style.display = "block";
        document.getElementById("score-number").innerText = finalScore.toFixed(0);
        document.getElementById("score-text").innerHTML = finalScore >= 75 ? `<b>Tuntas!</b> Benar ${correct} dari ${total}. SANGAT BAIK! 🎉` : `Benar ${correct} dari ${total}. Silakan pelajari ulang materi! 💪`;
        scoreBox.scrollIntoView({ behavior: 'smooth' });
    }
</script>

</body>
</html>
