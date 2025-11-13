### 🚀 Panduan Pengaturan Bot browsercash

Selamat datang di panduan pengaturan bot! Ikuti langkah-langkah di bawah ini untuk menginstal dan mengonfigurasi bot dengan benar. Panduan ini dibuat untuk pengguna baru dengan penjelasan yang jelas di setiap langkah.

📱 **Untuk Pengguna Mobile (Termux):** [Lihat panduannya di sini](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## Daftar Isi

1. [Persyaratan Sistem](#persyaratan-sistem)
2. [Instalasi Bot](#instalasi-bot)
3. [Konfigurasi Bot](#konfigurasi-bot)
4. [Menjalankan Bot](#menjalankan-bot)
5. [Memperbarui Bot](#memperbarui-bot)
6. [Kontak & Dukungan](#kontak--dukungan)

---

## Persyaratan Sistem

Sebelum menjalankan bot, pastikan Anda telah menginstal:

* **Node.js** (Versi: `22.11.0`)
* **npm** (Versi: `10.9.0`)
* **Git**
* **Docker** *(Opsional)*

📥 **Node.js & npm:** [Unduh di sini](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [Unduh di sini](https://t.me/KeoAirDropFreeNe/257/60831)

---

## Instalasi Bot

<details>
<summary><strong>🔧 Instalasi melalui Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 Instalasi Manual</strong></summary>

1. Unduh dan ekstrak bot secara manual.
2. Jalankan perintah `npm install` yang sama seperti di atas.

</details>

<details>
<summary><strong>🐳 Instalasi dengan Docker</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 Di **Windows CMD**, gunakan `%cd%` alih-alih `$(pwd)`

</details>

---

## Konfigurasi Bot

<details open>
<summary><strong>📜 1. <code>configs.json</code> - Konfigurasi Utama</strong></summary>

```json
{
  "rotateProxy": false,
  "proxyMode": "static",
  "skipInvalidProxy": false,
  "proxyRotationInterval": 2,
  "delayEachAccount": [5, 8],
  "timeToRestartAllAccounts": 300,
  "howManyAccountsRunInOneTime": 100
}
```

| **Nama Parameter**            | **Tipe**           | **Default** | **Deskripsi**                               |
| ----------------------------- | ------------------ | ----------- | ------------------------------------------- |
| `rotateProxy`                 | `boolean`          | `false`     | Aktifkan rotasi proxy antar akun            |
| `proxyMode`                   | `string`           | `static`    | Menentukan mode proxy untuk semua akun      |
| `skipInvalidProxy`            | `boolean`          | `false`     | Lewati akun jika proxy tidak valid          |
| `proxyRotationInterval`       | `number`           | `2`         | Waktu (menit) antara rotasi proxy           |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`    | Jeda acak (detik) antar akun                |
| `timeToRestartAllAccounts`    | `number`           | `300`       | Waktu (detik) sebelum semua akun di-restart |
| `howManyAccountsRunInOneTime` | `number`           | `100`       | Jumlah akun yang dijalankan bersamaan       |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - Data Pengguna</strong></summary>

Tuliskan email dan password untuk setiap akun:

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - Daftar Proxy</strong></summary>

📥 [Proxy gratis dari Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - Daftar Dompet</strong></summary>

📥 [Buat dompet di sini](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
...
```

</details>

---

## Menjalankan Bot

<details open>
<summary><strong>🪟 Jalankan di Windows (.bat)</strong></summary>

1. Klik dua kali `run.bat`
2. Bot akan otomatis memperbarui, menginstal dependensi, dan mulai berjalan.

> Jika gagal, klik kanan → **Run as Administrator**
> Atau jalankan dari CMD:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Jalankan di Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Jalankan dengan Docker</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> Untuk memulai ulang nanti:

```bash
docker start browsercash-container
```

</details>

---

## Memperbarui Bot

<details>
<summary><strong>🔄 Jika diinstal melalui Git</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Jika menggunakan Docker</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image .
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## Kontak & Dukungan

* **Dukung saya melalui:** [Tautan Ekstensi](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf) - [Tautan Referensi](https://app.browser.cash/install?ref=0mu1wyhx)
* **Donasi:** [Klik di sini untuk donasi](https://t.me/KeoAirDropFreeNe/312/27801)
* **Kontak (Kerja):** [@MeoMunDep](https://t.me/MeoMunDep)
* **Grup Dukungan:** [Gabung di sini](https://t.me/KeoAirDropFreeNe)
* **Saluran Pembaruan:** [Lihat di sini](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [Tonton di sini](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [Ikuti](https://www.instagram.com/meomundep)
* **Tiktok:** [Ikuti](https://www.tiktok.com/@meomundep)

---

⚠️ **Pernyataan:** Kode ini disediakan “sebagaimana adanya” tanpa jaminan apa pun. Gunakan dengan risiko Anda sendiri. Anda bertanggung jawab penuh atas semua konsekuensi dari penggunaannya. Dilarang keras mendistribusikan atau menjual ulang kode ini dalam bentuk apa pun.

<p align="center">
  <sub>✨ Dibuat oleh <b>@MeoMunDep</b> | ✨ Terima kasih telah menggunakan bot ini, semoga sukses dan banyak rezeki! 🚀</sub>
</p>
