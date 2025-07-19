graph TD
    subgraph Tahapan Proses
        direction LR
        T1("1. Penemuan & Kelayakan") --> T2("2. Pengajuan") --> T3("3. Persetujuan & Pencairan") --> T4("4. Onboarding & Pengelolaan Usaha") --> T5("5. Pembayaran & Pertumbuhan")
    end

    subgraph Aksi Nasabah (Frontstage)
        direction LR
        A1("Melihat banner di Livin' & menekan tombol 'Cek Kelayakan'") --> A2("Mengisi form digital & mengunggah dokumen (KTP, KTM/Ijazah)") --> A3("Meninjau & menyetujui perjanjian kredit via PIN Livin'") --> A4("Menerima notifikasi & mulai menggunakan Livin' Merchant untuk menerima pembayaran") --> A5("Menerima notifikasi auto-debit & memantau performa bisnis")
    end

    subgraph Titik Interaksi & Aksi Bank Terlihat (Frontstage)
        direction LR
        B1("Banner promosi di beranda Livin'<br>Halaman penjelasan produk<br>Notifikasi hasil kelayakan instan") --> B2("Formulir pengajuan digital<br>Notifikasi 'Pengajuan Diterima'") --> B3("Halaman Perjanjian Kredit Digital<br>Notifikasi 'Pinjaman Disetujui & Dicairkan'") --> B4("Notifikasi 'Akun Livin' Merchant Aktif'<br>Dasbor Livin' Merchant di dalam aplikasi Livin'") --> B5("Notifikasi pengingat & bukti potong cicilan<br>Grafik performa penjualan di dasbor")
    end

    subgraph Aksi Bank Tak Terlihat (Backstage)
        direction LR
        C1("Sistem melakukan pre-scoring otomatis berdasarkan data internal (saldo, total aset)") --> C2("Sistem menjalankan algoritma credit scoring utama<br>Verifikasi data via API (Dukcapil, PDDikti)") --> C3("Sistem memicu pencairan dana<br><i>(Jika perlu)</i> Analis Kredit melakukan verifikasi manual") --> C4("API otomatis membuat akun Livin' Merchant & QRIS<br>Data transaksi merchant mulai direkam") --> C5("Sistem auto-debit menjalankan pembayaran cicilan<br>Sistem menganalisis data penjualan untuk penawaran di masa depan")
    end

    subgraph Proses Pendukung (Support Systems)
        direction LR
        D1("Core Banking System<br>CRM untuk segmentasi<br>Algoritma Pre-Scoring") --> D2("Credit Scoring Engine<br>Koneksi API Eksternal<br>Sistem Manajemen Dokumen") --> D3("Loan Origination System<br>Sistem Manajemen Risiko<br>SOP Verifikasi Manual") --> D4("Platform Livin' Merchant<br>Sistem Data Analytics") --> D5("Core Banking System (Auto-Debit)<br>Algoritma Penawaran Produk Lanjutan")
    end

    classDef stage fill:#E1EEF3,stroke:#333,stroke-width:2px,color:#333
    classDef front fill:#FFFFFF,stroke:#003366,stroke-width:2px,color:#003366
    classDef back fill:#F0F4F7,stroke:#00529B,stroke-width:2px,color:#00529B
    classDef support fill:#D6EAF8,stroke:#0073B2,stroke-width:1px,color:#0073B2

    class T1,T2,T3,T4,T5 stage
    class A1,A2,A3,A4,A5 front
    class B1,B2,B3,B4,B5 front
    class C1,C2,C3,C4,C5 back
    class D1,D2,D3,D4,D5 support
