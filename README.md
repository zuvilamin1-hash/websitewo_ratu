<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sanggar Rias Ratu • Paket Sewa Kuwadi & Job Rias Profesional</title>

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            'ratu-green':'#0b5a3a',
            'ratu-deep-red':'#7a1414',
            'ratu-red':'#c62828'
          }
        }
      }
    }
  </script>
  <!-- Alpine.js for small interactivity -->
  <script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    body{
      font-family:'Poppins',system-ui,Arial,Helvetica,sans-serif;
      background:linear-gradient(180deg,#fff 0%,#f7faf7 100%);
    }
    body.dark{
      background:radial-gradient(circle at top,#1f2933 0%,#020617 60%);
      color:#e5e7eb;
    }
    .accent-btn{background:linear-gradient(90deg,#7a1414,#c62828);} /* deep-red to red */
    .card{transition:transform .18s ease, box-shadow .18s ease}
    .card:hover{transform:translateY(-6px); box-shadow:0 10px 30px rgba(11,90,58,0.35)}
    @media print{
      body{background:#fff;color:#000;}
      header, footer, #booking, #galeri, #testimoni{display:none !important;}
      #paket, #harga{margin-top:0 !important;}
      a[href]:after{content:"" !important;}
    }
  </style>
</head>
<body x-data="{ dark:false }" :class="dark ? 'dark bg-slate-950 text-slate-100' : 'text-gray-800'" class="transition-colors duration-300">

  <!-- Navbar -->
  <header class="shadow sticky top-0 z-50"
  :class="dark ? 'bg-slate-900 text-white' : 'bg-white text-gray-800'">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <button @click="dark = !dark"
  class="hidden md:inline-flex items-center text-xs px-3 py-1 rounded-full border mr-4"
  :class="dark ? 'border-gray-400 text-gray-100' : 'border-gray-400 text-gray-700'">
  <span x-show="!dark">🌙 Dark</span>
  <span x-show="dark">☀️ Light</span>
</button>
        <div class="flex items-center gap-3">
          <div class="w-12 h-12 rounded-full bg-[linear-gradient(180deg,#0b5a3a,#06422a)] flex items-center justify-center text-white font-bold">RR</div>
          <div>
              <a href="#home"
     class="text-lg font-semibold"
     :class="dark ? 'text-white' : 'text-ratu-green'">
     Sanggar Rias Ratu
  </a>
  <div class="text-xs"
       :class="dark ? 'text-gray-300' : 'text-gray-500'">
    Sidayu — Gresik • Rias & Sewa Kuwadi Profesional
  </div>
</div>
        <nav class="hidden md:flex items-center gap-4">
  <a href="#paket"
     class="nav-link px-3 py-2 rounded"
     :class="dark ? 'text-gray-100 hover:bg-slate-800' : 'text-ratu-green hover:bg-slate-900 hover:text-white'">
    Paket
  </a>
  <a href="#galeri"
     class="nav-link px-3 py-2 rounded"
     :class="dark ? 'text-gray-100 hover:bg-slate-800' : 'text-ratu-green hover:bg-slate-900 hover:text-white'">
    Galeri
  </a>
  <a href="#harga"
     class="nav-link px-3 py-2 rounded"
     :class="dark ? 'text-gray-100 hover:bg-slate-800' : 'text-ratu-green hover:bg-slate-900 hover:text-white'">
    Harga
  </a>
  <a href="#testimoni"
     class="nav-link px-3 py-2 rounded"
     :class="dark ? 'text-gray-100 hover:bg-slate-800' : 'text-ratu-green hover:bg-slate-900 hover:text-white'">
    Testimoni
  </a>
  <a href="#kontak"
     class="nav-link px-3 py-2 rounded"
     :class="dark ? 'text-gray-100 hover:bg-slate-800' : 'text-ratu-green hover:bg-slate-900 hover:text-white'">
    Kontak
  </a>
  <a href="#booking"
     class="px-4 py-2 rounded text-white font-semibold"
     style="background:linear-gradient(90deg,#0b5a3a,#06422a);">
    Booking
  </a>
</nav>

        <!-- Mobile hamburger -->
        <div class="md:hidden" x-data="{open:false}">
          <button @click="open = !open" class="p-2 rounded-md focus:outline-none">
            <svg x-show="!open" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" /></svg>
            <svg x-show="open" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" /></svg>
          </button>

          <div
  x-show="open"
  x-transition
  class="absolute right-4 left-4 mt-2 border rounded-lg shadow-lg p-4"
  :class="dark ? 'bg-slate-900 text-white border-slate-700' : 'bg-white text-gray-800 border-gray-200'">
  <a href="#paket" class="block py-2">Paket</a>
  <a href="#galeri" class="block py-2">Galeri</a>
  <a href="#harga" class="block py-2">Harga</a>
  <a href="#kontak" class="block py-2">Kontak</a>
  <a href="#booking"
     class="block mt-3 px-4 py-2 rounded text-white text-center"
     style="background:linear-gradient(90deg,#0b5a3a,#06422a);">
    Booking
  </a>
</div>

      </div>
    </div>
  </header>

  <!-- Hero -->
  <main id="home" class="pt-10 pb-16">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
        <div>
          <h1 class="text-3xl sm:text-4xl font-bold text-ratu-green">Sanggar Rias Ratu</h1>
          <p class="mt-3 text-gray-700">Profesional dalam rias pengantin, rias acara, serta layanan sewa kuwadi terbaik di Sidayu — Gresik. Pelayanan hangat, makeup tahan lama, & penataan rapi sesuai adat.</p>

          <div class="mt-6 flex flex-wrap gap-3">
            <a href="#paket" class="inline-block px-5 py-3 rounded-lg font-semibold text-white" style="background:linear-gradient(90deg,#7a1414,#c62828);">Lihat Paket</a>
            <a href="#galeri" class="inline-block px-5 py-3 rounded-lg font-semibold border border-ratu-green text-ratu-green">Lihat Galeri</a>
          </div>

          <ul class="mt-6 text-sm text-gray-600 space-y-2">
            <li><strong>Alamat:</strong> Jl. Pelita III, Desa Asempapak, Sidayu, Gresik.</li>
            <li><strong>Jam Operasional:</strong> 08.00 - 21.00 WIB (Sen-Sab)</li>
          </ul>
        </div>

        <div class="bg-white border rounded-lg p-4 shadow-sm overflow-hidden">
  <!-- Wrapper slider -->
  <div class="relative w-full h-56 overflow-hidden rounded-lg bg-black/5 flex items-center justify-center">
    <!-- Track slider -->
    <div id="sliderTrack"
         class="flex w-[600%] h-full transition-transform duration-700 ease-out items-center">
      <!-- 6 slide: semua pakai object-contain -->
      <div class="w-full h-full flex-shrink-0 flex items-center justify-center">
        <img src="images/foto1.jpg"
             alt="Rias Pengantin 1"
             class="max-w-full max-h-full object-contain" />
      </div>
      <div class="w-full h-full flex-shrink-0 flex items-center justify-center">
        <img src="images/foto2.jpg"
             alt="Rias Pengantin 2"
             class="max-w-full max-h-full object-contain" />
      </div>
      <div class="w-full h-full flex-shrink-0 flex items-center justify-center">
        <img src="images/foto3.jpg"
             alt="Rias Pengantin 3"
             class="max-w-full max-h-full object-contain" />
      </div>
      <div class="w-full h-full flex-shrink-0 flex items-center justify-center">
        <img src="images/foto4.jpg"
             alt="Rias Pengantin 4"
             class="max-w-full max-h-full object-contain" />
      </div>
      <div class="w-full h-full flex-shrink-0 flex items-center justify-center">
        <img src="images/foto5.jpg"
             alt="Rias Pengantin 5"
             class="max-w-full max-h-full object-contain" />
      </div>
      <div class="w-full h-full flex-shrink-0 flex items-center justify-center">
        <img src="images/foto6.jpg"
             alt="Rias Pengantin 6"
             class="max-w-full max-h-full object-contain" />
      </div>
    </div>

    <!-- Bullets indikator -->
    <div class="absolute bottom-2 left-1/2 -translate-x-1/2 flex gap-2">
      <button class="w-2.5 h-2.5 rounded-full bg-white/70" data-slide="0"></button>
      <button class="w-2.5 h-2.5 rounded-full bg-white/40" data-slide="1"></button>
      <button class="w-2.5 h-2.5 rounded-full bg-white/40" data-slide="2"></button>
      <button class="w-2.5 h-2.5 rounded-full bg-white/40" data-slide="3"></button>
      <button class="w-2.5 h-2.5 rounded-full bg-white/40" data-slide="4"></button>
      <button class="w-2.5 h-2.5 rounded-full bg-white/40" data-slide="5"></button>
    </div>
  </div>

  <div class="mt-4">
    <h3 class="font-semibold text-ratu-green"
        :class="dark ? 'text-ratu-green' : 'text-ratu-green'">
      Siap Melayani
    </h3>
    <p class="text-sm mt-1"
       :class="dark ? 'text-gray-300' : 'text-gray-600'">
      Dokumentasi hasil rias pengantin, rias acara, dan sewa kuwadi Sanggar Rias Ratu Sidayu — Gresik.
    </p>
    <div class="mt-3 flex gap-2">
      <a href="#booking" class="px-3 py-2 rounded text-white font-medium"
         style="background:linear-gradient(90deg,#0b5a3a,#06422a);">
        Pesan Sekarang
      </a>
      <a href="#kontak" class="px-3 py-2 rounded border">
        Hubungi
      </a>
    </div>
  </div>
</div>
      </div>
    </div>

    <!-- Paket Section -->
    <section id="paket" class="mt-12 max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between">
        <h2 class="text-2xl font-semibold text-ratu-green">Daftar Paket Sewa Kuwadi & Job Rias</h2>
        <div class="text-sm text-gray-500">Pilih paket sesuai kebutuhan — transparan & profesional.</div>
      </div>

      <div class="mt-6 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Paket Card 1: Kuwadi Basic -->
        <article class="card bg-white border rounded-lg p-5">
          <div class="flex items-center justify-between">
            <h3 class="text-lg font-semibold"
    :class="dark ? 'text-black' : 'text-ratu-green'">
  Kuwadi Basic
</h3>
            <div class="text-sm px-2 py-1 rounded text-white" style="background:linear-gradient(90deg,#7a1414,#c62828);">Populer</div>
          </div>
          <p class="mt-3 text-sm text-gray-600">Sewa kuwadi lengkap (piring, tatakan, hias sederhana) untuk acara kecil & family gathering.</p>
          <ul class="mt-3 text-sm text-gray-700 space-y-1 list-disc pl-5">
            <li>Kuantity: sampai 50 pax</li>
            <li>Pengiriman & pasang</li>
            <li>Waktu sewa 1 hari (opsi tambahan +)</li>
          </ul>
          <div class="mt-4 flex items-center justify-between">
            <div class="text-xl font-bold text-ratu-green">Rp 950.000</div>
            <button @click="openModal('Kuwadi Basic',700000)" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Pesan</button>
          </div>
        </article>

        <!-- Paket Card 2: Kuwadi Premium -->
        <article class="card bg-white border rounded-lg p-5">
          <h3 class="text-lg font-semibold"
    :class="dark ? 'text-black' : 'text-ratu-green'">
  Kuwadi Premium
</h3>
          <p class="mt-3 text-sm text-gray-600">Hiasan lebih mewah, tawaran dekorasi tradisional, ideal untuk resepsi kecil hingga sedang.</p>
          <ul class="mt-3 text-sm text-gray-700 space-y-1 list-disc pl-5">
            <li>Kuantity: sampai 150 pax</li>
            <li>Hiasan bunga & kain</li>
            <li>Tim pemasangan profesional</li>
          </ul>
          <div class="mt-4 flex items-center justify-between">
            <div class="text-xl font-bold text-ratu-green">Rp 2.200.000</div>
            <button @click="openModal('Kuwadi Premium',2200000)" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Pesan</button>
          </div>
        </article>

        <!-- Paket Card 3: Job Rias Pengantin -->
        <article class="card bg-white border rounded-lg p-5">
          <h3 class="text-lg font-semibold"
    :class="dark ? 'text-black' : 'text-ratu-green'">
  Job Rias Pengantin
</h3>
          <p class="mt-3 text-sm text-gray-600">Rias pengantin lengkap (makeup & hairdo), datang ke lokasi, trial rias 1x.</p>
          <ul class="mt-3 text-sm text-gray-700 space-y-1 list-disc pl-5">
            <li>Makeup + tata rambut</li>
            <li>Asisten rias (opsional)</li>
            <li>Durasi layanan 6 jam</li>
          </ul>
          <div class="mt-4 flex items-center justify-between">
            <div class="text-xl font-bold text-ratu-green">Rp 1.800.000</div>
            <button @click="openModal('Job Rias Pengantin',1800000)" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Pesan</button>
          </div>
        </article>

        <!-- Paket Card 4: Job Rias Acara (Non-Pengantin) -->
        <article class="card bg-white border rounded-lg p-5">
          <h3 class="text-lg font-semibold"
    :class="dark ? 'text-black' : 'text-ratu-green'">
  Job Rias Acara
</h3>
          <p class="mt-3 text-sm text-gray-600">Rias tamu/peserta acara, natural & tahan lama.</p>
          <ul class="mt-3 text-sm text-gray-700 space-y-1 list-disc pl-5">
            <li>Per orang</li>
            <li>Group booking tersedia</li>
          </ul>
          <div class="mt-4 flex items-center justify-between">
            <div class="text-xl font-bold text-ratu-green">Rp 180.000 / org</div>
            <button @click="openModal('Job Rias Acara',180000)" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Pesan</button>
          </div>
        </article>

        <!-- Paket Card 5: Paket Tradisional Lengkap -->
        <article class="card bg-white border rounded-lg p-5">
          <h3 class="text-lg font-semibold"
    :class="dark ? 'text-black' : 'text-ratu-green'">
  Paket Tradisional Lengkap
</h3>
          <p class="mt-3 text-sm text-gray-600">Rias adat lengkap + kuwadi dekor tradisional untuk pengantin.</p>
          <ul class="mt-3 text-sm text-gray-700 space-y-1 list-disc pl-5">
            <li>Rias pengantin adat</li>
            <li>Kuwadi & hias adat</li>
            <li>Tim lengkap</li>
          </ul>
          <div class="mt-4 flex items-center justify-between">
            <div class="text-xl font-bold text-ratu-green">Rp 4.500.000</div>
            <button @click="openModal('Paket Tradisional Lengkap',4500000)" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Pesan</button>
          </div>
        </article>

        <!-- Paket Card 6: Paket Hemat -->
        <article class="card bg-white border rounded-lg p-5">
          <h3 class="text-lg font-semibold"
    :class="dark ? 'text-black' : 'text-ratu-green'">
  Paket Hemat
</h3>
          <p class="mt-3 text-sm text-gray-600">Solusi ekonomis untuk acara kecil: kuwadi + rias sederhana.</p>
          <ul class="mt-3 text-sm text-gray-700 space-y-1 list-disc pl-5">
            <li>Terbatas hingga 30 pax</li>
            <li>Pengiriman + pemasangan</li>
          </ul>
          <div class="mt-4 flex items-center justify-between">
            <div class="text-xl font-bold text-ratu-green">Rp 450.000</div>
            <button @click="openModal('Paket Hemat',450000)" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Pesan</button>
          </div>
        </article>
         

      </div>
    </section>

    <!-- Harga & Kebijakan -->
    <section id="harga" class="mt-12 max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="bg-white border rounded-lg p-6 shadow-sm">
        <h2 class="text-2xl font-semibold text-ratu-green">Keterangan Harga & Kebijakan</h2>
        <ul class="mt-3 list-disc pl-5 text-sm text-gray-700 space-y-2">
          <li>Harga sudah termasuk biaya pemasangan (kecuali jarak > 20 km dari Sidayu — biaya tambahan akan dikenakan).</li>
          <li>Booking wajib membayar DP 30% untuk konfirmasi tanggal.</li>
          <li>Pembatalan kurang dari 7 hari sebelum acara: DP tidak dapat dikembalikan.</li>
          <li>Untuk kebutuhan khusus (hias mewah, jumlah pax besar), hubungi admin untuk penawaran khusus.</li>
        </ul>
      </div>
    </section>

    <!-- Galeri -->
    <section id="galeri" class="mt-12 max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
  <h2 class="text-2xl font-semibold text-ratu-green">Galeri Pekerjaan</h2>
  <div class="mt-4 grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-3">
    <img src="assets/gallery1.jpg" alt="galeri 1" class="w-full h-36 object-cover rounded-lg" />
    <img src="assets/gallery2.jpg" alt="galeri 2" class="w-full h-36 object-cover rounded-lg" />
    <img src="assets/gallery3.jpg" alt="galeri 3" class="w-full h-36 object-cover rounded-lg" />
    <img src="assets/gallery4.jpg" alt="galeri 4" class="w-full h-36 object-cover rounded-lg" />
    <img src="assets/gallery5.jpg" alt="galeri 5" class="w-full h-36 object-cover rounded-lg" />
    <img src="assets/gallery6.jpg" alt="galeri 6" class="w-full h-36 object-cover rounded-lg" />
    <img src="assets/gallery7.jpg" alt="galeri 7" class="w-full h-36 object-cover rounded-lg" />
    <img src="assets/gallery8.jpg" alt="galeri 8" class="w-full h-36 object-cover rounded-lg" />
  </div>
</section>
    <!-- Testimoni -->
    <section id="testimoni" class="mt-12 max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-2xl font-semibold text-ratu-green">Testimoni</h2>
      <div class="mt-4 grid grid-cols-1 md:grid-cols-2 gap-4">
        <div class="bg-white border rounded-lg p-4">
          <p class="text-sm text-gray-700">"Riasnya awet dan timnya ramah. Kuwadinya juga rapi — semuanya teratur."</p>
          <div class="mt-3 text-xs text-gray-500">— Aisyah, Pengantin 2024</div>
        </div>
        <div class="bg-white border rounded-lg p-4">
          <p class="text-sm text-gray-700">"Pelayanan cepat, harga sesuai kualitas. Recommended!"</p>
          <div class="mt-3 text-xs text-gray-500">— Hendra, Event Organizer</div>
        </div>
      </div>
    </section>

    <!-- Booking Form -->
    <section id="booking" class="mt-12 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="bg-white border rounded-lg p-6 shadow-sm">
        <h2 class="text-2xl font-semibold text-ratu-green">Form Booking / Permintaan Penawaran</h2>
        <p class="text-sm text-gray-600 mt-2">Isi form berikut untuk reservasi atau permintaan penawaran. Kami akan menghubungi Anda via WhatsApp/telepon.</p>

        <form id="bookingForm" class="mt-4 space-y-4" method="POST" action="/api/bookings" onsubmit="return submitBooking(event)">
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <label class="block">
              <span class="text-sm font-medium">Nama *</span>
              <input type="text" id="bname" name="name" required class="mt-1 block w-full rounded border px-3 py-2" />
            </label>
            <label class="block">
              <span class="text-sm font-medium">No. Telepon / WA *</span>
              <input type="tel" id="btelp" name="telp" required class="mt-1 block w-full rounded border px-3 py-2" />
            </label>
          </div>

          <label class="block">
            <span class="text-sm font-medium">Email</span>
            <input type="email" id="bemail" name="email" class="mt-1 block w-full rounded border px-3 py-2" />
          </label>

          <label class="block">
            <span class="text-sm font-medium">Paket yang dipilih *</span>
            <select id="bpaket" name="paket" required class="mt-1 block w-full rounded border px-3 py-2">
              <option value="">— Pilih Paket —</option>
              <option value="Kuwadi Basic">Kuwadi Basic</option>
              <option value="Kuwadi Premium">Kuwadi Premium</option>
              <option value="Job Rias Pengantin">Job Rias Pengantin</option>
              <option value="Job Rias Acara">Job Rias Acara</option>
              <option value="Paket Tradisional Lengkap">Paket Tradisional Lengkap</option>
              <option value="Paket Hemat">Paket Hemat</option>
            </select>
          </label>

          <label class="block">
            <span class="text-sm font-medium">Tanggal Acara *</span>
            <input type="date" id="bdate" name="tanggal" required class="mt-1 block w-full rounded border px-3 py-2" />
          </label>

          <label class="block">
            <span class="text-sm font-medium">Catatan / Permintaan Khusus</span>
            <textarea id="bnotes" name="catatan" class="mt-1 block w-full rounded border px-3 py-2" rows="3"></textarea>
          </label>

          <div class="flex gap-3">
            <button type="submit" class="px-5 py-2 rounded text-white font-semibold" style="background:linear-gradient(90deg,#7a1414,#c62828);">Kirim Permintaan</button>
            <button type="button" onclick="resetBooking()" class="px-4 py-2 rounded border">Bersihkan</button>
          </div>
        </form>

        <div id="bookingMsg" class="mt-4 hidden p-3 rounded text-sm"></div>
      </div>
    </section>

    <!-- Kontak -->
    <section id="kontak" class="mt-12 max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 mb-12">
      <div class="bg-[linear-gradient(90deg,#0b5a3a,#06422a)] text-white rounded-lg p-6 shadow-lg">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div>
            <h3 class="font-semibold text-lg">Sanggar Rias Ratu</h3>
            <p class="text-sm mt-2">Jl. Pelita III, Desa Asempapak, Sidayu, Gresik</p>
            <p class="text-sm mt-1">Telp/WA: <strong>0857-5555-9341</strong></p>
            <p class="text-sm mt-1">Email: <strong>info.sanggarriasratusidayu@gmail.com</strong></p>
          </div>
          <div>
            <h4 class="font-semibold">Jam Operasional</h4>
            <p class="text-sm mt-2">Sen — Sab: 08.00 — 21.00</p>
            <p class="text-sm mt-1">Minggu: Tetap buka / By appointment</p>
          </div>
          <div>
            <h4 class="font-semibold">Ikuti Kami</h4>
            <div class="mt-2 flex gap-3">
              <a href="#" class="px-3 py-2 rounded bg-white text-ratu-green text-sm font-medium">Instagram</a>
              <a href="#" class="px-3 py-2 rounded bg-white text-ratu-green text-sm font-medium">WhatsApp</a>
            </div>
          </div>
        </div>
      </div>
    </section>

  </main>

  <footer class="bg-white border-t py-6">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-sm text-gray-600">
      © <span id="year"></span> Sanggar Rias Ratu • Semua hak dilindungi.
    </div>
  </footer>

  <!-- Modal for quick booking (client-side) -->
  <div x-data="bookingModal()" x-cloak>
    <div x-show="open" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
      <div @click.away="close()" class="bg-white rounded-lg max-w-md w-full p-6">
        <h3 class="text-lg font-semibold text-ratu-green" x-text="title"></h3>
        <p class="text-sm text-gray-600 mt-2">Harga: <strong x-text="formatPrice(price)"></strong></p>
        <p class="text-sm text-gray-600 mt-2">Silakan isi form booking untuk konfirmasi tanggal dan DP. Kami akan mengontak Anda.</p>
        <div class="mt-4 flex gap-3">
          <button @click="proceed()" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Isi Form Booking</button>
          <button @click="close()" class="px-4 py-2 rounded border">Tutup</button>
        </div>
      </div>
    </div>
  </div>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();

    function bookingModal(){
      return {
        open:false, title:'', price:0,
        formatPrice(v){ return 'Rp ' + v.toString().replace(/\B(?=(\d{3})+(?!\d))/g, '.'); },
        openModal(name,price){ this.title = name; this.price = price; this.open = true; },
        close(){ this.open = false; },
        proceed(){ this.close(); document.getElementById('bpaket').value = this.title; document.getElementById('bpaket').dispatchEvent(new Event('change')); window.scrollTo({top: document.getElementById('booking').offsetTop - 60, behavior:'smooth'}); }
      }
    }

    // Expose helper to Alpine root
    window.openModal = function(name, price){ document.querySelectorAll('[x-data]').forEach(el => { const comp = el.__x; if(comp && comp.getUnobservedData){ /* noop */ } });
      // Use a simple global modal data store
      if(window._ratuModal){ window._ratuModal.title = name; window._ratuModal.price = price; window._ratuModal.open = true; }
    };

    // Initialize a global reference for modal
    document.addEventListener('alpine:init', () => {
      Alpine.data('bookingModal', bookingModal);
    });

    // Submit ke endpoint nyata dengan fetch API + buka WhatsApp
async function submitBooking(e){
  e.preventDefault();
  const form = document.getElementById('bookingForm');

  const name   = document.getElementById('bname').value;
  const telp   = document.getElementById('btelp').value;
  const email  = document.getElementById('bemail').value;
  const paket  = document.getElementById('bpaket').value;
  const tanggal= document.getElementById('bdate').value;
  const catatan= document.getElementById('bnotes').value;

  // Siapkan FormData untuk tetap kirim ke server (opsional, bisa dihapus jika tidak dipakai)
  const formData = new FormData(form);

  try{
    // Kirim ke backend (jika endpoint sudah ada)
    const res = await fetch(form.action, {
      method: 'POST',
      body: formData
    });

    if(!res.ok){
      throw new Error('Gagal mengirim ke server.');
    }

    // Tampilkan pesan di website
    showBookingMsg('Permintaan booking Anda berhasil disimpan. WhatsApp akan dibuka untuk konfirmasi ke admin.', true);

  }catch(err){
    console.error(err);
    // Kalau gagal ke server, tetap lanjutkan ke WhatsApp agar tidak rugi data
    showBookingMsg('Gagal menyimpan ke server, tetapi kami tetap membuka WhatsApp agar Anda bisa kirim data ke admin.', false);
  }

  // ========================
  // BUKA WHATSAPP OTOMATIS
  // ========================
  const adminNumber = '6285755559341'; // 62 + 85755559341 (tanpa 0 depan)

  const message =
    `Assalamu'alaikum, saya ingin booking Dekorasi & Makeup sanggar rias ratu.\n\n` +
    `Nama: ${name}\n` +
    `No. HP/WA: ${telp}\n` +
    (email ? `Email: ${email}\n` : '') +
    `Paket: ${paket}\n` +
    `Tanggal Acara: ${tanggal}\n` +
    (catatan ? `Catatan: ${catatan}\n` : '') +
    `\nMohon konfirmasi ketersediaan admin Sanggar Rias Ratu mengenai tanggal dan detail pembayaran DP yang perlu saya bayarkan. Terima kasih.`;

  const url = `https://wa.me/${adminNumber}?text=${encodeURIComponent(message)}`;

  // Buka WA di tab baru (atau aplikasi WA di HP)
  window.open(url, '_blank');

  // Reset form setelah itu
  form.reset();
  return false;
}

    function showBookingMsg(msg, ok){
      const el = document.getElementById('bookingMsg');
      el.textContent = msg; el.classList.remove('hidden');
      el.classList.toggle('bg-green-100', ok); el.classList.toggle('text-green-800', ok);
      el.classList.toggle('bg-red-100', !ok); el.classList.toggle('text-red-800', !ok);
    }

    function resetBooking(){ document.getElementById('bookingForm').reset(); document.getElementById('bookingMsg').classList.add('hidden'); }

    // Attach openModal to window for card buttons
    window.openModal = function(name, price){
      // create temporary modal overlay
      const modal = document.createElement('div');
      modal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50';
      modal.innerHTML = `<div class="bg-white rounded-lg max-w-md w-full p-6">
        <h3 class="text-lg font-semibold text-[#0b5a3a]">${name}</h3>
        <p class="text-sm text-gray-600 mt-2">Harga: <strong>Rp ${price.toString().replace(/\B(?=(\d{3})+(?!\d))/g,'.')}</strong></p>
        <p class="text-sm text-gray-600 mt-2">Silakan isi form booking untuk konfirmasi tanggal dan DP. Kami akan mengontak Anda.</p>
        <div class="mt-4 flex gap-3">
          <button id="openBookingForm" class="px-4 py-2 rounded text-white" style="background:linear-gradient(90deg,#0b5a3a,#06422a);">Isi Form Booking</button>
          <button id="closeModalBtn" class="px-4 py-2 rounded border">Tutup</button>
        </div>
      </div>`;
      document.body.appendChild(modal);
      document.getElementById('openBookingForm').onclick = function(){ document.getElementById('bpaket').value = name; document.getElementById('bpaket').dispatchEvent(new Event('change')); modal.remove(); window.scrollTo({top: document.getElementById('booking').offsetTop - 60, behavior:'smooth'}); };
      document.getElementById('closeModalBtn').onclick = function(){ modal.remove(); };
    };

  </script>
<script>
  // SLIDER "Siap Melayani"
  document.addEventListener('DOMContentLoaded', function(){
    const track = document.getElementById('sliderTrack');
    if(!track) return;

    const slides = track.querySelectorAll('img');
    const bullets = document.querySelectorAll('[data-slide]');
    const total = slides.length;
    let current = 0;
    let intervalId = null;

    function goToSlide(index){
      current = index;
      const offset = -100 * index; // persen
      track.style.transform = `translateX(${offset}%)`;

      // update bullets
      bullets.forEach((b, i) => {
        if(i === index){
          b.classList.remove('bg-white/40');
          b.classList.add('bg-white', 'w-3', 'h-3');
        }else{
          b.classList.remove('bg-white', 'w-3', 'h-3');
          b.classList.add('bg-white/40', 'w-2.5', 'h-2.5');
        }
      });
    }

    function nextSlide(){
      const next = (current + 1) % total;
      goToSlide(next);
    }

    // Auto slide setiap 4 detik
    function startAuto(){
      if(intervalId) clearInterval(intervalId);
      intervalId = setInterval(nextSlide, 4000);
    }

    // Klik bullet manual
    bullets.forEach(b => {
      b.addEventListener('click', () => {
        const idx = parseInt(b.getAttribute('data-slide'), 10);
        goToSlide(idx);
        startAuto(); // reset timer setelah klik
      });
    });

    // Inisialisasi
    goToSlide(0);
    startAuto();
  });
</script>
</body>
</html>
<form id="bookingForm"
      class="mt-4 space-y-4"
      method="POST"
      action="/api/bookings"
      onsubmit="return submitBooking(event)">

