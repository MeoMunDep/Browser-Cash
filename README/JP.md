### 🚀 Browsercashボット設定ガイド

このガイドでは、初心者の方でもわかりやすく、**Browsercash ボットのインストールと設定方法**をステップごとに説明します。
それでは始めましょう 👇

📱 **モバイルユーザー（Termux）はこちら:**
[Termux 用ガイドを見る](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## 📘 目次

1. [システム要件](#システム要件)
2. [ボットのインストール](#ボットのインストール)
3. [ボットの設定](#ボットの設定)
4. [ボットの起動](#ボットの起動)
5. [ボットの更新](#ボットの更新)
6. [サポートと連絡先](#サポートと連絡先)

---

## 🧩 システム要件

ボットを実行する前に、以下をインストールしてください：

* **Node.js**（バージョン: `22.11.0`）
* **npm**（バージョン: `10.9.0`）
* **Git**
* **Docker** *(オプション)*

📥 **Node.js & npm:** [こちらからダウンロード](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [こちらからダウンロード](https://t.me/KeoAirDropFreeNe/257/60831)

---

## ⚙️ ボットのインストール

<details>
<summary><strong>🔧 Git を使ってインストール</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 手動インストール</strong></summary>

1. ボットを手動でダウンロードして解凍します。
2. 上記と同じ `npm install` コマンドを実行します。

</details>

<details>
<summary><strong>🐳 Docker でインストール</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 **Windows CMD** の場合は、`$(pwd)` の代わりに `%cd%` を使用してください。

</details>

---

## 🧾 ボットの設定

<details open>
<summary><strong>📜 1. <code>configs.json</code> – メイン設定</strong></summary>

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

| パラメータ名                        | 型                  | デフォルト値     | 説明                        |
| ----------------------------- | ------------------ | ---------- | ------------------------- |
| `rotateProxy`                 | `boolean`          | `false`    | アカウント間でプロキシをローテーションするかどうか |
| `proxyMode`                   | `string`           | `"static"` | 使用するプロキシモード               |
| `skipInvalidProxy`            | `boolean`          | `false`    | 無効なプロキシをスキップする            |
| `proxyRotationInterval`       | `number`           | `2`        | プロキシを切り替える間隔（分）           |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`   | 各アカウント間のランダムな遅延（秒）        |
| `timeToRestartAllAccounts`    | `number`           | `300`      | 全アカウント再起動までの時間（秒）         |
| `howManyAccountsRunInOneTime` | `number`           | `100`      | 同時に実行するアカウント数             |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> – アカウント情報</strong></summary>

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> – プロキシリスト</strong></summary>

📥 [Webshareの無料プロキシを入手](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> – ウォレット一覧</strong></summary>

📥 [ウォレットを自動生成するツール](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
```

</details>

---

## ▶️ ボットの起動

<details open>
<summary><strong>🪟 Windows (.bat)</strong></summary>

1. `run.bat` をダブルクリックします。
2. ボットが自動的に更新・依存関係をインストールし、起動します。

> 失敗する場合は、右クリック → **管理者として実行**
> または CMD で手動実行：

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Docker</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

再起動する場合：

```bash
docker start browsercash-container
```

</details>

---

## 🔄 ボットの更新

<details>
<summary><strong>Git でインストールした場合</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>Docker を使用している場合</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image .
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## 💬 サポートと連絡先

* **サポート＆拡張:** [Chrome 拡張](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf)
* **招待リンク:** [Browser.cash 公式](https://app.browser.cash/install?ref=0mu1wyhx)
* **寄付:** [寄付はこちら](https://t.me/KeoAirDropFreeNe/312/27801)
* **作者:** [@MeoMunDep](https://t.me/MeoMunDep)
* **サポートグループ:** [Telegram グループ](https://t.me/KeoAirDropFreeNe)
* **アップデートチャンネル:** [公式チャンネル](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [チャンネルを見る](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [フォローする](https://www.instagram.com/meomundep)
* **TikTok:** [フォローする](https://www.tiktok.com/@meomundep)

---

⚠️ **免責事項:**
このコードは「現状のまま」提供され、いかなる保証もありません。使用は自己責任で行ってください。
本スクリプトの再配布・販売は禁止されています。

---

<p align="center">
  <sub>✨ 作成者：<b>@MeoMunDep</b> | ご利用ありがとうございます。あなたの成功と幸運を願っています 🚀</sub>
</p>
