# Redis Learning Notes

Selamat datang di repositori dokumentasi pembelajaran **Redis** saya. Repositori ini berisi catatan mengenai dasar-dasar perintah dan administrasi Redis yang telah saya pelajari.

---

## 📖 Apa itu Redis?

**Redis** (*Remote Dictionary Server*) adalah sistem penyimpanan struktur data *in-memory* yang sangat cepat, bersifat sumber terbuka (*open source*), dan sering digunakan sebagai:
- **Database**
- **Cache**
- **Message Broker**

Redis mampu memberikan performa tinggi karena menyimpan data langsung di memori (RAM), menjadikannya solusi ideal untuk aplikasi yang membutuhkan latensi rendah.

---

## 🛠️ Daftar Perintah yang Dipelajari

Berikut adalah daftar perintah yang telah saya pelajari untuk administrasi, pemantauan, dan manajemen koneksi server Redis.

### 1. Koneksi & Operasi Massal
| Command | Deskripsi |
| :--- | :--- |
| `redis-cli -h localhost -p 6379` | Menghubungkan ke server Redis lokal. |
| `redis-cli -h localhost -p 6379 -n 0 --pipe < input_file.txt` | Mengirim perintah secara massal dari file via *pipe*. |
| `select 0` | Berpindah atau memilih basis data dengan indeks tertentu. |

### 2. Administrasi & Pemantauan
| Command | Deskripsi |
| :--- | :--- |
| `monitor` | Memantau seluruh perintah yang dieksekusi server secara *real-time*. |
| `info` | Menampilkan statistik dan informasi umum tentang server. |
| `config get` | Mengambil konfigurasi server (contoh: `config get *`). |

### 3. Manajemen Klien (Client Management)
| Command | Deskripsi |
| :--- | :--- |
| `client list` | Menampilkan daftar klien yang sedang terhubung ke server. |
| `client id` | Menampilkan ID unik dari koneksi klien saat ini. |
| `client kill <ip:port>` | Memutuskan paksa koneksi klien tertentu. |

---

## 🚀 Eksplorasi Perintah Redis (Input File)

Tabel berikut menjelaskan perintah yang terdapat dalam `input_file_redis.txt` yang saya gunakan dalam pembelajaran:

| Line | Command | Penjelasan |
| :--- | :--- | :--- |
| 1-3 | `setex key 30 val` | Mengatur key dengan nilai dan durasi (TTL) 30 detik. |
| 5 | `ttl key` | Melihat sisa waktu hidup (*time to live*) dari sebuah key. |
| 7 | `set key val` | Mengatur nilai sebuah key. |
| 8 | `mset k1 v1 k2 v2` | Mengatur banyak key sekaligus. |
| 9 | `expire key 10` | Mengatur durasi (TTL) 10 detik untuk key tertentu. |
| 11 | `keys *` | Menampilkan seluruh key yang ada di database. |
| 12 | `get key` | Mengambil nilai dari sebuah key. |
| 13 | `mget k1 k2` | Mengambil nilai dari banyak key sekaligus. |
| 15-16 | `incr` / `decr` | Menambah/mengurangi nilai numerik sebuah key sebesar 1. |
| 18-19 | `incrby` / `decrby` | Menambah/mengurangi nilai numerik sebuah key sebesar N. |
| 21-24 | `multi` ... `discard` | Memulai transaksi dan membatalkannya. |
| 26-29 | `multi` ... `exec` | Memulai transaksi dan mengeksekusinya secara atomik. |
| 31 | `flushdb` | Menghapus seluruh data di database saat ini. |

---

