### 🚀 Guia de Configuração do Bot Browsercash

Bem-vindo ao guia de instalação do bot!
Siga os passos abaixo para instalar e configurar o bot corretamente.
Este guia foi criado para **novos usuários**, com explicações simples e diretas.

📱 **Para usuários móveis (Termux):** [Veja o guia aqui](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## 📘 Índice

1. [Requisitos do Sistema](#requisitos-do-sistema)
2. [Instalação do Bot](#instalação-do-bot)
3. [Configuração do Bot](#configuração-do-bot)
4. [Execução do Bot](#execução-do-bot)
5. [Atualização do Bot](#atualização-do-bot)
6. [Contato e Suporte](#contato-e-suporte)

---

## 🧩 Requisitos do Sistema

Antes de executar o bot, verifique se você tem os seguintes programas instalados:

* **Node.js** (Versão: `22.11.0`)
* **npm** (Versão: `10.9.0`)
* **Git**
* **Docker** *(Opcional)*

📥 **Node.js & npm:** [Baixar aqui](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [Baixar aqui](https://t.me/KeoAirDropFreeNe/257/60831)

---

## ⚙️ Instalação do Bot

<details>
<summary><strong>🔧 Instalar via Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 Instalação Manual</strong></summary>

1. Baixe e extraia o bot manualmente.
2. Execute o mesmo comando `npm install` acima.

</details>

<details>
<summary><strong>🐳 Instalar com Docker</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 No **Windows CMD**, use `%cd%` em vez de `$(pwd)`

</details>

---

## 🧾 Configuração do Bot

<details open>
<summary><strong>📜 1. <code>configs.json</code> – Configuração principal</strong></summary>

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

| Nome do parâmetro             | Tipo               | Padrão     | Descrição                                       |
| ----------------------------- | ------------------ | ---------- | ----------------------------------------------- |
| `rotateProxy`                 | `boolean`          | `false`    | Alternar proxies entre contas                   |
| `proxyMode`                   | `string`           | `"static"` | Tipo de proxy usado para todas as contas        |
| `skipInvalidProxy`            | `boolean`          | `false`    | Pular contas com proxy inválido                 |
| `proxyRotationInterval`       | `number`           | `2`        | Intervalo (minutos) entre trocas de proxy       |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`   | Intervalo aleatório (segundos) entre contas     |
| `timeToRestartAllAccounts`    | `number`           | `300`      | Tempo (segundos) para reiniciar todas as contas |
| `howManyAccountsRunInOneTime` | `number`           | `100`      | Número de contas executadas simultaneamente     |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> – Dados do Usuário</strong></summary>

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> – Lista de Proxies</strong></summary>

📥 [Proxies gratuitos da Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> – Lista de Carteiras</strong></summary>

📥 [Gerar carteiras aqui](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
```

</details>

---

## ▶️ Execução do Bot

<details open>
<summary><strong>🪟 No Windows (.bat)</strong></summary>

1. Dê um duplo clique em `run.bat`.
2. Ele atualizará automaticamente, instalará as dependências e iniciará o bot.

> Se falhar, clique com o botão direito → **Executar como administrador**
> Ou use o CMD:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 No Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Com Docker</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

Para reiniciar depois:

```bash
docker start browsercash-container
```

</details>

---

## 🔄 Atualização do Bot

<details>
<summary><strong>🔄 Se instalado via Git</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Se estiver usando Docker</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image .
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## 💬 Contato e Suporte

* **Suporte via Extensão:** [Extensão do Chrome](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf)
* **Link de Indicação:** [Instalar Browser.cash](https://app.browser.cash/install?ref=0mu1wyhx)
* **Doar:** [Clique aqui para doar](https://t.me/KeoAirDropFreeNe/312/27801)
* **Contato:** [@MeoMunDep](https://t.me/MeoMunDep)
* **Grupo de Suporte:** [Entrar no grupo](https://t.me/KeoAirDropFreeNe)
* **Canal de Atualizações:** [Ver canal](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [Assista aqui](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [Siga aqui](https://www.instagram.com/meomundep)
* **TikTok:** [Siga aqui](https://www.tiktok.com/@meomundep)

---

⚠️ **Aviso Legal:**
Este código é fornecido "como está", sem garantias.
Use por sua conta e risco. Qualquer redistribuição ou venda deste código é estritamente proibida.

---

<p align="center">
  <sub>✨ Criado por <b>@MeoMunDep</b> | Obrigado por usar o bot. Boa sorte e bons ganhos! 🚀</sub>
</p>
