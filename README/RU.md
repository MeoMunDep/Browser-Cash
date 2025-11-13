### 🚀 Руководство по установке Browsercash Bot

Добро пожаловать! Это пошаговое руководство поможет вам установить и запустить бота **Browsercash**.
Инструкция подходит как для начинающих, так и для опытных пользователей.

📱 **Если вы используете телефон (Termux):** [Откройте руководство здесь](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## 📘 Содержание

1. [Системные требования](#системные-требования)
2. [Установка бота](#установка-бота)
3. [Настройка бота](#настройка-бота)
4. [Запуск бота](#запуск-бота)
5. [Обновление бота](#обновление-бота)
6. [Контакты и поддержка](#контакты-и-поддержка)

---

## 🧩 Системные требования

Перед установкой убедитесь, что установлены следующие программы:

* **Node.js** (версия: `22.11.0`)
* **npm** (версия: `10.9.0`)
* **Git**
* **Docker** *(опционально)*

📥 **Node.js & npm:** [Скачать здесь](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [Скачать здесь](https://t.me/KeoAirDropFreeNe/257/60831)

---

## ⚙️ Установка бота

<details>
<summary><strong>🔧 Через Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 Ручная установка</strong></summary>

1. Скачайте и распакуйте архив с ботом.
2. Выполните ту же команду `npm install`, как указано выше.

</details>

<details>
<summary><strong>🐳 Установка через Docker</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 В **Windows CMD** используйте `%cd%` вместо `$(pwd)`

</details>

---

## 🧾 Настройка бота

<details open>
<summary><strong>📜 1. <code>configs.json</code> — Основные настройки</strong></summary>

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

| Параметр                      | Тип                | По умолчанию | Описание                                 |
| ----------------------------- | ------------------ | ------------ | ---------------------------------------- |
| `rotateProxy`                 | `boolean`          | `false`      | Включить/выключить ротацию прокси        |
| `proxyMode`                   | `string`           | `"static"`   | Режим прокси для всех аккаунтов          |
| `skipInvalidProxy`            | `boolean`          | `false`      | Пропускать нерабочие прокси              |
| `proxyRotationInterval`       | `number`           | `2`          | Интервал (мин) между сменой прокси       |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`     | Задержка (сек) между аккаунтами          |
| `timeToRestartAllAccounts`    | `number`           | `300`        | Перезапуск всех аккаунтов (сек)          |
| `howManyAccountsRunInOneTime` | `number`           | `100`        | Кол-во одновременно запущенных аккаунтов |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> — Данные аккаунтов</strong></summary>

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> — Список прокси</strong></summary>

📥 [Бесплатные прокси Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> — Список кошельков</strong></summary>

📥 [Создать кошельки можно здесь](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
```

</details>

---

## ▶️ Запуск бота

<details open>
<summary><strong>🪟 На Windows (.bat)</strong></summary>

1. Дважды кликните по `run.bat`.
2. Скрипт автоматически обновится, установит зависимости и запустит бота.

> Если не работает, нажмите **правой кнопкой → Запуск от имени администратора**
> Или используйте CMD:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 На Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Через Docker</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

Чтобы перезапустить позже:

```bash
docker start browsercash-container
```

</details>

---

## 🔄 Обновление бота

<details>
<summary><strong>🔄 Если установлен через Git</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Если через Docker</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image .
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## 💬 Контакты и поддержка

* **Расширение Chrome:** [Browser.cash Extension](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf)
* **Реферальная ссылка:** [Установить Browser.cash](https://app.browser.cash/install?ref=0mu1wyhx)
* **Донат:** [Поддержать проект](https://t.me/KeoAirDropFreeNe/312/27801)
* **Автор:** [@MeoMunDep](https://t.me/MeoMunDep)
* **Группа поддержки:** [Присоединиться](https://t.me/KeoAirDropFreeNe)
* **Канал с обновлениями:** [Открыть канал](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [Смотреть](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [Подписаться](https://www.instagram.com/meomundep)
* **TikTok:** [Подписаться](https://www.tiktok.com/@meomundep)

---

⚠️ **Отказ от ответственности:**
Данный код предоставляется "как есть", без каких-либо гарантий.
Используйте на свой страх и риск.
Перепродажа или публикация кода без разрешения запрещена.

---

<p align="center">
  <sub>✨ Автор: <b>@MeoMunDep</b> | Спасибо за использование! Удачи и больших прибылей 🚀</sub>
</p>
