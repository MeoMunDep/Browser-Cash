### 🚀 browsercash 机器人安装指南

欢迎使用机器人安装指南！请按照以下步骤正确安装和配置机器人。本指南专为新用户设计，每个步骤都有清晰的解释。

📱 **移动端用户 (Termux)：** [点击查看指南](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## 目录

1. [系统要求](#系统要求)
2. [安装机器人](#安装机器人)
3. [机器人配置](#机器人配置)
4. [运行机器人](#运行机器人)
5. [更新机器人](#更新机器人)
6. [联系与支持](#联系与支持)

---

## 系统要求

在运行机器人之前，请确保已安装以下内容：

* **Node.js**（版本：`22.11.0`）
* **npm**（版本：`10.9.0`）
* **Git**
* **Docker** *(可选)*

📥 **Node.js & npm:** [下载](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [下载](https://t.me/KeoAirDropFreeNe/257/60831)

---

## 安装机器人

<details>
<summary><strong>🔧 通过 Git 安装</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 手动安装</strong></summary>

1. 手动下载并解压机器人。
2. 运行与上面相同的 `npm install` 命令。

</details>

<details>
<summary><strong>🐳 通过 Docker 安装</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 在 **Windows CMD** 中使用 `%cd%` 替代 `$(pwd)`

</details>

---

## 机器人配置

<details open>
<summary><strong>📜 1. <code>configs.json</code> - 主配置文件</strong></summary>

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

| **参数名**                       | **类型**             | **默认值**  | **说明**          |
| ----------------------------- | ------------------ | -------- | --------------- |
| `rotateProxy`                 | `boolean`          | `false`  | 是否在账户之间轮换代理     |
| `proxyMode`                   | `string`           | `static` | 设置所有账户的代理模式     |
| `skipInvalidProxy`            | `boolean`          | `false`  | 代理无效时是否跳过该账户    |
| `proxyRotationInterval`       | `number`           | `2`      | 代理轮换间隔（分钟）      |
| `delayEachAccount`            | `[number, number]` | `[5, 8]` | 账户之间的随机延迟（秒）    |
| `timeToRestartAllAccounts`    | `number`           | `300`    | 所有账户重新启动前的时间（秒） |
| `howManyAccountsRunInOneTime` | `number`           | `100`    | 同时运行的账户数量       |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - 用户数据</strong></summary>

存放每个账户的邮箱与密码：

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - 代理列表</strong></summary>

📥 [免费代理（来自 Webshare）](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - 钱包列表</strong></summary>

📥 [在此生成钱包](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
...
```

</details>

---

## 运行机器人

<details open>
<summary><strong>🪟 在 Windows 上运行 (.bat)</strong></summary>

1. 双击 `run.bat`
2. 程序会自动更新、安装依赖并启动机器人。

> 如果运行失败，请右键选择 **以管理员身份运行**
> 或在 CMD 中执行：

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 在 Linux/macOS 上运行 (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 使用 Docker 运行</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 之后重新启动：

```bash
docker start browsercash-container
```

</details>

---

## 更新机器人

<details>
<summary><strong>🔄 如果通过 Git 安装</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 如果使用 Docker</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image . 
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## 联系与支持

* **支持我：** [扩展链接](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf) - [推荐链接](https://app.browser.cash/install?ref=0mu1wyhx)
* **捐赠：** [点击捐赠](https://t.me/KeoAirDropFreeNe/312/27801)
* **工作联系：** [@MeoMunDep](https://t.me/MeoMunDep)
* **支持群组：** [加入这里](https://t.me/KeoAirDropFreeNe)
* **更新频道：** [查看频道](https://t.me/KeoAirDropFreeNee)
* **YouTube：** [观看视频](https://www.youtube.com/@keoairdropfreene)
* **Instagram：** [关注](https://www.instagram.com/meomundep)
* **Tiktok：** [关注](https://www.tiktok.com/@meomundep)

---

⚠️ **免责声明：** 此代码以“原样”提供，不提供任何形式的担保。使用风险自负。您需对使用本代码产生的任何后果负责。严禁以任何形式重新分发或出售此代码。

<p align="center">
  <sub>✨ 由 <b>@MeoMunDep</b> 创建 | ✨ 感谢您使用本机器人，祝您赚到收益！🚀</sub>
</p>
