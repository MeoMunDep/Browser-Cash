### 🚀 브라우저캐시(Browsercash) 봇 설정 가이드

이 문서는 **Browsercash 봇**을 올바르게 설치하고 설정하는 방법을 단계별로 안내합니다.
초보자도 쉽게 따라 할 수 있도록 자세히 설명되어 있습니다 👇

📱 **모바일 사용자(Termux)** 전용 가이드는 [여기에서 확인하세요](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## 📘 목차

1. [시스템 요구사항](#시스템-요구사항)
2. [봇 설치](#봇-설치)
3. [봇 설정](#봇-설정)
4. [봇 실행](#봇-실행)
5. [봇 업데이트](#봇-업데이트)
6. [연락처 및 지원](#연락처-및-지원)

---

## 🧩 시스템 요구사항

봇을 실행하기 전에 다음 프로그램들이 설치되어 있어야 합니다:

* **Node.js** (버전: `22.11.0`)
* **npm** (버전: `10.9.0`)
* **Git**
* **Docker** *(선택사항)*

📥 **Node.js & npm:** [다운로드 링크](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [다운로드 링크](https://t.me/KeoAirDropFreeNe/257/60831)

---

## ⚙️ 봇 설치

<details>
<summary><strong>🔧 Git을 통한 설치</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 수동 설치</strong></summary>

1. 봇을 직접 다운로드하고 압축을 풉니다.
2. 위와 동일한 `npm install` 명령어를 실행합니다.

</details>

<details>
<summary><strong>🐳 Docker로 설치</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 **Windows CMD**에서는 `$(pwd)` 대신 `%cd%`를 사용하세요.

</details>

---

## 🧾 봇 설정

<details open>
<summary><strong>📜 1. <code>configs.json</code> – 주요 설정</strong></summary>

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

| 설정 이름                         | 타입                 | 기본값        | 설명                          |
| ----------------------------- | ------------------ | ---------- | --------------------------- |
| `rotateProxy`                 | `boolean`          | `false`    | 계정 간 프록시 회전 활성화 여부          |
| `proxyMode`                   | `string`           | `"static"` | 프록시 모드 (static, round 등)    |
| `skipInvalidProxy`            | `boolean`          | `false`    | 잘못된 프록시가 있을 경우 계정을 건너뜀      |
| `proxyRotationInterval`       | `number`           | `2`        | 프록시 변경 주기 (분 단위)            |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`   | 각 계정 간 대기 시간 (초 단위)         |
| `timeToRestartAllAccounts`    | `number`           | `300`      | 전체 계정을 재시작하기 전 대기 시간 (초 단위) |
| `howManyAccountsRunInOneTime` | `number`           | `100`      | 동시에 실행할 계정 수                |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> – 계정 데이터</strong></summary>

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> – 프록시 목록</strong></summary>

📥 [무료 Webshare 프록시 받기](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> – 지갑 목록</strong></summary>

📥 [지갑 생성 도구 보기](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
```

</details>

---

## ▶️ 봇 실행

<details open>
<summary><strong>🪟 Windows (.bat)</strong></summary>

1. `run.bat` 파일을 더블 클릭합니다.
2. 자동으로 업데이트 및 필요한 패키지를 설치한 후 봇을 실행합니다.

> 오류가 발생하면 오른쪽 클릭 → **관리자 권한으로 실행**
> 또는 CMD에서 직접 실행:

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
<summary><strong>🐳 Docker 실행</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

다음 명령어로 재시작할 수 있습니다:

```bash
docker start browsercash-container
```

</details>

---

## 🔄 봇 업데이트

<details>
<summary><strong>Git 설치 버전</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>Docker 버전</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image .
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## 💬 연락처 및 지원

* **확장 지원:** [Chrome 확장 프로그램](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf)
* **추천 링크:** [Browser.cash 설치 링크](https://app.browser.cash/install?ref=0mu1wyhx)
* **후원:** [후원하기](https://t.me/KeoAirDropFreeNe/312/27801)
* **제작자:** [@MeoMunDep](https://t.me/MeoMunDep)
* **지원 그룹:** [Telegram 그룹 참여](https://t.me/KeoAirDropFreeNe)
* **업데이트 채널:** [공지 채널 보기](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [채널 시청](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [팔로우하기](https://www.instagram.com/meomundep)
* **TikTok:** [팔로우하기](https://www.tiktok.com/@meomundep)

---

⚠️ **면책 조항:**
이 코드는 “있는 그대로” 제공되며, 어떠한 보증도 하지 않습니다.
사용으로 인한 모든 책임은 사용자 본인에게 있습니다.
이 코드를 무단 배포하거나 판매하는 행위는 금지됩니다.

---

<p align="center">
  <sub>✨ 제작자: <b>@MeoMunDep</b> | ✨ 사용해 주셔서 감사합니다. 좋은 수익과 행운을 기원합니다 🚀</sub>
</p>
