const express = require('express');
const path = require('path');

const app = express();

// Middleware
app.use(express.json());
app.use(express.static(path.join(__dirname, '..', 'public')));

// ==============================
// ROUTE HALAMAN
// ==============================

// Halaman utama
app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, '..', 'public', 'index.html'));
});

// ==============================
// ROUTE API
// ==============================

// API: Salam
app.get('/api/hello', (req, res) => {
  res.json({
    status: 'success',
    pesan: 'Halo! API kamu berjalan dengan baik! 🚀',
    waktu: new Date().toLocaleString('id-ID', {
      timeZone: 'Asia/Jakarta'
    }),
    teknologi: ['Node.js', 'Express.js', 'Vercel']
  });
});

// API: Info
app.get('/api/info', (req, res) => {
  res.json({
    status: 'success',
    data: {
      nama: 'Website Pertamaku',
      versi: '1.0.0',
      dibuat_dengan: 'HP Android + GitHub + Vercel',
      author: 'Nama Kamu'
    }
  });
});

// Handle 404
app.use((req, res) => {
  res.status(404).json({
    status: 'error',
    pesan: 'Halaman tidak ditemukan'
  });
});

// Jalankan server
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`✅ Server jalan di port ${PORT}`);
});

module.exports = app;
