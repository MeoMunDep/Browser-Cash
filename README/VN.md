### 🚀 Hướng Dẫn Cài Đặt Bot browsercash

Chào mừng bạn đến với hướng dẫn cài đặt bot! Hãy làm theo các bước bên dưới để cài đặt và cấu hình bot đúng cách. Hướng dẫn này được viết dành cho người mới, với mô tả chi tiết và dễ hiểu cho từng bước.

📱 **Dành cho người dùng Mobile (Termux):** [Xem hướng dẫn tại đây](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## Mục Lục

1. [Yêu Cầu Hệ Thống](#yêu-cầu-hệ-thống)
2. [Cài Đặt Bot](#cài-đặt-bot)
3. [Cấu Hình Bot](#cấu-hình-bot)
4. [Chạy Bot](#chạy-bot)
5. [Cập Nhật Bot](#cập-nhật-bot)
6. [Liên Hệ & Hỗ Trợ](#liên-hệ--hỗ-trợ)

---

## Yêu Cầu Hệ Thống

Trước khi chạy bot, hãy đảm bảo bạn đã cài đặt:

* **Node.js** (Phiên bản: `22.11.0`)
* **npm** (Phiên bản: `10.9.0`)
* **Git**
* **Docker** *(Không bắt buộc)*

📥 **Node.js & npm:** [Tải tại đây](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [Tải tại đây](https://t.me/KeoAirDropFreeNe/257/60831)

---

## Cài Đặt Bot

<details>
<summary><strong>🔧 Cài Đặt qua Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 Cài Đặt Thủ Công</strong></summary>

1. Tải xuống và giải nén bot.
2. Chạy cùng lệnh `npm install` như ở trên.

</details>

<details>
<summary><strong>🐳 Cài Đặt qua Docker</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 Trên **Windows CMD**, dùng `%cd%` thay vì `$(pwd)`

</details>

---

## Cấu Hình Bot

<details open>
<summary><strong>📜 1. <code>configs.json</code> - Cấu Hình Chính</strong></summary>

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

| **Tên Tham Số**               | **Loại**           | **Mặc Định** | **Mô Tả**                                     |
| ----------------------------- | ------------------ | ------------ | --------------------------------------------- |
| `rotateProxy`                 | `boolean`          | `false`      | Bật xoay proxy giữa các tài khoản             |
| `proxyMode`                   | `string`           | `static`     | Chế độ sử dụng proxy cho tất cả tài khoản     |
| `skipInvalidProxy`            | `boolean`          | `false`      | Bỏ qua tài khoản nếu proxy bị lỗi             |
| `proxyRotationInterval`       | `number`           | `2`          | Thời gian (phút) giữa các lần xoay proxy      |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`     | Độ trễ ngẫu nhiên (giây) giữa các tài khoản   |
| `timeToRestartAllAccounts`    | `number`           | `300`        | Thời gian (giây) để khởi động lại toàn bộ bot |
| `howManyAccountsRunInOneTime` | `number`           | `100`        | Số lượng tài khoản chạy song song cùng lúc    |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - Dữ Liệu Người Dùng</strong></summary>

Email và mật khẩu cho từng tài khoản:

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - Danh Sách Proxy</strong></summary>

📥 [Proxy miễn phí từ Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - Danh Sách Ví</strong></summary>

📥 [Tạo ví tại đây](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
...
```

</details>

---

## Chạy Bot

<details open>
<summary><strong>🪟 Chạy trên Windows (.bat)</strong></summary>

1. Nhấp đúp `run.bat`
2. Tự động cập nhật, cài đặt dependencies và chạy bot.

> Nếu lỗi, nhấn chuột phải → **Run as Administrator**
> Hoặc chạy bằng CMD:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Chạy trên Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Chạy qua Docker</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> Khởi động lại sau:

```bash
docker start browsercash-container
```

</details>

---

## Cập Nhật Bot

<details>
<summary><strong>🔄 Nếu cài đặt qua Git</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Nếu sử dụng Docker</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image .
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## Liên Hệ & Hỗ Trợ

* **Ủng hộ mình qua** [Extension Link](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf) - [Referral Link](https://app.browser.cash/install?ref=0mu1wyhx)
* **Donate:** [Donate tại đây](https://t.me/KeoAirDropFreeNe/312/27801)
* **Liên hệ (Công việc):** [@MeoMunDep](https://t.me/MeoMunDep)
* **Nhóm hỗ trợ:** [Tham gia tại đây](https://t.me/KeoAirDropFreeNe)
* **Kênh cập nhật:** [Xem tại đây](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [Xem tại đây](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [Theo dõi](https://www.instagram.com/meomundep)
* **Tiktok:** [Theo dõi](https://www.tiktok.com/@meomundep)

---

⚠️ **Lưu ý**: Mã nguồn được cung cấp “nguyên trạng” mà không có bất kỳ bảo đảm nào. Hãy tự chịu trách nhiệm khi sử dụng. Nghiêm cấm bán lại hoặc phân phối mã này dưới bất kỳ hình thức nào.

<p align="center">
  <sub>✨ Được tạo bởi <b>@MeoMunDep</b> | ✨ Cảm ơn bạn đã sử dụng bot, chúc bạn kiếm được thật nhiều tiền với script của mình! 🚀</sub>
</p>
