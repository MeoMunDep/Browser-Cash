### 🚀 Guide d'installation du bot browsercash

Bienvenue dans le guide d'installation du bot ! Suivez les étapes ci-dessous pour installer et configurer correctement le bot. Ce guide est conçu pour les nouveaux utilisateurs, avec des explications claires pour chaque étape.

📱 **Pour les utilisateurs mobiles (Termux) :** [Voir le guide ici](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## Table des matières

1. [Prérequis système](#prérequis-système)
2. [Installation du bot](#installation-du-bot)
3. [Configuration du bot](#configuration-du-bot)
4. [Exécution du bot](#exécution-du-bot)
5. [Mise à jour du bot](#mise-à-jour-du-bot)
6. [Contact et support](#contact-et-support)

---

## Prérequis système

Avant d'exécuter le bot, assurez-vous d'avoir installé :

* **Node.js** (version : `22.11.0`)
* **npm** (version : `10.9.0`)
* **Git**
* **Docker** *(optionnel)*

📥 **Node.js & npm :** [Télécharger](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git :** [Télécharger](https://t.me/KeoAirDropFreeNe/257/60831)

---

## Installation du bot

<details>
<summary><strong>🔧 Installation via Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/browsercash.git
cd browsercash
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger ethers web3 ws
```

</details>

<details>
<summary><strong>🧰 Installation manuelle</strong></summary>

1. Téléchargez et extrayez le bot manuellement.
2. Exécutez la même commande `npm install` que ci-dessus.

</details>

<details>
<summary><strong>🐳 Installation via Docker</strong></summary>

```bash
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> 💡 Sous **Windows CMD**, utilisez `%cd%` au lieu de `$(pwd)`

</details>

---

## Configuration du bot

<details open>
<summary><strong>📜 1. <code>configs.json</code> - Configuration principale</strong></summary>

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

| **Nom du paramètre**          | **Type**           | **Valeur par défaut** | **Description**                                              |
| ----------------------------- | ------------------ | --------------------- | ------------------------------------------------------------ |
| `rotateProxy`                 | `boolean`          | `false`               | Active la rotation de proxy entre les comptes                |
| `proxyMode`                   | `string`           | `static`              | Définit le type de proxy pour tous les comptes               |
| `skipInvalidProxy`            | `boolean`          | `false`               | Ignore un compte si son proxy est invalide                   |
| `proxyRotationInterval`       | `number`           | `2`                   | Intervalle (en minutes) entre les rotations de proxy         |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`              | Délai aléatoire (en secondes) entre les comptes              |
| `timeToRestartAllAccounts`    | `number`           | `300`                 | Temps (en secondes) avant le redémarrage de tous les comptes |
| `howManyAccountsRunInOneTime` | `number`           | `100`                 | Nombre de comptes exécutés simultanément                     |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - Données utilisateur</strong></summary>

Vos e-mails et mots de passe pour chaque compte :

```txt
email1|password1|installId1
email2|password2|installId2
email3|password3|installId3
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - Liste de proxys</strong></summary>

📥 [Proxy gratuit depuis Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - Liste de portefeuilles</strong></summary>

📥 [Générez vos portefeuilles ici](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
0xabc123...
0xdef456...
...
```

</details>

---

## Exécution du bot

<details open>
<summary><strong>🪟 Exécution sous Windows (.bat)</strong></summary>

1. Double-cliquez sur `run.bat`
2. Le script mettra à jour, installera les dépendances et lancera le bot automatiquement.

> Si cela échoue, faites un clic droit → **Exécuter en tant qu’administrateur**
> Ou lancez depuis le CMD :

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Exécution sous Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Exécution avec Docker</strong></summary>

```bash
docker stop browsercash-container 2>/dev/null && docker rm browsercash-container 2>/dev/null
docker build -t browsercash-image .
docker run -d --name browsercash-container -v $(pwd)/logs:/app/logs browsercash-image
```

> Pour redémarrer plus tard :

```bash
docker start browsercash-container
```

</details>

---

## Mise à jour du bot

<details>
<summary><strong>🔄 Si installé via Git</strong></summary>

```bash
cd browsercash
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Si vous utilisez Docker</strong></summary>

```bash
docker stop browsercash-container
docker rm browsercash-container
docker build -t browsercash-image .
docker run -d --name browsercash-container browsercash-image
```

</details>

---

## Contact et support

* **Soutenez-moi via** [Extension Chrome](https://chromewebstore.google.com/detail/browser-cash/oaldjcdohhhibelagdhoahbedekfjjjf) - [Lien de parrainage](https://app.browser.cash/install?ref=0mu1wyhx)
* **Faire un don :** [Faire un don ici](https://t.me/KeoAirDropFreeNe/312/27801)
* **Contact (Travail) :** [@MeoMunDep](https://t.me/MeoMunDep)
* **Groupe de support :** [Rejoindre ici](https://t.me/KeoAirDropFreeNe)
* **Canal des mises à jour :** [Voir ici](https://t.me/KeoAirDropFreeNee)
* **YouTube :** [Regarder ici](https://www.youtube.com/@keoairdropfreene)
* **Instagram :** [Suivre](https://www.instagram.com/meomundep)
* **Tiktok :** [Suivre](https://www.tiktok.com/@meomundep)

---

⚠️ **Avertissement :** Ce code est fourni "tel quel", sans aucune garantie. Vous l'utilisez à vos propres risques. Vous êtes seul responsable de toute conséquence liée à son utilisation. Toute redistribution ou vente de ce code est strictement interdite.

<p align="center">
  <sub>✨ Créé par <b>@MeoMunDep</b> | ✨ Merci d’utiliser le bot, bon gain et bonne chance ! 🚀</sub>
</p>
